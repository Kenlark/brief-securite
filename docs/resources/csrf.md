# CSRF

---

Une attaque CSRF force un utilisateur à exécuter une action non souhaitée sur un site web où il est **authentifié**

## Fonctionnement de l'attaque

1. L'utilisateur est connecté à sa banque (`bank.com`)
2. Il visite un site malveillant contenant ce code :

```html
<img src="https://bank.com/transfer?amount=1000&to=hacker" />
```

3. Le navigateur envoie **automatiquement** la requête (avec les cookies de session).
4. La banque ne détecte pas l'attaque et effectue le virement.

## Protection CSRF

- Ajouter un **jeton CSRF** (token unique dans les requêtes).
- Exiger une **confirmation utilisateur** (ex : re-saisie du mot de passe).
