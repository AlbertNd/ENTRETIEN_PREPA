# Creation d'un dashboard 

### Importation des données 
1. **Aceuil** 
    - Obtenir des données 
        - Choisir l'extension du fichier 
            - Ici c'est un fichier CSV
                - ***On ouvre un fichier à la foie***
        - Ouvrir
            1. On a un apercu des données.
            2. Charger
                - Charger les donnée directement dans Power Bi 
            3. Transformer les données 
                - Transformer les données pour etre sur qu'elles sont correctement reconnu par Power BI
                - Nettoyage de donnée 
                - Ajout de colone 
                - Etc ... 
        - **Transformer les données**
            - Vue de l'editeur Power Query 
                - Si bon fichier: 
                    - Les en-tete sont directement reconnu 
                        - Voir a droit **ETAPES APPLIQUEES** :les etpes que Power BI a effectué automatiquement
                        - Pour voir l'etat initial : Dans etapes Appliquées => Source
                            - Modifier : Power BI a modifier le type de certain colonne
                                - Par exemple la colonne ID qui de base etait de type texte et qu'il a mis en type nombre 
                    - **NB: Bien parcourir les donnée pour voir si c'est ce qui est souhaité**
                    - **Changement de type**
                        - Iconne à gauche de l'en-tete de la colonne concernée
                            - **Ajouter une nouvelle étape**
                        - **Dans le choix du mobre**: Faire attention au separateur sinon erreur 
                            - Le separateur dans Power BI est une virgule **,** et non un point "."
                                - Selection de la colonne 
                                    - Click droit 
                                        - **Remplacer les valeurs**
        - **Chargement des autres fichier en rapport et ainsi suite ....**
            - ***NB ici il y a pas de choix on click sur ok et on tomber directement dans l'editeur Power Query***
2. **Aceuil**
    - **Fermer et appliquer**
        - Les données sont chargées dans Power BI 
            - Volet à droite **Champs**
                - Les source de données 
                    - Les different champs

### Traitement de fusion des source dans Power BI 
- Volet à gauche 
    - Onglet : **Modele**
        - Lien créer automatiquement ***(Car Power BI reconnait la simularité des identifiants)***
            - C'est confugurer par defaut dans les option Power BI 
                - Fichier 
                    - Options et paramettres 
                        - Options 
                            - Chargement des données 
                                - Detection 
                                    - .....
        - Possibilité de modifier ou de les liens.
            - Supprimer : click droit sur le lien 
            - Creation : Drag and drop 
    - Onglet : **Donnée**
        - Pour revenir sur les données 
            - Click droit sur la table 
                - Modifier la requete 
                    - Ouverture de l'editeur Power Query. 

### Création de dashBoard 
- Volet à gauche 
    - Onglet : **Rapport**
        - ***Se poser les question du type de consommateur du rapport avant de le créer***
1. **Affichage du quadrillage**
    - Afficher 
        - Zone option de page
            - **Cocher Quadrillage**
    - **Pour une bonne pratique**
        - Nommer la page
        - Arriere plan gris, transparance 0%
        - Tout d'abord commencer par le cadre generale, la ou on va place les elements, le graphique que l'on veut y place etc ... 
            - prendre des formers
                - Onglet **insertion**
                    - Formes 
                        - Mise en forme 
                            - Former 
                                - Style ....
                        - Disposer les forme a l'aide des cales
                            - [Voir demo](https://www.youtube.com/watch?v=_P2m9GZvBh4) 
2. **Insertion des element du rapport**
    - **Titre** 
        - Onglet Aceuil : Zone insert **Zone de texte**
            - Proposition de mise en forme 
    - **Segment** ou **Slicer (en anglais)**
        - Volet visualisattion (à droite) 
            - **Segement** (***C'est un filtre qui adapte l'ensemble des tableau***) 
                - Click dessus et il est injecter automatiquement dans le board
                    - **Pour les donnée on choche le champs souhaité**
                - Lorsque les donnée sont continues 
                    - il y a un slider de niveau 
                - Lorsque les donnée sont de type discretes
                    - Il y a soit un style deroulant ou liste a cocher
                        - Chois sur l'iconne de fleche vers le bas dans le cadre
    - **Les visuelles**
        - **Carte**
            - Activer le visuel de la carte 
                - fichier 
                    - Option et paramettre 
                        - Options 
                            - Global 
                                - securité 
                                    - Visuels de la carte et de carte remplis 
            - Prealablement travailler les donnée 
                - On click sur le champs ***Pas chocher***
                    - Apparition de deux nouvels onglets **Outils de table** et **Outils de colonne**
                        - **Outils de colonne**
                            - Cotegorie de donnée : Localité
                                - Permet d'indiqu"e qu'il sagit q'une ville 
            - Création de hierarchie 
                - Permet de dire que telle element appartient a telle autre elemement (exemple ville et etat)
                    - Voir les trois point à droite du champs 
                        - **Créer une hierarchie**
                    - Choix du deuxieme champs et 
                        - **Ajouter une hierarchie**
                - Possibilité de changer de niveau de hierarchie 
                    - voir fleche avec intercection ...
            - Cocher la hierarchie souhaité dans la carte (Option recommander).
                - Pour le nombre de par etat 
                    - deplace le champs convainable (exemple les ID) dans  **Taille** 
                        - Les bulle seront grande en fonction du nombres des id present dans l'etat (la localité) 
                - Pour le pourcentage :
                    - Voir le champs placé dans **taille**
                        - La fleche vers le bas 
                            - Afficher la valeur comme 
                                - Pourcentage du total général.        
            - Drag and drop la hierarchie dans **Emplacement** (Volet visualisation)  
            - **Changer le style de la carte**
                - Voir onglet de mise en forme du visuel (dans volet visualisation)
                    - Carte thermique 
        - **table**
            - Permet de montrer differentes informations dans un tableau 
            - Click sur la visualisation table 
                - choix des information souhaité dans la table
        - **Carte 123** Pour avoir le nombre d'une selection   
            - Volet visualisation carte 
                - Choix de l'id 
                    - Dans champs de la visualisation 
                        - Fleche vers le bas du choix choisi
                            - Nombre element distinct
        - **Graph a bar empilée**   
            - Permet par exemple de voir lequele produite le plus de .....
            - Volet visualisation 
                - Choix graphique empilée 
                    - Choix des données des axes 
3. Ajout de bordure 

[Voir doc pour type autre type de visualisarion](https://docs.microsoft.com/fr-fr/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#visualizations-in-power-bi)

4. Nomination de la page 

### Enregistrement et publication 
- **Enregistrement**
    - Fichier 
        - Enregistrer sous 
            - Format PBIX
- **Publication**
    - Se connecter (Un compte pro)
        - Fichier 
            - Publier 
                - Publier sur Power BI 
                    - Par defaut : on click sur mon espace de travail
                        - **Ouvrir ..... dans Power BI**
        
