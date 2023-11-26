<a href="./README.md">Retourner à la racine du repo</a>

> [!NOTE]
> Ce fichier documente la manière dont notre DB est structurée.

## Table `Users` :

- Chaque utilisateur est identifié de manière unique par un `user_UUID`, qui sert de clé primaire.

- Les pseudonymes des utilisateurs (`user_pseudo`) doivent être uniques.

- Les noms d'utilisateur (`username`) doivent également être uniques.

- La date de création de l'utilisateur (`created_at`) est automatiquement enregistrée avec le timestamp par défaut lors de la création.

## Table `Products` :

- Chaque produit est identifié de manière unique par un `product_UUID`, qui sert de clé primaire.

- Les noms de produits (`product_name`) ne doivent pas dépasser 99 caractères.

- Les prix des produits (`product_price`) sont stockés comme des valeurs décimales avec une précision de 10 chiffres au total, dont 2 sont après la virgule.

- Les quantités de produits (`product_quantity`) doivent être des valeurs entières non négatives.

- La date de création (`created_at`) est automatiquement enregistrée avec le timestamp par défaut lors de la création.

- La date de mise à jour (`updated_at`) est automatiquement enregistrée avec le timestamp par défaut lors de la création et est mise à jour à chaque modification.

## Table `Orders` :

- Chaque commande est identifiée de manière unique par un `order_number`, qui sert de clé primaire et est auto-incrémenté.

- Le coût total hors taxe de la commande (`order_total_cost_ht`) est stocké comme une valeur décimale avec une précision de 10 chiffres au total, dont 2 sont après la virgule.

- La quantité totale de produits dans la commande (`order_total_quantity`) doit être une valeur entière non négative.

- La date de création de la commande (`created_at`) est automatiquement enregistrée avec le timestamp par défaut lors de la création.

- Chaque commande est associée à un utilisateur via la clé étrangère `user_UUID` qui référence la table `Users`.

## Table `belong` :

- La table `belong` relie les produits et les commandes.

- Chaque enregistrement est identifié par la paire (`product_UUID`, `order_number`), qui sert de clé primaire.

- Le `product_UUID` fait référence à la table `Products`.

- Le `order_number` fait référence à la table `Orders`.
