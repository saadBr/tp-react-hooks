# TP React Hooks - Application de Gestion de Produits

Ce TP a pour objectif de mettre en pratique l'utilisation des Hooks React (useState, useEffect, useContext) ainsi que la création de Hooks personnalisés.

## Installation et configuration initiale

1. Cloner le dépôt :
```bash
git clone https://github.com/pr-daaif/tp-react-hooks.git
cd tp-react-hooks
```
![1](images/1.png)

2. Créer votre propre dépôt sur Github et changer le remote :
```bash
# Supprimer le remote origine
git remote remove origin

# Ajouter votre nouveau remote
git remote add origin https://github.com/[votre-username]/tp-react-hooks.git

# Premier push
git push -u origin main
```
![2](images/2.png)
3. Installer les dépendances :
```bash
npm install
```
![3](images/3.png)

4. Lancer l'application :
```bash
npm start
```
![4](images/4.png)

## Instructions pour le TP

Pour chaque exercice :
1. Lisez attentivement l'énoncé
2. Implémentez la solution
3. Testez votre implémentation (pensez à faire des copies d'écran)
4. Mettez à jour la section correspondante dans ce README avec :
   - Une brève explication de votre solution
   - Des captures d'écran montrant le fonctionnement
   - Les difficultés rencontrées et comment vous les avez résolues
5. Commitez vos changements avec un message descriptif

### Exercice 1 : État et Effets 
#### Objectif : Implémenter une recherche en temps réel

- [ ] 1.1 Modifier le composant ProductSearch pour utiliser la recherche
      Mise à jour du composant ProductSearch pour permettre à l'utilisateur de saisir un terme de recherche. 
      Le terme de recherche est transmis du composant enfant ProductSearch au composant parent App via les props. 
      Utilisation de la fonction onChange sur l'élément <input> pour mettre à jour la valeur du searchTerm à chaque modification du champ.
- [ ] 1.2 Implémenter le debounce sur la recherche
      Implementation debounce pour retarder l'execution de la mise à jour de l'état searchItem après un delai de 1s, pour éviter déclenchement de la rechercher pour chaque caractère saisi.
- [ ] 1.3 Documenter votre solution ici
      - Modification du composant ProductSearch : Le composant ProductSearch permet de saisir un terme de recherche. La valeur du champ de recherche est synchronisée avec l'état searchTerm du parent via les props. Chaque changement dans le champ met à jour cet état.
      -Implémentation du debounce avec setTimeout : Pour éviter de déclencher une recherche trop fréquemment, j'ai implémenté un mécanisme de debounce dans ProductSearch. Chaque fois que l'utilisateur saisit un terme, un setTimeout est lancé pour attendre 1s avant de mettre à jour le terme de recherche. Si un autre caractère est saisi avant la fin du délai, le setTimeout précédent est annulé et un nouveau délai commence.
      -Utilisation de clearTimeout : Cette logique permet d'annuler le précédent délai à chaque modification dans le champ de recherche, garantissant ainsi que la recherche ne se déclenche que lorsque l'utilisateur cesse de taper pendant un certain temps.
_Votre réponse pour l'exercice 1 :_
```
Code dans ProductSearch :
debouncedSearchTerm : Un état local est utilisé pour conserver temporairement le terme de recherche pendant que l'utilisateur tape.
useEffect : Lorsqu'un utilisateur tape quelque chose, un setTimeout est mis en place. Si l'utilisateur continue à taper, l'ancien setTimeout est annulé, et un nouveau est créé. Cela garantit que la mise à jour du terme de recherche dans le composant parent n'a lieu qu'après une période d'inactivité de 1 seconde.
clearTimeout : Cette fonction est utilisée pour annuler les appels précédents et éviter que plusieurs recherches soient effectuées pendant que l'utilisateur tape.
ProductList
Le composant ProductList affiche les produits filtrés en fonction du terme de recherche. La recherche est effectuée sur le titre du produit, et seuls les produits dont le titre contient le terme de recherche sont affichés.

Code dans ProductList :
Filtrage des produits : Le tableau des produits est filtré en fonction du searchTerm passé par le composant parent (App).

Code dans App :
État searchTerm : Le terme de recherche est stocké dans l'état global (searchTerm) et est passé comme prop aux composants ProductSearch et ProductList.

```
Expliquez votre solution ici
1.2 
1.3
[Ajoutez vos captures d'écran]
Recherche fonctionne après la modification du ProdcutSearch.
![1.1](images/1.1.png)

Etat de recherche avec debounce juste après l'insertion : 
![1.2](images/1.2 before.png)
Etat de recherche avec debounce après 1 second : 
![1.2](images/1.2 after.png)



### Exercice 2 : Context et Internationalisation
#### Objectif : Gérer les préférences de langue

- [ ] 2.1 Créer le LanguageContext
- [ ] 2.2 Ajouter le sélecteur de langue
- [ ] 2.3 Documenter votre solution ici

_Votre réponse pour l'exercice 2 :_
```
Expliquez votre solution ici
[Ajoutez vos captures d'écran]
```

### Exercice 3 : Hooks Personnalisés
#### Objectif : Créer des hooks réutilisables

- [ ] 3.1 Créer le hook useDebounce
- [ ] 3.2 Créer le hook useLocalStorage
- [ ] 3.3 Documenter votre solution ici

_Votre réponse pour l'exercice 3 :_
```
Expliquez votre solution ici
[Ajoutez vos captures d'écran]
```

### Exercice 4 : Gestion Asynchrone et Pagination
#### Objectif : Gérer le chargement et la pagination

- [ ] 4.1 Ajouter le bouton de rechargement
- [ ] 4.2 Implémenter la pagination
- [ ] 4.3 Documenter votre solution ici

_Votre réponse pour l'exercice 4 :_
```
Expliquez votre solution ici
[Ajoutez vos captures d'écran]
```

## Rendu

- Ajoutez l'URL de votre dépôt Github dans  **Classroom** et envoyer la réponse dès le démarage de votre projet.
- Les push doivent se faire au fûr et à mesure que vous avancez dans votre projet.
- Le README.md doit être à jour avec vos réponses et captures d'écran. 
- Chaques exercice doit faire l'objet d'au moins un commit avec un message mentionnant le numéro de l'exercice.