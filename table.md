<a href="./README.md">Retourner à la racine du repo</a>

> [!NOTE]
> Les spécificités de chaque table sont indiquées sous le bloc de code


```SQL
DROP TABLE IF EXISTS products_orders;
DROP TABLE IF EXISTS orders;
DROP TABLE IF EXISTS users;
DROP TABLE IF EXISTS products;
```
`DROP TABLE IF EXISTS` -> suppression des tables respectives si elles existent.

```SQL
CREATE TABLE Users (
    user_UUID UUID PRIMARY KEY,
    user_pseudo VARCHAR(99) UNIQUE,
    username VARCHAR(99) UNIQUE,
    user_password VARCHAR (99),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

```
`user_UUID` -> clé primaire de type `UUID` et qui identifie de manière unique chacune des colonnes de la table.

```SQL
CREATE TABLE Products (
    product_UUID UUID PRIMARY KEY,
    product_name VARCHAR(99),
    product_description TEXT,
    product_price DECIMAL(10, 2) CHECK (product_price) >= 0 
    product_quantity INT  CHECK (product_quantity) >= 0,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
    CONSTRAINT chk_dates CHECK (created_at < updated_at)
);
```
`product_price` -> Utilisation du type `DECIMAL` pour les valeurs monétaires: `DECIMAL(précision, chiffres à droite de la virgule)`

```SQL
CREATE TABLE Orders (
    order_number SERIAL PRIMARY KEY,
    order_total_cost_ht DECIMAL(10, 2),
    order_total_quantity INT CHECK (order_total_quantity >= 0),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    delivered_at TIMESTAMP,
    CONSTRAINT chk_dates CHECK (created_at < delivered_at),
    user_UUID UUID REFERENCES Users(user_UUID)  -- Clé étrangère vers la table Users
);
```
 `order_number` -> Utilisation du type `SERIAL` pour une clé primaire auto-incrémentée

```SQL
CREATE TABLE belong (
    product_UUID UUID REFERENCES Products(product_UUID),
    order_number SERIAL REFERENCES Orders(order_number),
    PRIMARY KEY (product_UUID, order_number)
);

```
`REFERENCES Products(product_UUID)` -> définit une clé étrangère, indiquant que la colonne `product_UUID` fait référence à la colonne `product_UUID` de la table "Products".
