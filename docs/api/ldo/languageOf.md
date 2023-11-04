# `languageOf`

The `languageOf` function lets you view and modify the language strings directly. `languageOf` takes two properties:

It returns a mapping of languages to strings or sets of strings depending on the cardinality of the JSON-LD context.

## `languageOf` Definition

```typescript
languagesOf(ldo: LdoBase, field: string | Symbol): LanguageSetMap | LanguageMap
```

### Parameters
 - `ldo`: Any Linked Data Object
 - `field`: Any field on the provided Linked Data Object

### Return

`languageOf` returns either a `LanguageSetMap` if the given field is an array, or a `LanguageMap` if the given field is a singular value. For example, `languageOf(profile, "friends")` would return a `LanguageSetMap` because there the `listOfFriendNames` field has a cardinality over 1, but `languageOf(profile, "familyName")` would return a `LanguageMap` because it has a cardinality of 1.

---

## `LangaugeMap`

```typescript
type LanguageMap = {
  "@none"?: string;
  [language: string]: string | undefined;
}
```

The `LanguageMap` is a mapping between various language tags (including the `@none` tag) and the singular language value for that tag. Modifying the `LanguageMap` will automatically update the underlying dataset.

### Usage

```typescript
const labelLanguages = languagesOf(hospitalInfo, "label");
// labelLanguages: { '@none': 'Hospital', fr: 'Hôpital', ko: '병원' }
// logs "병원"
console.log(labelLanguages.ko);
// Adds a Chinese label
labelLanguages.zh = "医院";
// Changes the no-language label from to "Super Hospital"
labelLanguages["@none"] = "Super Hospital";
// Removes the French label
delete labelLanguages.fr;
```

---

## `LangaugeSetMap`

```typescript
type LanguageMap = {
  "@none"?: string;
  [language: string]: string | undefined;
}
```

The `LanguageSetMap` is a mapping between various language tags (including the `@none` tag) and a JavaScript Set of all values for that tag. Modifying the `LanguageSetMap` will automatically update the underlying dataset.

### Usage

```typescript
const descriptionLanguages = languagesOf(hospitalInfo, "description");
// descriptionLanguages:
// {
//   '@none': Set(2) { 'Heals patients', 'Has doctors' },
//   fr: Set(2) { 'Guérit les malades', 'A des médecins' },
//   ko: Set(2) { '환자를 치료하다', '의사 있음' }
// }
// Logs: 환자를 치료하다\n의사 있음
Array.from(descriptionLanguages.ko).forEach((str) => console.log(str));
// Adds a Hindi description
descriptionLanguages.hi?.add("रोगियों को ठीक करता है");
// Checks to see if the korean label contains "의사 있음"
descriptionLanguages.ko?.has("의사 있음"); // returns true
// Removes "Has Doctors" from the no-language description
descriptionLanguages["@none"]?.delete("Has Doctors");
```