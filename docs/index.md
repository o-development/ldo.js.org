---
hide:
  - toc
---

<img src="assets/Logo-orig.png" alt="LDO Logo" style="max-height:25vh;margin-left:auto;margin-right:auto;display:block;"/>

<h1 style="text-align:center;">Solid and RDF without the Complexity</h1>

<center>

<a href="guides/raw_rdf/" class="md-button md-button--primary">For Raw Rdf</a>
<a href="guides/solid_react/" class="md-button md-button--primary">For Solid+React</a>

</center>

<div style="display: flex; justify-content: center;">
<table style="margin-left: auto;margin-right: auto;">
<tr>
<td> In LDO </td> <td> In RDF/JS </td>
</tr>
<tr>
<td>

```typescript
person.age = 23;
person.name.add("John");
```

</td>
<td>

```typescript
dataset.deleteMatches(
  namedNode("http://example.com/Person1"),
  namedNode("http://xmlns.com/foaf/0.1/age")
);
dataset.add(
  quad(
    namedNode("http://example.com/Person1"),
    namedNode("http://xmlns.com/foaf/0.1/age"),
    literal("23", "http://www.w3.org/2001/XMLSchema#integer")
  )
);
dataset.add(
  quad(
    namedNode("http://example.com/Person1"),
    namedNode("http://xmlns.com/foaf/0.1/name"),
    literal("John", "http://www.w3.org/2001/XMLSchema#string")
  )
);
```

</td>
</tr>
</table>
</div>

