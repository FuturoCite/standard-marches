# standard-marches
Il s'agit du standard wallon de publication sous condition Open Data des données relatives aux marchés en Wallonie 

## Contexte

Il existe un besoin d'harmonisation de la publication en open data de données essentielles produites par les administrations publiques wallonnes. En octobre 2022, plus de 660 jeux de données sont publiés sur le portail [Open Data Wallonie Bruxelles (ODWB)](https://www.odwb.be/explore/?sort=modified), qui sont très hétérogènes. 

Constatant la production de jeux de données disparates à l'échelle de la fédération Wallonie-Bruxelles, FuturoCité a réuni, dans le cadre d'un groupe de travail sollicité depuis mai 2021, une vingtaine de collectivités. La concertation de celles-ci a permis 1) d'identifier collectivement des jeux de données jugés prioritaires et 2) de s'accorder sur des spécifications des modèles de données. 
La standardisation de ces données prioritaires est en effet essentielle pour s'assurer de leur publication homogène et de faciliter leur exploitation (notamment leur agrégation) par les réutilisateurs. Elle facilitent l'exploitation des données publiées par les réutilisateurs (agrégation, consolidation et traitements automatiques).

## Construction du schéma de données 

Les membres du groupe de travail ont défini un schéma de données qui décrit le format des fichiers, les différents champs, les valeurs possibles… Ils se sont appuyés sur un état des lieux du patrimoine de données des collectivités wallonnes et sur une étude des modèles utilisés par des collectivités déjà productrices de ces données (notamment Liège et Namur), en prenant en compte les retours faits par les réutilisateurs de données. 

## Description du schéma

Un [gabarit au format tableur](https://github.com/FuturoCite/standard-marches/blob/main/Schéma_marchés_gabarit.xlsx) est également prévu pour faciliter la publication d'un jeu de données conforme au format du schéma.

Un exemple valide au format CSV est consultable [ici](https://github.com/FuturoCite/standard-marches/blob/main/exemple-valide.csv). 

La tableau ci-dessous donne un aperçu des champs du schéma. 

<table>
  <tr>
   <td><strong>Nom</strong>
   </td>
    <td><strong>Remplissage obligatoire/optionnel</strong>
   </td>
   <td><strong>Description</strong>
   </td>
  </tr>
  <tr>
   <td>Identifiant 
   <br>(id)
   </td>
   <td>Obligatoire
   </td>
   <td>Ce champ contient un identifiant unique local. Le producteur de données le génère en associant le code INS de la commune dans laquelle se tient le marché à un nombre. Ce champ permet d'éviter localement les doublons. Le code INS de la commune est accessible ici : <ahref="https://statbel.fgov.be/fr/open-data/code-refnis">https://statbel.fgov.be/fr/open-data/code-refnis</a>
   </td>
  </tr>
  <tr>
   <td>Nom 
   <br>(name)
   </td>
   <td>Obligatoire
   </td>
   <td>Ce champ indique le nom du marché
   </td>
  </tr>
  <tr>
   <td>Description 
   <br>(description)
   </td>
   <td>Obligatoire
   </td>
   <td>Ce champ permet de décrire textuellement le marché
   </td>
  </tr>
  <tr>
   <td>Type 
   <br>(type)
   </td>
   <td>Obligatoire
   </td>
   <td>Ce champ précise le type de marché. Une valeur est possible parmi la liste suivante : Marché hebdomadaire; Marché de Noël; Brocante; Braderie; Marché thématique; Marché provençal; Marché de producteurs locaux; Marché bio; Marché artisanal; Marché aux fleurs; Autre
   </td>
  </tr>
  <tr>
   <td>Photos 
   <br>(pictures)
   </td>
   <td>Optionnel
   </td>
   <td>Ce champ renvoie vers une ou plusieurs photos du marché, grâce à des url. En cas de plusieurs url : elles doivent être séparées par un point virgule.
   </td>
  </tr>  
  <tr>
   <td>Nom de la commune 
   <br>(municipality)
   </td>
    <td>Obligatoire
   </td>
   <td>Ce champ contient le nom de la commune dans laquelle se tient le marché. Le nom de la commune provient de la base de données BeST Address : https://opendata.bosa.be/index.fr.html ou de la liste des codes INS : https://statbel.fgov.be/fr/open-data/code-refnis
   </td>
  </tr>
  <tr>
   <td>Code INS 
   <br>(ins_code)
   </td>
    <td>Obligatoire
   </td>
   <td>Ce champ contient le code INS de la commune où est organisé le marché. Il est accessible ici : https://statbel.fgov.be/fr/open-data/code-refnis
   </td>
  </tr>
  <tr>
   <td>Partie de commune 
   <br>(zone_address)
   </td>
    <td>Optionnel
   </td>
   <td>Ce champ contient le nom de la partie de commune où se tient le marché, conforme à l'appelation dans StatBel :<ahref="https://statbel.fgov.be/fr/propos-de-statbel/methodologie/classifications/geographie">https://statbel.fgov.be/fr/propos-de-statbel/methodologie/classifications/geographie</a>
   </td>
  </tr>
  <tr>
   <td>Code INS de la partie de commune 
   <br>(ins_zone_address)
   </td>
    <td>Optionnel
   </td>
   <td>Ce champ contient le code INS de la partie de commune où se tient le marché. La découpe géographique de StatBel Level 5 (NIS6) liste ces codes :<ahref="https://statbel.fgov.be/fr/propos-de-statbel/methodologie/classifications/geographie">https://statbel.fgov.be/fr/propos-de-statbel/methodologie/classifications/geographie</a>
   </td>
  </tr>
  <tr>
   <td>Nom de rue 
   <br>(street_name)
   </td>
    <td>Optionnel
   </td>
   <td>Ce champ renseigne le nom de la voirie principale où se situe le marché (ou de la voirie la plus proche du marché s'il n'est pas en voirie).
   </td>
  </tr>
  <tr>
   <td>Code rue BeSTAddress 
   <br>(street_number)
   </td>
    <td>Optionnel
   </td>
   <td>Ce champ contient le code de la voirie principale où se tient le marché dans la base de données BeSTAdress (ou de la voirie la plus proche du marché s'il ne se tient pas en voirie) :<ahref="https://opendata.bosa.be/index.fr.html">
https://opendata.bosa.be/index.fr.html</a>
   </td>
  </tr>
  <tr>
   <td>Code rue national 
   <br>(street_number_rrn)
   </td>
    <td>Optionnel
   </td>
   <td>Code de la voirie où se situe le marché dans le registre national (ou de la voirie la plus proche du marché s'il ne se tient pas en voirie)
   </td>
  </tr>
  <tr>
   <td>Numéro de police le plus proche 
   <br>(house_number)
   </td>
    <td>Optionnel 
   </td>
   <td>Ce champ contient le numéro de police (de maison) le plus proche du marché. Dans le cas d'un marché intérieur, mettre le numéro du batiment principal. Si le marché s'étend sur une voirie, nous recommandons d'introduire un numéro central sur cette voirie. Si le marché s'étend sur plusieurs voiries, nous recommandons d'introduire un numéro central sur la voirie retenue pour l'encodage des champs précédents (Nom de rue, Code rue BeSTAddress, Code rue national)
   </td>
  </tr>
  <tr>
   <td>Précisions sur l'emplacement
   <br>(location_details)
   </td>
    <td>Optionnel
   </td>
   <td>Ce champ donne des précisions sur l'emplacement du marché.
   </td>
  </tr>
  <tr>
   <td>Coordonnées 
   <br>(coordinates)
   </td>
    <td>Obligatoire
   </td>
   <td>Ce champ indique les coordonnées du marché. Il respecte le format WGS 1984 (latitude,longitude). Les coordonnées d'un lieu peuvent être générées ici :<ahref="https://www.coordonnees-gps.fr/carte/pays/BE">https://www.coordonnees-gps.fr/carte/pays/BE</a>
   </td>
  </tr>
  <tr>
   <td>Géométrie 
   <br>(geometry)
   </td>
    <td>Optionnel
   </td>
   <td>Ce champ indique les coordonnées de la zone correspondante marché. Il respecte le format WGS 1984 (latitude,longitude). Les coordonnées d'un lieu peuvent être générées ici :<ahref="https://www.coordonnees-gps.fr/carte/pays/BE">https://www.coordonnees-gps.fr/carte/pays/BE</a>
   </td>
  </tr>  
  <tr>
   <td>Contact 
   <br>(contact)
   </td>
    <td>Optionnel
   </td>
   <td>Ce champ donne des informations de contact. Nous recommandons d'indiquer uniquement le site web du marché afin de faciliter la maintenance et la mise à jour des données. 
   </td>
  </tr>
  <tr>
   <td>Accessibilité PMR 
   <br>(disabled_access)
   </td>
    <td>Optionnel
   </td>
   <td>Ce champ indique si le marché est accessible aux PMR ou non. Les valeurs possibles sont true et false.
   </td>
  </tr>
  <tr>
   <td>Horaires 
   <br>(schedule)
   </td>
    <td>Optionnel
   </td>
   <td>Ce champ indique les horaires auxquels le marché est accessible. Il respecte le format proposé par OpenStreetMap (https://wiki.openstreetmap.org/wiki/FR:Key:opening_hours). L'outil YoHours (https://projets.pavie.info/yohours/) permet de générer des horaires au bon format. Le format OSM permet d'indiquer des exceptions pendant certaines périodes (vacances, jours fériés…). Pour les générer au bon format en utilisant YoHours, il suffit de les renseigner en cliquant sur le bouton 'plus' vert, situé en haut à gauche. 
   </td>
  </tr>  
  <tr>
   <td>Date de début
   <br>(begin_date)
   </td>
    <td>Obligatoire
   </td>
   <td>Ce champ indique la date à partir de laquelle ce marché est organisé.
   </td>
  </tr>  
  <tr>
   <td>Date de fin
   <br>(end_date)
   </td>
    <td>Optionnel
   </td>
   <td>Ce champ indique la date jusqu'à laquelle le marché est organisé.
   </td>
  </tr>  
  <tr>
   <td>Couvert
   <br>(covered)
   </td>
    <td>Optionnel
   </td>
   <td>Ce champ indique si le marché est couvert ou non. Les valeurs possibles sont true et false.
   </td>
  </tr>  
  <tr>
   <td>Gestionnaire
   <br>(provider)
   </td>
    <td>Optionnel
   </td>
   <td>Ce champ est recommandé. Il renseigne le gestionnaire du marché.
   </td>
  </tr>  
  <tr>
   <td>Présentation détaillée
   <br>(presentation_url)
   </td>
    <td>Optionnel
   </td>
   <td>Ce champ permet de donner des précisions sur les commerçants habituellement présents sur le marché soit via une localisation sur plan des commerçants (url vers un pdf par exemple), soit via une page web décrivant les commerçants habituellement présents.
   </td>
  </tr>  
  <tr>
   <td>Nombre de vendeurs
   <br>(number_of_stalls)
   </td>
    <td>Optionnel
   </td>
   <td>Ce champ indique le nombre approximatif de vendeurs présents sur le marché. 
   </td>
  </tr>    
  <tr>
   <td>Date de création de la donnée 
   <br>(created_date)
   </td>
    <td>Optionnel (recommandé)
   </td>
   <td>Ce champ indique la date de création de la donnée dans le jeu. Il
respecte le format ISO 8601 : année-mois-jour (YYYY-MM-DD)
   </td>
  </tr>
  <tr>
   <td>Date de dernière modification de la donnée 
   <br>(last_modified_date)
   </td>
    <td>Optionnel (recommandé)
   </td>
   <td>Ce champ indique la date de la dernière modification de la donnée dans le
jeu. Il respecte le format ISO 8601 : année-mois-jour (YYYY-MM-DD).
   </td>
  </tr>
</table>


## Format de fichier 

Le format de fichier retenu pour la publication des données est le CSV (Comma Separated Values, valeurs séparées par des virgules).

Les fichiers doivent, sauf exception et autant que possible, respecter les règles de formatage suivantes :

* l’encodage des caractères est UTF-8,
* le séparateur des colonnes est la virgule,
* le séparateur des nombres décimaux est le point,
* le séparateur de valeurs multiples dans un champ est le point-virgule,
* si un champ contient une virgule, il doit être entouré de guillemets doubles,
* chaque ligne doit avoir le même nombre de champs,
* le type MIME ou Content-Type est text/csv.

### Recommandations pour le nommage des fichiers 

Les fichiers doivent, sauf exception et autant que possible, respecter les règles de nommage suivantes :

* YYYY-MM-DD : Date de création du fichier
* idProducteur : code INS unique de la commune pour identifier le producteur
* marches : nom du fichier, en minuscules non accentuées
* territoire : Nom du territoire concerné, non accentué (exemple : Liege)
* extension : Si les règles de formatage sont respectées, l'extension est .csv

Exemple : 2023-01-25_62063_marches_Liege.csv

### Recommandations pour la mise en conformité 

Ces conseils reprennent ceux du [Socle commun des données locales publié par OpenDataFrance](https://scdl.opendatafrance.net/docs/recommandations-relatives-aux-jeux-de-donnees.html)

Les fichiers doivent comporter :

* Toutes les colonnes, y compris celles dont les cellules ne sont pas renseignées, dans le bon ordre, et avec des en-têtes correctement nommées sur la première ligne (nom correspondant strictement au schéma)
* Autant de lignes que nécessaire comprenant des cellules dont les valeurs peuvent être obligatoires (elles doivent être impérativement renseignées) ou optionnelles (elles sont seulement recommandées ou soumises à condition de disponibilité / pertinence)
