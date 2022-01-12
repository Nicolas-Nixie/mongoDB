# mongoDB
TP individuel MongoDB

### Sommaire

- 1 : Mise en place de la base de donnée
- 2 : Les premieres commandes mongo
- 3 : Les opérateurs
- 4 : Les données GéoJson
- 5 : Les agragateurs

## 1 : Mise en place de la base de donnée

### Etape 1

Dans un premier temps Nous avons créer le projets sur Atlas mongo puis nous avons attribué les permissions

![1](https://user-images.githubusercontent.com/63167717/148780501-720cc1cc-e972-4ec7-9c6f-0bc0a77d3087.JPG)

### Etape 2

Ensuite nous avons créer la collection

![2](https://user-images.githubusercontent.com/63167717/148780746-c4d37de2-c6f7-4f4b-bde9-f4e0ab05a1e0.JPG)

### Etape 3

Nous avons choisi le deployement

![3](https://user-images.githubusercontent.com/63167717/148780900-7e3c0e6d-cf3b-4526-bbdf-b3f402d61243.JPG)

### Etape 4

Nous avons deployé la collection grâce a AWS

![4](https://user-images.githubusercontent.com/63167717/148780993-96ab6522-76c4-4d56-ab73-37c16e8ba7cc.JPG)

### Etape 5

Nous avons ajouté un user a la collection 

![5](https://user-images.githubusercontent.com/63167717/148781591-a2513d69-4fc6-4720-80f7-f2c16c03d9b0.JPG)

### Etape 6

Le cluster s'est alors créé

![6](https://user-images.githubusercontent.com/63167717/148781816-2cc74e5d-02e8-4843-95d6-76752ab76422.JPG)

### Etape 7

Ensuite chacun d'entre nous a connecté Compase localement a Atlas

![7](https://user-images.githubusercontent.com/63167717/148781927-feae2f97-34ed-4fd2-abe5-3a2643edb6e9.JPG)

### Etape 8

Nous avons importé les tables dans la collection restaurants en ligne de commande

![8](https://user-images.githubusercontent.com/63167717/148782166-33ae6381-93b9-4310-8e4e-8c86cf3c75bf.JPG)

Et le resultat s'es't affiché

![9](https://user-images.githubusercontent.com/63167717/148782222-ad9ef1a5-9da0-46cd-9069-2d5b6640d904.JPG)

### 2 : Les premieres commandes mongo

Créeation d'un index pour trier les villes par codes postal, le but étant de trier pour pouvoir identifier les zones de chalandise et faire un publipostage ou une campagne de mailing avec une offre pour attirer des client.

![index classement ville cleints](https://user-images.githubusercontent.com/63167717/149179145-fa58c140-5f87-43d9-86ac-3bc70d95d243.png)

Rercherche des clients masculin pour leur faire une offre sur un type de pizza 

```db.clients.find({sexe: "M"})```

![cmd find](https://user-images.githubusercontent.com/63167717/149182049-0e4c4a2c-e59d-4d51-8d90-e5c7b859bcb5.png)

### 3: Les opérateurs
