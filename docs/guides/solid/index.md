# LDO for Solid Guide

`@ldo/connected-solid` is a high-level library that combines [LDO](https://ldo.js.org) with [Solid Pods](https://solidproject.org) for a type-safe interaction with linked data on the Solid platform. It extends `@ldo/connected` by adding Solid-specific concepts like containers, access control (WAC), and live update subscriptions.

## Getting Started

### 1. Install

```bash
npm install @ldo/connected-solid
```

### 2. Initialize a Connected Dataset

```ts
import { createSolidLdoDataset } from "@ldo/connected-solid";
// Use inrupt's auth library or any other Solid auth library for example
import { fetch } from "@inrupt/solid-client-authn-browser";

// Create an LdoDataset
const dataset = createSolidLdoDataset();
// Set the authenticated fetch
dataset.setContext("solid", { fetch: fetch });
```

## Core Concepts

### Resources

Use `.getResource(uri)` to get a `SolidLeaf` (file) or `SolidContainer` (folder):

```ts
const resource = dataset.getResource("https://pod.example.com/posts/myPost.ttl");
```

### Resource Types

Each resource can be:
- **Unfetched**: Not yet read
- **Absent**: 404 / doesn’t exist
- **Data Resource**: Turtle/JSON-LD
- **Binary Resource**: e.g., images or text files
- **Container**: like a folder


## Reading Resources

```ts
const readResult = await resource.read(); // Returns result object
if (readResult.isError) {
  // Handle Error
}
const readIfUnfetchedResult = await resource.readIfUnfetched(); // Reads only if needed
if (readIfUnfetchedResult.isError) {
  // Handle Error
}
```

Handles content negotiation, binary files, Turtle parsing, and error handling.

### Check State

```ts
// True if the resource exists, false if it doesn't, unefined if unknown
resource.isPresent();
// True if the resource is a binary, false if not.
resource.isBinary();
// True if the resource contains structured data, false if not.
resource.isDataResource();
```

## Creating or Uploading

### Create or Overwrite

`createAndOverwrite` (for structured data) and `uploadAndOverwrite` for binary
data will create a resource on the Solid Pod or overwrite it if it already
exits.

```ts
const createResult = await resource.createAndOverwrite();
if (createResult.isError) {
  // Handle Error
}
const uploadResult = await resource.uploadAndOverwrite(blob, mimeType);
if (uploadResult.isError) {
  // Handle Error
}
```

### Create If Absent

`createIfAbsent` (for structured data) and `uploadIfAbsent` for binary
data will create a resource on the Solid Pod only if it doesn't exist yet.

```ts
const createResult = await resource.createIfAbsent();
if (createResult.isError) {
  // Handle Error
}
const uploadResult = await resource.uploadIfAbsent(blob, mimeType);
if (createResult.isError) {
  // Handle Error
}
```

## Deleting

```ts
const result = await resource.delete();
if (result.isError) {
  // Handle error
}
```

Deletes containers recursively. Returns detailed `AggregateError` if some deletes fail.

## Updating Data (SPARQL Patch)

```ts
const transaction = dataset.startTransaction();
const profile = transaction
  .usingType(FoafShapeType)
  .write(resource)
  .fromSubject("https://example.com/profile#name");
profile.name = "John Doe";
const result = await transaction.commitToRemote();
```

## LDO Integration

```ts
const myPost = dataset.createData(
  PostShShapeType,
  "https://pod.example.com/posts/123",
  resource
);
myPost.title = "Hello Solid";
await commitData(myPost);
```

## Container Helpers

```ts
const container = dataset.getResource("https://pod.example.com/posts/");
const childContainer = container.child("newPost.ttl"); // Quick child URI
// Shorthand for creating a file
const childResult = container.createChildAndOverwrite("newPost.ttl");
if (!containerResult.isError) {
  const childResource = childResult.resource;
}
```

## Access Control (WAC)

### Read ACL

```ts
const wac = await resource.getWac();
console.log(wac.wacRule.agent[webId]); // { read: true, write: true, ... }
```

### Set ACL

```ts
await resource.setWac({
  public: { read: true, write: false, append: false, control: false },
  agent: { [webId]: { read: true, write: true, append: true, control: true } },
});
```

## Live Updates (WebSocket)

```ts
await resource.subscribeToNotifications();
resource.isSubscribedToNotifications(); // true
await resource.unsubscribeFromNotifications();
```

## Get Storage Container from WebID

```ts
import { getStorageFromWebId } from "@ldo/connected-solid";

const result = await getStorageFromWebId(webIdUri, dataset);
console.log(result.storageContainers); // array of root URIs
```

## Loading Status

Each resource has loading flags like:

```ts
resource.isReading(); 
resource.isCreating();
resource.isUpdating();
```
