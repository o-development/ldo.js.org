# `ShapeType`

A `ShapeType` is an interface that contains information required by LDO to create a Linked Data Object. ShapeTypes are generated by the `@ldo/cli` `build` command, and it contains the following data:

 - ShEx Schema
 - Generated Typescript Typings
 - Generated Context


## Usage

The following is the ShapeType generated for the example `FoafProfile.shex` file.
```typescript
import { ShapeType } from "ldo";
import { foafProfileSchema } from "./foafProfile.schema";
import { foafProfileContext } from "./foafProfile.context";
import { FoafProfile } from "./foafProfile.typings";

/**
 * FoafProfile ShapeType
 */
export const FoafProfileShapeType: ShapeType<FoafProfile> = {
  schema: foafProfileSchema,
  shape: "https://example.com/FoafProfile",
  context: foafProfileContext,
};
```

This can be imported and used to create a Linked Data Object.
```typescript
import { FoafProfileShapeType } from "./.ldo/foafProfile.shapeTypes";
import { FoafProfile } from "./.ldo/foafProfile.typings";

const profile: FoafProfile = ldoDataset
  .usingType(FoafProfileShapeType)
  .fromSubject("https://example.com/profile.ttl#me");
```

## Definition

```typescript
type ShapeType<Type extends LdoBase> = {
  schema: Schema;
  shape: string;
  context: ContextDefinition;
  exampleData?: Type;
}
```

### Fields
 - `schema`: The ShEx Schema
 - `shape`: The key of the shape within the schema to which this ShapeType refers
 - `context`: A JSON-LD context generated for this Schema
 - `exampleData` (Optional): This field is optional and the `@ldo/cli` `build` command will not provide this field. The `exampleData` field's primary purpose is to force the TypeScript parser to recognize the provided `Type` so it can be auto-inferenced in the `LdoDataset.usingType` method.