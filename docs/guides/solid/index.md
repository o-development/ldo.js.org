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
const 
const result = await transaction.commitToRemote();
```

Includes:
- Support for batching
- Type-safe editing via `changeData()` and `commitData()`

---

## ✨ LDO Integration

```ts
const myPost = dataset.createData(PostShShapeType, "https://pod.example.com/posts/123", resource);
myPost.title = "Hello Solid";
await commitData(myPost);
```

---

## 📁 Container Helpers

```ts
const container = dataset.getResource("https://pod.example.com/posts/");
container.child("newPost.ttl"); // Quick child URI
container.createChildAndOverwrite("newPost.ttl"); // Shorthand for creating a file
```

---

## 🛡 Access Control (WAC)

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

---

## 📡 Live Updates (WebSocket)

```ts
await resource.subscribeToNotifications();
resource.isSubscribedToNotifications(); // true
await resource.unsubscribeFromNotifications();
```

Also supports `subscribeToNotifications({ onNotificationError })` for reconnect logic.

---

## 🧠 Get Storage Container from WebID

```ts
import { getStorageFromWebId } from "@ldo/connected-solid";

const result = await getStorageFromWebId(webIdUri, dataset);
console.log(result.storageContainers); // array of root URIs
```

---

## ✅ Loading Status

Each resource has loading flags like:

```ts
resource.isReading(); 
resource.isCreating();
resource.isUpdating();
// Useful for UI feedback
```

---

## 🧪 Testing

Integration tests cover:
- Robust error handling
- Type safety
- Notification subscriptions
- ACL logic
- RDF/Turtle parsing quirks

---

## 📎 Related Packages

- [`@ldo/ldo`](https://ldo.js.org): Linked Data Objects
- [`@ldo/connected`](https://www.npmjs.com/package/@ldo/connected): Base library
- [`@solid/community-server`](https://github.com/solid/community-server): Local Pod testing

---

Would you like this guide turned into a Markdown file, or integrated into your documentation site?