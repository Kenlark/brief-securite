# RBAC

---

## Role-Based Access Control

Le RBAC (contrôle d'accès basé sur les rôles), est un modèle de gestion des accès qui restreint l'accès aux ressources d'un système en fonction des rôles des utilisateurs. Au lieu d'attribuer des permissions directement aux utilisateurs, celles-ci sont accordées à des rôles, qui sont ensuite attribués aux utilisateurs.

📌 Principes du RBAC :

1. Rôles → Un rôle représente un ensemble de permissions (ex : "Admin", "Manager", "Employé").
2. Utilisateurs → Chaque utilisateur se voit attribuer un ou plusieurs rôles.
3. Permissions → Les permissions définissent les actions qu’un rôle peut exécuter (ex : lecture, écriture, suppression).
4. Séparation des responsabilités → On évite qu'un même utilisateur ait trop de privilèges en séparant les rôles critiques.

✅ Avantages du RBAC :

- écurité renforcée en limitant l’accès aux informations sensibles.
- Gestion simplifiée des accès en affectant des rôles plutôt que des permissions individuelles.
- Conformité aux réglementations (RGPD, HIPAA, etc.) grâce à un contrôle clair des accès.
- Flexibilité en ajustant facilement les permissions par rôle.

🔥 Exemple concret :
Dans un système de gestion RH :

- Un Employé peut consulter ses propres fiches de paie.
- Un Manager peut consulter les fiches de paie de son équipe.
- Un Administrateur peut gérer tous les comptes et modifier les fiches de paie.
