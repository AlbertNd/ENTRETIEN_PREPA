# Créer des rapport paginés 
- Les rapports paginés permettent aux développeurs de rapports de créer des artefacts Power BI ayant des exigences de rendu étroitement contrôlées. 
    - Les rapports paginés sont idéaux pour créer:
        - Des factures de ventes, 
        - Des reçus, 
        - Des bons de commande 
        - Des données tabulaires. 
- Les rapports paginés offrent une vue en pixel parfait des données. 
    - Le pixel parfait signifie que on a un contrôle total sur le mode de rendu du rapport. 
        - *Si on souhaite un pied de page sur chaque reçu de vente qu'on crée, un rapport paginé est la solution appropriée.*
        - *Si on souhaite qu’un certain nom de client apparaisse toujours en vert dans un rapport, on peut le faire dans un rapport paginé.*

```
Les rapports paginés Power BI sont des descendants de SQL Server Reporting Services (SSRS), Les rapports paginés Power BI
et SSRS ont beaucoup de choses en commun. 
Si on recherche des informations sur des rapports paginés, la recherche sur Internet et dans la documentation Microsoft 
sur SSRS est une excellente idée, car on y trouvere de nombreux billets de blog, vidéos et documentation.
```
![](https://learn.microsoft.com/fr-fr/training/modules/create-paginated-reports-power-bi/media/04-power-bi-report-builder-ssm.png)

- On peut utiliser des rapports paginés pour des rapports opérationnels avec des tables de détails et des en-têtes et pieds de page facultatifs.
- utiliser des rapports paginés lorsque on prévoit d’imprimer le rapport sur un papier ou lorsque on souhaite recevoir un reçu électronique, un bon de commande ou une facture. 
    - Les rapports paginés affichent également les données tabulaires plus facilement. On peut avoir des ordres de tri personnalisés, des en-têtes interactifs et des URL dans les résultats, ce qui permet une intégration simple avec les applications personnalisées.
- Les rapports paginés Power BI peuvent également afficher toutes les données dans un seul élément de rapport, tel qu’une table. 
    - Si on a 25 000 enregistrements et que on souhaite que les rapports s’impriment sur 100 pages, on peut le faire. 
    - Si on souhaite imprimer chaque troisième enregistrement avec un arrière-plan rose clair, on peut également le faire.
- **Les rapports paginés Power BI ne sont pas créés dans Power BI Desktop ; ils sont générés à l’aide du Générateur de rapports Power BI.** 
    - ***Les rapports paginés Power BI sont une fonctionnalité de Power BI Premium.***

#### Obtenir des données

