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

Les opérateur permettent de traiter les informations contenus dans les documents 

Exemple :
```db.restaurants.find({"restaurant_id" : { $eq : "40356442" }})```

Cet opérateur $eq, permmet de conmparer l'égalité ainsi que le type. Cette commande affichera donc les "restaurant_id" correspondant a la valeur et au type "40356442"

```{ 
  _id: ObjectId("61dc0fa2350e86d7efb69f39"),
  address: {
    building: '2206',
    coord: [ -74.1377286, 40.6119572 ],
    street: 'Victory Boulevard',
    zipcode: '10314' 
  },
  borough: 'Staten Island',
  cuisine: 'Jewish/Kosher',
  grades:[
     { date: 2014-10-06T00:00:00.000Z, grade: 'A', score: 9 },
     { date: 2014-05-20T00:00:00.000Z, grade: 'A', score: 12 },
     { date: 2013-04-04T00:00:00.000Z, grade: 'A', score: 12 },
     { date: 2012-01-24T00:00:00.000Z, grade: 'A', score: 9 } 
  ],
  name: 'Kosher Island',
  restaurant_id: '40356442' 
}```

Plusieur opérateur peuvent être juxtaposer aux seins de la même requete 

Exemple :

```db.restaurants.find({"restaurant_id" : { $eq : "40364296" }, "borough": { $eq : "Bronx"}})```

La premiere partie de la commande aura la même fonction que la précedente, nous filtrerons la recherche en plus avec l'arrondissement ("borought") du "Bronx"

```  _id: ObjectId("61dc0fa2350e86d7efb69f6b"),
  address: {
    building: '277',
    coord: [ -73.8941893, 40.8634684 ],
    street: 'East Kingsbridge Road',
    zipcode: '10458' 
  },
  borough: 'Bronx',
  cuisine: 'Chinese',
  grades:[
     { date: 2014-03-03T00:00:00.000Z, grade: 'A', score: 10 },
     { date: 2013-09-26T00:00:00.000Z, grade: 'A', score: 10 },
     { date: 2013-03-19T00:00:00.000Z, grade: 'A', score: 10 },
     { date: 2012-08-29T00:00:00.000Z, grade: 'A', score: 11 },
     { date: 2011-08-17T00:00:00.000Z, grade: 'A', score: 13 } 
  ],
  name: 'Happy Garden',
  restaurant_id: '40364296' 
}```
