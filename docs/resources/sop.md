# SOP

---

La Same-Origin Policy (SOP) est une règle de sécurité qui empêche une page web de faire des requêtes vers un autre domaine **sans autorisation explicite**. Elle est implémentée par les navigateurs pour protéger les utilisateurs contre les attaques de type **vol de données** ou **exécutionn de scripts malveillants**.

## Définition d'une "origin"

Une origin est définie par trois éléments :

1. Le protocole (`http`/`https`)
2. Le nom de domaine (`example.com`)
3. Le port (`:443` pour HTTPS, `:80` pour HTTP)

Deux URL ont **la même orgine si et seulement si** ces trois éléments sont identiques.

## Exemple

- Même origine

  - `https://example.com/page1.html`
  - `https://example.com/page2.html`

- Origine différente
  - `http://example.com/page1.html` (**http &ne; https**)
  - `http://sub.example.com/page1.html` (**sub.example.com &ne; example.com**)
  - `http://sub.example.com:8080/page1.html` (**port 8080 &ne; 443**)

## Conséquence

Un script exécuté sur `https://example.com` **ne peut accèder** aux données de `https://sub.example.com`.

## Problème causés par la SOP

Bien que la **SOP** améliore la sécurité, elle pose aussi des restrictions gênantes.

Exemple typique : un site veut récupérer des données d'une API externe.

```javascript
fetch("https://api.autresite.com/data")
  .then((response) => response.json())
  .then((data) => console.log(data));
```

### Erreur bloquée par la SOP

```html
Access to fetch at 'https://api.autresite.com/data' from origin
'https://monsite.com' has been blocked by CORS policy.
```

## Contournement de la SOP avec CORS

Solution: l'API doit activer CORS

Si `api.autresite.com` souhaite autoriser `monsite.com` à accéder à ses données, il doit inclure cet en-tête HTTP :

```html
Access-Control-Allow-Origin: https://monsite.com
```

Ou pour autoriser tout le monde (**déconseillé**) :

```html
Access-Control-Allow-Origin: *
```

## Exploitation de la SOP par les attaques XSS

Si un site est **vulnérable au XSS**, un attaquant peut **injecter du JavaScript** qui contourne la SOP.

### Comment éviter ça ?

- Éviter les vulnérabilités XSS (valider et échapper toutes les entrées utilisateur).
- Mettre en place des en-têtes de sécurité (**CSP, SRI**)

## Conclusion

La Same-Origin Policy (SOP) est une protection essentielle contre le vol de données et l’exécution de scripts malveillants.
Cependant, elle nécessite des ajustements comme CORS pour permettre certaines interactions légitimes entre sites.
