# SRI

---

Mécanisme garantissant qu'un fichier externe **n'a pas été modifié** en vérifiant un **hash**

## Exemple

```html
<script
  src="https://cdn.example.com/lib.js"
  integrity="sha384-xyz"
  crossorigin="anonymous"
></script>
```

`Si le fichier a été modifié, le navigateur le bloque`
