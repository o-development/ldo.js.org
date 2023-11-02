# `parseRdf`

## Definition

```typescript
parseRdf(data: string, parserOptions?: ParserOptions): Promise<LdoDataset>
```

### Parameters
 - `data`: The raw data to parse as a `string`.
 - `options` (optional): Parse options containing the following keys:
    - `format` (optional): The format the data is in. The following are acceptable formats: `Turtle`, `TriG`, `N-Triples`, `N-Quads`, `N3`, `Notation3`.
    - `baseIRI` (optional): If this data is hosted at a specific location, you can provide the baseIRI of that location.
    - `blankNodePrefix` (optional): If blank nodes should have a prefix, that should be provided here.
    - `factory` (optional): a RDF Data Factory from  [`@rdfjs/data-model`](https://www.npmjs.com/package/@rdfjs/data-model). 

## Usage

```typescript
import { parseRdf } from "ldo";

const rawTurtle = "...";
const ldoDataset = parseRdf(rawTurtle, { baseIRI: "https://example.com/" });
```