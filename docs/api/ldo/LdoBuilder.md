# `LdoBuilder`

An LdoBuilder contains utility methods for building a Linked Data Object for a certain type.

It is not recommended to instantiate an LdoDataset. Instead use the [`createLdoDataset`](createLdoDataset.md) function.

## Usage

```typescript
import { LdoDataset, createLdoDatasetFactory } from "@ldo/ldo";
import { FoafProfileShapeType } from "./.ldo/foafProfile.shapeTypes";

const ldoDataset = createLdoDataset();
const ldoBuilder = ldoDataset.usingType(FoafProfileShapeType);
const profile = ldoBuilder
  .write("https://example.com/someGraph")
  .fromSubject("https://example.com/profile#me");
```

## Definition

```typescript
class LdoBuilder<Type extends LdoBase> 
```

---

### `constructor`

```typescript
constructor(
  jsonldDatasetProxyBuilder: JsonldDatasetProxyBuilder,
  shapeType: ShapeType<Type>,
)
```

#### Parameters
 - `jsonldDatasetProxyBuilder`: A [JsonldDatasetProxyBuilder](../jsonld-dataset-proxy/JsonldDatasetProxyBuilder.md)
 - `shapeType`: The [ShapeType](./ShapeType.md) for this builder

---

### `fromSubject`
`fromSubject` lets you define a an `entryNode`, the place of entry for the graph. The object returned by `jsonldDatasetProxy` will represent the given node. This parameter accepts both `namedNode`s and `blankNode`s. `fromSubject` takes a generic type representing the typescript type of the given subject.

```
fromSubject(subject: SubjectNode | string): Type
```

#### Properties

 - `subject`: The node to match

#### Usage

```typescript
const profile = ldoDataset
  .usingType(FoafProfileShapeType)
  .fromSubject("http://example.com/Person1");
```

---

### `matchSubject`
`matchSubject` returns a Jsonld Dataset Proxy representing all subjects in the dataset matching the given predicate, object, and graph.

```typescript
matchSubject(
  predicate: PredicateNode | string,
  object?: ObjectNode | string,
  graph?: GraphNode | string,
): LdSet<Type>
```

#### Parameters
 - `predicate` (Optional): A valid Predicate Node (NamedNode) or a string URI.
 - `object` (Optional): A valid object node (NamedNode, Blank Node, or Literal) or a string URI.
 - `graph` (Optional): A valid graph node (NamedNode or DefaultGraph) or a string URI.

#### Usage

```typescript
const profiles = ldoDataset
  .usingType(FoafProfileShapeType)
  .matchSubject(
    namedNode("http://www.w3.org/1999/02/22-rdf-syntax-ns#type"),
    namedNode("http://xmlns.com/foaf/0.1/Person")
  );
profiles.forEach((person) => {
  console.log(person.fn);
});
```

---

### `matchObject`
`matchObject` returns a Jsonld Dataset Proxy representing all objects in the dataset matching the given subject, predicate, and graph.

```typescript
matchObject(
  subject?: SubjectNode | string,
  predicate?: PredicateNode | string,
  graph?: GraphNode | string,
): LdSet<Type>
```

#### Parameters
 - `subject` (Optional): A valid object node (NamedNode or Blank Node) or a string URI.
 - `predicate` (Optional): A valid Predicate Node (NamedNode) or a string URI.
 - `graph` (Optional): A valid graph node (NamedNode or DefaultGraph) or a string URI.

#### Usage

```typescript
const friendsOfPerson1 = ldoDataset
  .usingType(FoafProfileShapeType)
  .matchSubject(
    namedNode("http://example.com/Person1"),
    namedNode("http://xmlns.com/foaf/0.1/knows")
  );
friendsOfPerson1.forEach((person) => {
  console.log(person.fn);
});
```

---

### `fromJson`
`fromJson` will take any regular Json, add the information to the dataset, and return a Jsonld Dataset Proxy representing the given data.

```typescript
fromJson(inputData: Type): Type
```

#### Parameters

 - `inputData`: Initial data matching the type

#### Usage
```typescript
const person2 = ldoDataset
  .usingType(FoafProfileShapeType)
  .fromJson({
    "@id": "http://example.com/Person2",
    fn: set("Jane Doe"),
  });
```

---

### `write`

By default, all new quads are added to the default graph, but you can change the graph to which new quads are added.

NOTE: These operations only dictate the graph for new triples. Any operations that delete triples will delete triples regardless of their graph.

```typescript
write(...graphs: (GraphNode | string)[]): LdoBuilder<Type>
```

#### Parameters

 - `...graphs`: any number of Graph Nodes or string URIs that all add operations will be put in.

#### Usage

```typescript
const person1 = ldoDataset.usingType(FoafShapeType)
  .write(namedNode("http://example.com/ExampleGraph"))
  .fromSubject(namedNode("http://example.com/Person1"));
person1.name.push("Jack");
console.log(dataset.toString());
// Logs:
// <http://example.com/Person1> <http://xmlns.com/foaf/0.1/name> "Jack" <http://example.com/ExampleGraph> .
```

---

### `setLanguagePreferences`

Sets the order of language preferences for Language Strings. Acceptable values are EITF language tags, "@none" and "@other"

#### Parameters
 - `...languageOrdering`: The order languages will be selected. Acceptable values are EITF language tags, "@none" and "@other".

#### Usage

```typescript
// Read Spansih first, then Korean, then language strings with no language
// New writes are in Spanish
["es", "ko", "@none"]

// Read any language other than french, then french
// New writes are in French
["@other", "fr"]
```