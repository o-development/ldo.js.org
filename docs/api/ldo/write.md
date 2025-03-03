# `write`

By default, all new quads are added to the default graph, but you can change the graph to which new quads are added using the `write` function.

---

## `write.using`
The `write(...).using(...)` function lets you define the graphs you wish to write to using specific jsonldDatasetProxies.

```typescript
write(...graphs: GraphNode[])
  .using(...ldos: LdoBase[]): void
```

### Parameters
setLanguagePreference

 - `graphs`: Any number of GraphNodes (DefaultNode or NamedNode)

using

 - `ldos`: Any number of linked data objects that should have changes written to the provided graph upon modification.

### Usage

```typescript
import { write } from "@ldo/ldo";

// Now all additions with person1 will be on ExampleGraph1
write(namedNode("http://example.com/ExampleGraph1")).using(person1);
person1.name.add("Jack");
// Now all additions with person1 will be on ExampleGraph2
write(namedNode("http://example.com/ExampleGraph2")).using(person1);
person1.name.add("Spicer");

console.log(dataset.toString());
// Logs:
// <http://example.com/Person1> <http://xmlns.com/foaf/0.1/name> "Jack" <http://example.com/ExampleGraph1> .
// <http://example.com/Person1> <http://xmlns.com/foaf/0.1/name> "Spicer" <http://example.com/ExampleGraph2> .
```

The function also returns an `end` function that will reset the graph to what it was before. This is useful for nesting graph modifications.

```typescript
person1.name.add("default");
const end1 = write(namedNode("http://example.com/Graph1")).using(person1);
person1.name.add("1");
const end2 = write(namedNode("http://example.com/Graph2")).using(person1);
person1.name.add("2");
const end3 = write(namedNode("http://example.com/Graph3")).using(person1);
person1.name.add("3");
end3();
person1.name.add("2 again");
end2();
person1.name.add("1 again");
end1();
person1.name.add("default again");
console.log(dataset.toString());
// Logs:
// <http://example.com/Person1> <http://xmlns.com/foaf/0.1/name> "default" .
// <http://example.com/Person1> <http://xmlns.com/foaf/0.1/name> "default again" .
// <http://example.com/Person1> <http://xmlns.com/foaf/0.1/name> "1" <http://example.com/Graph1> .
// <http://example.com/Person1> <http://xmlns.com/foaf/0.1/name> "1 again" <http://example.com/Graph1> .
// <http://example.com/Person1> <http://xmlns.com/foaf/0.1/name> "2" <http://example.com/Graph2> .
// <http://example.com/Person1> <http://xmlns.com/foaf/0.1/name> "2 again" <http://example.com/Graph2> .
// <http://example.com/Person1> <http://xmlns.com/foaf/0.1/name> "3" <http://example.com/Graph3> .
```

---

## `write.usingCopy`
If you would like a new variable to write to without modifying the original Jsonld Dataset Proxy, you can use `write(...).usingCopy(...)`.

```typescript
setLanguagePreference(...languageOrdering: ("@none" | "@other" | string)[])
  .using(...ldos: LdoBase[]): LdoBase[]
```

### Parameters
setLanguagePreference

 - `graphs`: Any number of GraphNodes (DefaultNode or NamedNode)

using

 - `ldos`: Any number of linked data objects that should have changes written to the provided graph upon modification.

### Return

An array of copied Linked Data Objects with the given write graphs applied.

### Usage

```typescript
const [person1WritingToNewGraph] = write(
  namedNode("http://example.com/NewGraph")
).usingCopy(person1);
person1WritingToNewGraph.name.add("Brandon");
person1.name.add("Sanderson");
console.log(dataset.toString());
// Logs:
// <http://example.com/Person1> <http://xmlns.com/foaf/0.1/name> "Brandon" <http://example.com/NewGraph> .
// <http://example.com/Person1> <http://xmlns.com/foaf/0.1/name> "Sanderson" .
```
