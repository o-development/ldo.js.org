# `serialize`

Converts a Linked Data Object to a string representation based on a provided configuration.

## Usage

```typescript
import { serialize } from "@ldo/ldo"
// ...
const rawTurtle: string = await serialize(profile, {
  format: "Turtle",
  prefixes: {
    ex: "https://example.com/",
    foaf: "http://xmlns.com/foaf/0.1/",
  }
});
```

## Definition

```typescript
serialize(ldo: LdoBase, options: WriterOptions): Promise<string> 
```

### Parameters
 - `ldo`: Any linked data object
 - `options`: WriterOptions from N3:
   - `format` (Optional): `string | MimeFormat | undefined` The name of the format to serialize.
   - `prefixes` (Optional): `Prefixes<RDF.NamedNode | string> | - undefined` A list of prefixes that should be in the document. 
