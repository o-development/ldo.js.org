---
date: 2025-03-02 
---

# 1.0.0-alpha.1: Arrays are now Sets

I am proud to announce the release of LDO 1.0.0-alpha.1, and it has a huge breaking change: Arrays on Linked Data Objects are now Sets. In this short post I'll detail how you can easily migrate your existing LDO applications to the new paridigm as well as my reasoning for changing this.

## Migrating your Application

Migrating your application is easy if you follow some simple steps:

### Installation

1. Update the various LDO pagckages in your in your package.json to version 1.0.0-alpha.1. These packages could include:
   - `@ldo/ldo`
   - `@ldo/cli`
   - `@ldo/solid`
   - `@ldo/solid-react`
2. Run `npm install` to install the update
3. Run `npm run build:ldo` to build your LDO types.
4. New types will be generated and point you to where things will need to be updated.

### Declaring Sets

Previously, you could declare an array in LDO with array brackets (`[]`). As of 1.0.0-alpha.1, you will need to use a `LdSet` instead of an array for fields with a caridnality greater than 1. `@ldo/ldo` contains a helper function for defining sets.

```typescript
import { LdSet, set } from "@ldo/ldo";

const names = set("Garrett", "Bobby", "Ferguson");
```

So, instead of

```typescript
person.roommate = {
  "@id": "https://example.com/Person2",
  name: ["Garrett", "Bobby", "Ferguson"]
}
```

you would write the same as

```typescript
person.roommate = {
  "@id": "https://example.com/Person2",
  name: set("Garrett", "Bobby", "Ferguson")
}
```

### New Methods

Because collections are now "Sets" rather than "Arrays," the method names have been updated to reflect that. You will need to use the `add()` method rather than `push()`, or the `delete()` method rather than `splice()`. But, every array method has a set equivalent.

Check out the [documentation for a JavaScript set](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set) to view the methods you'll have access to.

I've also added in some additional methods to be more helpfule. `map()`, `reduce()`, and `filter()` may not exist on a JavaScript set, but they're helpful shorthands to accomplish familiar activities.

## Why the change?

### Arrays Implied Ordering Where There Was None

Initially, LDO treated fields with a cardinality greater than one as arrays. This seemed intuitive because JavaScript arrays naturally store multiple values. However, in RDF, collections are unordered, whereas arrays imply order. This mismatch led to confusion.

For example, consider the following RDF data:

```turtle
@prefix ex: <https://example.com/> .

ex:Person1 ex:name "Alice", "Bob", "Charlie" .
```

This simply states that "Alice," "Bob," and "Charlie" are names associated with Person1, but it does not guarantee that "Alice" comes first. However, when LDO stored these names as an array, it incorrectly suggested that order mattered:

```typescript
console.log(person.name); // ["Alice", "Bob", "Charlie"]
```

This led developers to use array-specific methods like .sort() and .reverse(), even though ordering an RDF collection doesn’t make sense. Novice developers might incorrectly assume that array indexing worked in RDF:

```typescript
person.name[1] = "Bob"; 
```

This might make sense in JavaScript, but it completely misrepresents RDF data. Since RDF doesn’t guarantee order, there’s no reason to assume "Bob" is the second name. Moving to sets eliminates this misleading behavior, guiding developers toward the correct mental model.

### Performance Issues with Hidden Ordering Logic

Since arrays allowed sorting, LDO had to silently track an ordered list in the background to ensure users who did use methods like .sort() weren't perturbed. This meant that every time you accessed a collection, LDO had to check and maintain the order.

This turned what should have been a fast O(1) lookup into an O(n) operation:

```typescript
const name = person.name[0]; // This should be fast, but it was O(n)!
```

For large datasets, this unnecessary complexity slowed down applications significantly.

### Laying the Groundwork for Proper Ordered Lists

In the future, LDO will support arrays again, but only for actual ordered lists as serialized in RDF. Before that can happen, I needed to remove the current array implementation, which incorrectly represented unordered collections.

### Conclusion

LDO originally used Arrays because, upon initial construction, I held strict to the doctrine that LDO should feel exactly like programming with JSON. But, I've now losened that doctrine as this simple change makes LDO more semantically correct while not sacroficing the ease of use that's core to its design philosophy.