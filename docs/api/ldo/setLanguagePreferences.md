# `setLanguagePreferences`

A language preference is an ordered list telling the Linked Data Object the language you prefer as well as callbacks. 



For read operations, the Linked Data Object will search for values in order of the preference. Write operations will choose the first language in the language preference, unless that language is `@other`, in which case it will choose the next language.

```typescript
// Read Spansih first, then Korean, then language strings with no language
// New writes are in Spanish
["es", "ko", "@none"]

// Read any language other than french, then french
// New writes are in French
["@other", "fr"]
```

---

## `setLanguagePreferences.using`
The `setLanguagePreferences(...).using(...)` function sets the language preferences for a set of Linked Data Objects. 

```typescript
setLanguagePreference(...languageOrdering: ("@none" | "@other" | string)[])
  .using(...ldos: LdoBase[]): void
```

### Parameters
setLanguagePreference

 - `languageOrdering`: An ordering of preferred languages. Valid values for the language preferences includes any [IETF Language Tag](https://en.wikipedia.org/wiki/IETF_language_tag) as well as the special tags `@none` and `@other`. `@none` represents any language literal that doesn't have a language tag. `@other` represents any language literal that isn't listed among the language preferences.

using

 - `ldos`: Any number of linked data objects that should have the provided language preferences applied.

### Usage

```typescript
import { setLanguagePreferences } from "@ldo/ldo";

setLanguagePreferences("fr", "ko").using(hospitalInfo);
console.log(hospitalInfo.label); // Logs "Hôpital"
setLanguagePreferences("@none").using(hospitalInfo);
console.log(hospitalInfo.label); // Logs "Hospital"
```

---

## `setLanguagePreferences.usingCopy`
The `setLanguagePreferences(...).usingCopy(...)` function returns a copy of the provided Linked Data Objects with the given language preferences.

```typescript
setLanguagePreference(...languageOrdering: ("@none" | "@other" | string)[])
  .using(...ldos: LdoBase[]): LdoBase[]
```

### Parameters
setLanguagePreference

 - `languageOrdering`: An ordering of preferred languages. Valid values for the language preferences includes any [IETF Language Tag](https://en.wikipedia.org/wiki/IETF_language_tag) as well as the special tags `@none` and `@other`. `@none` represents any language literal that doesn't have a language tag. `@other` represents any language literal that isn't listed among the language preferences.

using

 - `ldos`: Any number of linked data objects that should have the provided language preferences applied to a copy.

### Return

An array of copied Linked Data Objects with the given language preferences applied.

### Usage

```typescript
import { setLanguagePreferences } from "@ldo/ldo";

// ...

const [frenchPreference] = setLanguagePreferences("fr").usingCopy(hospitalInfo);
const [koreanPreference] = setLanguagePreferences("ko").usingCopy(hospitalInfo);
console.log(frenchPreference.label); // Logs "Hôpital"
console.log(koreanPreference.label); // Logs "병원"
```