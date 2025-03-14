# SQLi

---

Une attaque **SQL Injection** consiste à insérer du code SQL malveillant dans un champ utilisateur pour manipuler une base de données.

## Fonctionnement de l'attaque

Imaginons un site vulnérable avec cette requête SQL :

```sql
SELECT * FROM users WHERE username = '$input'
```

Si un hacker entre `admin' OR '1'='1`, la requête devient :

```sql
SELECT * FROM users WHERE  username = 'admin' OR '1'='1'
```

**Effet : L'attaquant accède à tous les comptes**.

## Protection contre SQLi

- Utiliser des requêtes préparées :

```javascript
import mysql from "mysql2";

const db = mysql.createConnection({
  host: "localhost",
  user: "root",
  password: "",
  database: "testdb",
});

// Requête préparée
const query = "SELECT * FROM users WHERE username = ?";

// Exécution avec un paramètre sécurisé
db.query(query, [username], (err, result) => {
  if (err) throw err;
  console.log(result);
});
```
