# CORS

---

CORS (Cross-Origin Resource Sharing) est un mécanisme de sécurité permettant à un site web d'accéder à des ressources d'un **autre domaine**, tout en protégeant contre certaines attaques.

## Problème que CORS résout

Par défaut, un site web ne peut pas faire de requêtes AJAX\* vers un **domaine différent** à cause de la **Same-Origin Policy** ([SOP]())

# Exemple

Un site `siteA.com` essaie de récupérer des données d'une API sur `api.siteB.com`. Si `siteB` n'autorise pas `siteA` dans ses en-têtes CORS, la requête sera bloquée.

- Solution côté serveur :

```html
Access-Control-Allow-Origin: https://siteA.com
```

- Exemple d'erreur CORS courante dans la console navigateur :

```html
Access to fetch at 'https://api.siteB.com' from origin 'https://siteA.com' has
been blocked by CORS policy.
```

_\* Une requête AJAX (Asynchronous JavaScript and XML) est une technique qui permet à une page web de communiquer avec un serveur sans nécessiter de rechargement complet de la page_
