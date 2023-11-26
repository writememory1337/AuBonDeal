<a href="./README.md">Retourner à la racine du repo</a>

> [!NOTE]
> Ce fichier gère les droits de chaque utilisateur sur la DB.

## Création des rôles

```sql
CREATE ROLE global LOGIN NOCREATEDB NOSUPERUSER;
CREATE ROLE gestion_utilisateurs LOGIN NOCREATEROLE NOCREATEDB NOSUPERUSER;
CREATE ROLE gestion_produits LOGIN NOCREATEROLE NOCREATEDB NOSUPERUSER;
CREATE ROLE gestion_commandes LOGIN NOCREATEROLE NOCREATEDB NOSUPERUSER;
```

## Attribution des autorisations sur les tables

```sql
-- Pour le rôle global
GRANT SELECT, INSERT, UPDATE, DELETE ON users, products, orders, products_orders TO global;

-- Pour le rôle gestion_utilisateurs
GRANT SELECT, INSERT, UPDATE, DELETE ON users TO gestion_utilisateurs;

-- Pour le rôle gestion_produits
GRANT SELECT, INSERT, UPDATE, DELETE ON products TO gestion_produits;

-- Pour le rôle gestion_commandes
GRANT SELECT, INSERT, UPDATE, DELETE ON orders, products_orders TO gestion_commandes;
```
