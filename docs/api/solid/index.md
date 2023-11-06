# @ldo/solid

`@ldo/solid` is an interface for accessing Linked Data Objects with the Solid API.

## Guide

A full walkthrough for using the `@ldo/solid` library can be found in the [For Solid Guide](../../solid/index.md).

## Installation

### Automatic Installation

Navigate into your project's root folder and run the following command:
```
cd my_project/
npx run @ldo/cli init
npm i @ldo/solid
```

### Manual Installation

If you already have generated ShapeTypes, you may install the `@ldo/ldo` library independently.

```
npm i @ldo/solid @ldo/ldo
```

## Simple Example

Below is a simple example of LDO in a real use-case (changing the name on a Solid Pod). Assume that a ShapeType was previously generated and placed at `./.ldo/foafProfile.shapeTypes`.

```typescript
import { createSolidLdoDataset } from "@ldo/solid";
import { startTransaction, transactionChanges } from "@ldo/ldo";
import { FoafProfileShapeType } from "./.ldo/foafProfile.shapeTypes";

// Import an authenticated Solid Fetch function.
// In this example, the Solid authentication is performed elsewhere
import { fetch } from "@inrupt/solid-client-authn-js"

async function run() {
  /**
   * Step 1: Create a SolidLdoDataset 
   */
  const solidLdoDataset = createSolidLdoDataset({ fetch });

  /**
   * Step 2: Fetch the Solid WebId Resource
   */
  const webId = "https://example.com/jane/card.ttl#me";
  // Get a resource representation
  const webIdResource = solidLdoDataset.getResource(webId);
  // Perform a fetch of the resource
  const readResult = await webIdResource.read();
  // Check for errors
  if (readResult.isError) {
    console.error(readResult.message);
    return;
  }

  /**
   * Step 3: Get a Linked Data Object of the data retrieved in the webIdResource
   */
  // Create a linked data object by telling the dataset the type and subject of
  // the object
  const janeProfile = solidLdoDataset
    // Tells the LDO dataset that we're looking for a FoafProfile
    .usingType(FoafProfileShapeType)
    // Says the subject of the FoafProfile
    .fromSubject(webId);

  /**
   * Step 4: Read Information like it was JSON
   */
  // Logs "Jane Doe"
  console.log(janeProfile.name);
  // Logs "Person"
  console.log(janeProfile.type);
  // Logs 0
  console.log(janeProfile.knows?.length);

  /**
   * Step 5: Change data and commit it back to the Pod
   */
  // Begins a transaction that tracks your changes
  startTransaction(janeProfile);
  janeProfile.name = "Jane Smith";
  janeProfile.knows?.push({
    "@id": "https://solidweb.me/john_smith/profile/card#me",
    type: {
      "@id": "Person",
    },
    name: "John Smith",
    knows: [janeProfile],
  });
  await (transactionChanges(janeProfile));
}
run();
```

## API Details

Getting a SolidLdoDataset

 - [createSolidLdoDataset](createSolidLdoDataset.md)
 - [SolidLdoDataset](SolidLdoDataset.md)
