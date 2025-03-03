# Advanced Data Manipulation Guide

LDO attempts to make reading and manipulating data as similar to JSON as possible. However, because LDO's job is to translate actions into RDF, there are advanced techniques that can be employed to do actions that can't be done on JSON.

## Changing an Object's Id
You can rename an object by setting its `@id` field. This will update all triples that reference the id to the new id.

```typescript
const dataset = await serializedToDataset(`
  @prefix example: <http://example.com/> .
  @prefix foaf: <http://xmlns.com/foaf/0.1/> .
  @prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

  example:Person1
    foaf:name "Alice"^^xsd:string;
    foaf:bestFriend example:Person2.
  
  example:Person2
    foaf:bestFriend example:Person1.
`);
const person = jsonldDatasetProxy(
  dataset,
  PersonContext
).fromSubject<IPerson>(namedNode("http://example.com/Person1"))
person["@id"] = "http://example.com/NewPersonId";
console.log(dataset.toString());
// <http://example.com/Person2> <http://xmlns.com/foaf/0.1/bestFriend> <http://example.com/NewPersonId> .
// <http://example.com/NewPersonId> <http://xmlns.com/foaf/0.1/name> "Alice" .
// <http://example.com/NewPersonId> <http://xmlns.com/foaf/0.1/bestFriend> <http://example.com/Person2> .
```

## Removing an Object Connection
Removing one triple can be done by setting a property to `undefined`;

```typescript
const dataset = await serializedToDataset(`
  @prefix example: <http://example.com/> .
  @prefix foaf: <http://xmlns.com/foaf/0.1/> .
  @prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

  example:Person1
    foaf:name "Alice"^^xsd:string;
    foaf:bestFriend example:Person2.
  
  example:Person2
    foaf:name "Bob"^^xsd:string;
    foaf:bestFriend example:Person1.
`);
const person = jsonldDatasetProxy(
  dataset,
  PersonContext
).fromSubject<IPerson>(namedNode("http://example.com/Person1"));
person.bestFriend = undefined;
console.log(dataset.toString());
// <http://example.com/Person1> <http://xmlns.com/foaf/0.1/name> "Alice" .
// <http://example.com/Person2> <http://xmlns.com/foaf/0.1/name> "Bob" .
// <http://example.com/Person2> <http://xmlns.com/foaf/0.1/bestFriend> <http://example.com/Person1> .
```

## Deleting an Entire Object
If you want to delete all triples represented by an object, you can call `delete` on the `@id` property.
```typescript
const dataset = await serializedToDataset(`
  @prefix example: <http://example.com/> .
  @prefix foaf: <http://xmlns.com/foaf/0.1/> .
  @prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

  example:Person1
    foaf:name "Alice"^^xsd:string;
    foaf:bestFriend example:Person2.
  
  example:Person2
    foaf:name "Bob"^^xsd:string;
    foaf:bestFriend example:Person1.
`);
const person = jsonldDatasetProxy(
  dataset,
  PersonContext
).fromSubject<IPerson>(namedNode("http://example.com/Person1"));
delete person["@id"];
console.log(dataset.toString());
// <http://example.com/Person2> <http://xmlns.com/foaf/0.1/name> "Bob" .
```

## Using Blank Nodes
If you want to create an object with a blankNode subject, simply omit the `@id` field when you're making the object.
```typescript
const dataset = await createDataset();
const person = jsonldDatasetProxy(
  dataset,
  PersonContext
).fromSubject<IPerson>(namedNode("http://example.com/Person1"));
person.bestFriend = {
  name: set("Charlie"),
};
console.log(dataset.toString());
// <http://example.com/Person1> <http://xmlns.com/foaf/0.1/bestFriend> _:b1 .
// _:b1 <http://xmlns.com/foaf/0.1/name> "Charlie" .
```

If your dataset has blank nodes and you want to assign that blank node as a triple's object, you can retrieve it from the JSONLD Dataset Proxy and assign it.
```typescript
const dataset = await serializedToDataset(`
  @prefix example: <http://example.com/> .
  @prefix foaf: <http://xmlns.com/foaf/0.1/> .
  @prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
  
  example:Person1
    foaf:knows [
      foaf:name "Alice"^^xsd:string;
    ].
`);
const person = jsonldDatasetProxy(
  dataset,
  PersonContext,
).fromSubject<IPerson>(namedNode("http://example.com/Person1"));

const alice = person.knows?.toArray()[0];
person.bestFriend = alice;
console.log(dataset.toString());
// _:n3-0 <http://xmlns.com/foaf/0.1/name> "Alice" .
// <http://example.com/Person1> <http://xmlns.com/foaf/0.1/knows> _:n3-0 .
// <http://example.com/Person1> <http://xmlns.com/foaf/0.1/bestFriend> _:n3-0 .
```

## Writing Information to a Specific Graph
By default, all new quads are added to the default graph, but you can change the graph to which new quads are added in a few different ways:

NOTE: These operations only dictate the graph for new triples. Any operations that delete triples will delete triples regardless of their graph.

#### `jsonldDatasetProxy(...).write(...graphs)`
The write graph can be set upon creating a jsonld dataset proxy by using the `write` method. This method takes in any number of graphs.

```typescript
const person1 = jsonldDatasetProxy(dataset, PersonContext)
  .write(namedNode("http://example.com/ExampleGraph"))
  .fromSubject<IPerson>(namedNode("http://example.com/Person1"));
person1.name.add("Jack");
console.log(dataset.toString());
// Logs:
// <http://example.com/Person1> <http://xmlns.com/foaf/0.1/name> "Jack" <http://example.com/ExampleGraph> .
```

### `write(...graphs).using(...jsonldDatasetProxies)`
The `write(...).using(...)` function lets you define the graphs you wish to write to using specific jsonldDatasetProxies.

```typescript
import jsonldDatasetProxy, { write } from "jsonld-dataset-proxy";

const person1 = jsonldDatasetProxy(
  dataset,
  PersonContext
).fromSubject<IPerson>(namedNode("http://example.com/Person1"));
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
const person1 = jsonldDatasetProxy(
  dataset,
  PersonContext
).fromSubject<IPerson>(namedNode("http://example.com/Person1"));
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

### `write(...graphs).usingCopy(...jsonldDatasetProxies)`
If you would like a new variable to write to without modifying the original Jsonld Dataset Proxy, you can use `write(...).usingCopy(...)`.

```typescript
const person1 = jsonldDatasetProxy(
  dataset,
  PersonContext
).fromSubject<IPerson>(namedNode("http://example.com/Person1"));
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

### Detecting the graph of specific information

The graph of specific information can be detected using the `graphOf(subject, predicate, object)` function. The `graphOf` function takes in two to three arguments.

 - `subject`: A Jsonld Dataset Proxy that represents the subject of a quad.
 - `predicate`: A string key
 - `object?`: An optional parameter that represents the direct object of a statement. This could be a Jsonld Dataset Proxy or a value to differentiate the part of an LdSet to check.

```typescript
graphOf(person, "name", "Bob"); // returns defaultGraph()
graphOf(person, "age"); // returns defaultGraph()
```

## Managing Language Tags

RDF includes a special attribute for string literals called a [language tag](https://www.w3.org/TR/rdf11-concepts/#section-Graph-Literal). Language tags let developers provide string representations for many different translations and JSON-LD Dataset Proxy helps you manage them.

To use language tags, RDF requires the datatype of a literal to be `http://www.w3.org/1999/02/22-rdf-syntax-ns#langString`, and LDO's functions will only work on literals of type that type.

For the following examples, we'll use this context and dataset, typescript typing and JSON-LD Context. Notice that there is a field called "label" with translations for French and Korean and one language string that doesn't have a language tag. There's also a field called "description" that holds multiple strings per language.

```typescript
// Define initial data
const initialData = `
  @prefix example: <http://example.com/> .
  @prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
  @prefix ns: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
  
  example:Hospital
    rdfs:label "Hospital"^^ns:langString;
    rdfs:label "Hôpital"@fr;
    rdfs:label "병원"@ko;
    rdfs:description "Heals patients"^^ns:langString;
    rdfs:description "Has doctors"^^ns:langString;
    rdfs:description "Guérit les malades"@fr;
    rdfs:description "A des médecins"@fr;
    rdfs:description "환자를 치료하다"@ko;
    rdfs:description "의사 있음"@ko.
`;

// Typescript Typing
interface IThing {
  label: string;
  description: LdSet<string>;
}

// Define JSON-LD Context
const PersonContext: ContextDefinition = {
  label: {
    "@id": "http://www.w3.org/2000/01/rdf-schema#label",
    "@type": "http://www.w3.org/1999/02/22-rdf-syntax-ns#langString",
  },
  description: {
    "@id": "http://www.w3.org/2000/01/rdf-schema#description",
    "@type": "http://www.w3.org/1999/02/22-rdf-syntax-ns#langString",
    "@container": "@set",
  },
};
```

### Language Preferences
A language preference is an ordered list telling the JSON-LD Dataset Proxy the language you prefer as well as callbacks. 

Valid values for the language preferences includes any [IETF Language Tag](https://en.wikipedia.org/wiki/IETF_language_tag) as well as the special tags `@none` and `@other`. `@none` represents any language literal that doesn't have a language tag. `@other` represents any language literal that isn't listed among the language preferences.

For read operations, the JSON-LD Dataset Proxy will search for values in order of the preference. Write operations will choose the first language in the language preference, unless that language is `@other`, in which case it will choose the next language.

```typescript
// Read Spansih first, then Korean, then language strings with no language
// New writes are in Spanish
["es", "ko", "@none"]

// Read any language other than french, then french
// New writes are in French
["@other", "fr"]
```

Language preferences can be set when a JSON-LD Dataset Proxy is created using the `setLanguagePreferences` method.

```typescript
// Create a dataset loaded with initial data
const dataset = await serializedToDataset(initialData);
// Make a JSONLD Dataset Proxy
const hospitalInfo = jsonldDatasetProxy(dataset, PersonContext)
  .setLanguagePreferences("es", "ko", "@none")
  .fromSubject<IThing>(namedNode("http://example.com/Hospital"));

console.log(hospitalInfo.label); // Logs "병원"
console.log(hospitalInfo.description.size); // Logs "2" for the 2 korean entries
console.log(hospitalInfo.description.toArray()[0]); // Logs "환자를 치료하다"
console.log(hospitalInfo.description.toArray()[1]); // Logs "의사 있음"

// Adds a string to the description in spanish, because spanish if the first
// language in the language preference
hospitalInfo.description.add("Cura a las pacientes");

// Now that a spanish entry exists, JSON-LD dataset proxy focuses on that
console.log(hospitalInfo.description.size); // Logs "1" for the 1 spanish entry
console.log(hospitalInfo.description.toArray()[0]); // Logs "Cura a las pacientes"
```

### `setLanguagePreferences(...languagePreferences).using(...jsonldDatasetProxies)`
The `setLanguagePreferences(...).using(...)` function sets the language preferences for a set of JSON-LD Dataset Proxies. It follows roughly the same paridigms as the `write(...).using(...)` function.

```typescript
import { setLanguagePreferences } from "jsonld-dataset-proxy";

setLanguagePreferences("fr", "ko").using(hospitalInfo);
console.log(hospitalInfo.label); // Logs "Hôpital"
setLanguagePreferences("@none").using(hospitalInfo);
console.log(hospitalInfo.label); // Logs "Hospital"
```

### `setLanguagePreferences(...languagePreferences).usingCopy(...jsonldDatasetProxies)`
The `setLanguagePreferences(...).usingCopy(...)` function returns a copy of the provided JSON-LD Dataset Proxies with the given language preferences. It follows roughly the same paridigms as the `write(...).usingCopy(...)` function.

```typescript
import { setLanguagePreferences } from "jsonld-dataset-proxy";

// ...

const [frenchPreference] = setLanguagePreferences("fr").usingCopy(hospitalInfo);
const [koreanPreference] = setLanguagePreferences("ko").usingCopy(hospitalInfo);
console.log(frenchPreference.label); // Logs "Hôpital"
console.log(koreanPreference.label); // Logs "병원"
```

### `languageOf(jsonldDatasetProxy, key)`
The `languageOf` function lets you view and modify the languages more directly. `languageOf` takes two properties:

 - `jsonldDatasetProxy`: A JSON-LD dataset proxy
 - `key`: A key on the JSON-LD dataset proxy pointing to a language string.

It returns a mapping of languages to strings or sets of strings depending on the cardinality of the JSON-LD context.

```typescript
const labelLanguages = languagesOf(hospitalInfo, "label");
// labelLanguages: { '@none': 'Hospital', fr: 'Hôpital', ko: '병원' }
const descriptionLanguages = languagesOf(hospitalInfo, "description");
// descriptionLanguages:
// {
//   '@none': Set(2) { 'Heals patients', 'Has doctors' },
//   fr: Set(2) { 'Guérit les malades', 'A des médecins' },
//   ko: Set(2) { '환자를 치료하다', '의사 있음' }
// }
```

You can also modify languauages by changing the mappings. Mappings with sets of strings follow the JavaScript [`Set` interface](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set).

```typescript
// Adds a Chinese label
labelLanguages.zh = "医院";
// Changes the no-language label from to "Super Hospital"
labelLanguages["@none"] = "Super Hospital";
// Removes the French label
delete labelLanguages.fr;
// Adds a Hindi description
descriptionLanguages.hi?.add("रोगियों को ठीक करता है");
// Checks to see if the korean label contains "의사 있음"
descriptionLanguages.ko?.has("의사 있음"); // returns true
// Removes "Has Doctors" from the no-language description
descriptionLanguages["@none"]?.delete("Has Doctors");
```