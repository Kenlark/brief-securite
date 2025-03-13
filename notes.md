# Convention de lecture :

- R- : Recommandation alternative de premier niveau
- R : Recommandation à l'état de l'art
- R+ : Recpmmandation renforcée

# Liste et description des acronymes : (voir 2.2 (p.10) pour certains détails)

- **API** : Application Programming Interface
- **CDN** : Content Delivery Network
- **CMS** : Content Management System
- **CORS** : Cross-Origin Resource Sharing
- **CSP** : Content Security Policy
- **CSRF** : Cross-Site Request Forgery
- **CSS** : Cascading Style Sheets
- **CT** : Certificate Transparency
- **DOM** : Document Object Model
- **ECMA** : European association for standardizing information and communication systems
- **ES6** : ECMAScript6
- **FTP** : File Transfer Protocol
- **HSTS** : HTTP Strict Transport Security
- **HTML** : HyperText Markup Language
- **HTTP** : HyperText Transfer Protocol
- **HTTPS** : HTTP Secure
- **JSON** : JavaScript Object Notation
- **JSON-P** : JSON with Padding
- **REST** : REpresentational State Transfer
- **RGPD** : Règlement Général sur la Protection des Données
- **SOP** : Same-Origin Policy
- **SQL** : Structured Query Language
- **SQLi** : SQL Injection
- **SRI** : Subresource Integrity
- **TCP** : Transmission Control Protocol
- **TLD** : Top-Level Domain
- **TLS** : Transport Layer Security
- **URL** : Uniform Resource Locator
- **XHR** : XMLHttpRequest
- **XML** : Extensible Markup Language
- **XSS** : Cross-Site Scripting

# Menaces les plus courantes :

- La compromission des ressources applicatives (p9)
- Le vol des données (p9)
- Le déni de service (DDoS) (p9)

# 1. Introduction :

- Pourquoi sécuriser une application web ?

  - De plus en plus de cyberattaques sur les applications web.
  - Règlementation et conformité (RGPD, NIS2...)

- Objectifs du document :
  - Proposer une stratégie de sécurité couvrant tout le cycle de vie du développement.
  - Protéger toutes les couches de l'application : back-end; front-end, base de données.

# 2. Cycle de vie du développement & sécurité :

- Les phases du développement et leurs vulnérabilités :

  - Conception -> Mauvaise architecture = Vulnérabilités intégrées
  - Développement -> Mauvaises pratiques = bugs exploitables
  - Tests & validation -> Manque de tests de sécurité = failles non détectées
  - Déploiement -> Mauvaise configuration = portes ouvertes aux attaques

- Exemple d'attaque sur chaque phase :

  - Développement -> Injection SQL via une mauvaise gestion de requêtes
  - Déploiement -> Clés API dans le code, fuite sur GitHub

- Comment contrer ça ? :
  - Analyse des risques en amont
  - Intégration des tests de sécurité
