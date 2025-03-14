# Le HSTS

---

Le HSTS (HTTP Strict Transport Security) est un mécanisme de **sécurité** qui permet à un site web d'imposer l'utilisation exclusive du protocole **HTTPS**, empêchant ainsi les connexions non sécurisées en HTTP.

# Comment fonctionne HSTS ?

Lorsqu'un utilisateur accède à un site web avec HSTS activé, le serveur envoie un en-tête HTTP spécial :

```lua
Strict-Transport-Security: max-age=31536000; includeSubDomains; preload
```

# Ce que ca signifie :

- <code> max-age=31536000 </code> : La durée (en secondes) pendant laquelle le navigateur doit forcer HTTPS (ici, 1 an).
- <code> includeSubDomains </code> : Applique la règle à tous les sous-domaines du site.
- <code> preload </code> : Permet d'ajouter le site à une liste de préchargement utilisée par les navigateurs pour forcer HTTPS dès la première visite.

# Pourquoi utiliser HSTS ?

- Evite les attaques de type _man-in-the-middle_ en bloquant le passage en HTTP.
- Corrige les erreurs de configuration (ex : un utilisateur tapant "http://site.com" est redirigé immédiatement vers HTTPS.)
- Protège contre le SSL _stripping_, une attaque qui force un site sécurisé à fonctionner en HTTP.

# Précaution à prendre !

- Une fois HSTS activé, il est impossible d'accèder au site en HTTP, même en cas de mauvais certificat SSL. Il faut donc s'assurer que le site HTTPS fonctionne parfaitement avant d'activer HSTS.
