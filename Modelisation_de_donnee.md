# Modélisation de données

## 1. Créer un dépot git :
- Ouvrir un terminal 
- taper :
```sh
git init
```
Cette commande va initialiser un dépot Git, Git va traquer toutes les modification.

## 2. Utiliser Git :

- Ajouter un fichier a mon dépot git
````sh
git add <fichier>
````
- Sauvegarder mon dépot
````sh
git commit -m "message de commit"
````

## 3. Merise :


Merise est une méthode de modélisation de données. Elle permet de représenter les données d'un système d'information.Merise est un acronyme de : Méthode d'Etude et de Réalisation Informatique pour les Systèmes d'Entrepryse.

#### Présentation générale :
Cette méthode se caracterise par trois points clés : 
- une approche dite systèmique : on transforme les processus de l'entreprise en système d'information 
- une séparation des données et des traitements
- une approche nivelée

    ![Alt text](image-1.png)

Le systeme de pilotage : 
- il est composé de l'ensemble des acteurs qui vont **piloter** le système d'information  

le système d'information :
- il est composé de l'ensemble des acteurs qui vont **utiliser** le système d'information

Le système operant : 
- Il est composé de l'ensemble des acteurs qui vont **produire** les données du système d'information

### Séparation des données et des traitements 


La séparation des données et des traitements permet de séparer les données du système d'information et les traitements effectués sur ces données. 
Cette démarche se fait en 3 étapes :
- L'analyse des flux : on annalyse les flux de d'informations entre les acteurs du système d'information et les acteurs du système opérant
- L'étude des documents interne (factures, bon de livraison etc...)
- L'étude des documents externes (fournisseurs, clients etc...)


Les différents types d'informations : 

- les infos de bases ou élémentaires : ce sont les données de base du système d'information 
- les infos calculées : ce sont les données calculées a partir des données de base 
- les traitements ou les fonctions : ce sont les traitements effectués sur les données de base pour obtenir les données calculées 

**En Résumé :** vous devres identifier les données et les traitements efféctués sur ces derniers.

### l'approche nivelée

Pour effectuer la conception d'un SI, on va utiliser une approche nivelée. Cette approche se compose de 4 niveaux :

- le niveau conceptuel
- le niveau organisationnel
- le niveau logique 
- le niveau physique

#### **Le niveau conceptuel :**

Le niveau conceptuel permet de moéliser les données de l'entreprise. On va utiliser le modèle conceptuel de données MCD pour modéliser les données de l'entreprise, et le MCT pour modéliser les traitements effectués sur ces données.

#### **Le niveau organisationnel :**

Le niveau organisationnel va permettre d'integrer a l'analyse précédente toutes les notions de temporalité, de chronologie des opérations, de contrainte géographique. On va utilser le modele organisationnel des traitements "MOT" et le modèle organisationnel des données "MOD" pour modéliser les traitements de l'entreprise.

En resumé on se pose les questions suivantes a partir des données recueillies au niveau conceptuel :

- **Quand** les traitements sont-ils effectuées ?
- **Où** les traitements sont-ils effectuées ?
- Par **qui** les traitements sont-ils effectués ?

#### **Le niveau Logique**

Le niveau logique va permettre de modéliser les données de l'entreprise en utilisatn le modèle logique de données "MLD" et les traitements de l'entreprise en utilisant le modèle logique des traitement"MLT"

Le MLD et indépendant des languages de programmation et des SGBD 

On répond a la qjestion : **avec quoi** les traitements sont-ils effectuées

#### **Le niveau physique**

Il s'agit de l'organisation `réelle` des données. On va utiliser le modèles physiques de données "MPD" et le modèle physique des traitments "MPT". 

Ici, on apporte les solutions techniques de stockage des données.

On repond a la question: **Comment** les traitements sont-ils efféctuées ?

#### **Résumée des 4 niveaux**
![Alt text](image-2.png)

### Des données aux dépendances fonctionnelles : 

Pour etre intégrées dans un système d'information , les données doivent être triées et organisées. On va souvent tenter de les classer par type de données : 

- chaines de caractères, format texte
- type alphanumérique, format texte
- le type numérique (intégrer, float...)
- le type date (date, datetime, timestamp)
- logique ou bouléen (true, false)

Création d'un dictionnaire de données :

![Alt text](image-3-1.png)
<br>
### Les dépendances fonctionnelles 
<br>

Une Dépendances fonctionnelles est une relation entre deux awttributs d'une table. Elle permet de definir une relation de dépendance entre deux attributs d'une table.

Le role d'une dépendance fonctionnelle est de permettre de définir une relation de dépendance entre deux attributs d'une table: une donnée A depend fonctionnellement d'une donnée B lorsque la valeur de B détermine la valeur de A (par un calcul ou autre)

Pour formaliser une dépendance fonctionnelle on utilise la notation suivante : `Numero adherent (Nom, prenom, code postal, ville, telephone, date d'adhesion, mail)`

La partie gauche (numéro adherent) est la `source` de la dépendance fonctionnelle.
La partie droite désigne le `but` de la dépendance 

### Les dépendances fonctionnelles composées 

Si une dependance fonctionnelle qui fait intervenir plus de deux attributs on parle de dépendance fonctionnelle comporsée

Exemple: pour connaitre le temps d'un coureur sur une etape donnée il nous faut son numéro, son nom ainsi que le nom ou le numéro de l'étape

Formalisation :
`(numero coureur, numero etape)  (temps)`

### Les dépendances fonctionnelles élémentaires

une dépendance fonctionnelle A -> B est élémentaire s'il n'existe pas une donnée C, sous-ensemble de A, decrivant une dépendance fonctionnelle
type C -> B

Exemples : 
 - RefProduit -> LibelleProduit
 - NumCommande RefProduit -> QuantiteCommandee
 - <strike> NumCommande RefProduite -> DesignationProduit </strike>

 ### Les dépendances fonctionnelles élémentaires directes


Exemple : 
- RefPromo -> NumApprenant
- NumApprenant -> NomApprenant
- RefPromo -> NomAprrenant : RefPromo -> NumApprenant -> NomApprenant  

### Sujet TP/TD MCD jour 1

![Alt text](image-14.png) ![Alt text](image-5-1.png) ![Alt text](image-6-1.png) ![Alt text](image-7-1.png)



<br>

### **Exercice :**

Le but de l'exercice est d'élaborer un MCD a partir d'un dictionnaire de données. 

### Réponse exo : 
![Alt text](TP_MCD_MENU.png)

Ici on va introduire les notions d'entités, de relations et de propriétés. 

 #### Les propriétés sont les informations de bases d'un SI (système d'information). 

![Alt text](image-10-1.png) 

#### Les entités sont les objets du SI.

![Alt text](image-8-1.png) 

Quelques définitions :
 - entité forte : une entité qui ne dépend pas d'une autre entité pour exister
 - entité faible : une entité qui dépend d'une autre entité pour exister 

#### Les relations

![Alt text](image-9-1.png)

#### Les relations "porteuses"

Une relation est dite porteuse si elle possede des propriétés
img 15
img 16

#### Les relations reflexives

une relation est dite reflexive si elle relie une entité 

**Les cardinalités :** elles permettent de définir le nombre d'occurences d'une entité par rapport a une autre entité dans le cadre d'une relation. 

Petit exemple sur la cardinalité :
![Alt text](image-11-1.png) ![Alt text](image-12-1.png) ![Alt text](image-13-1.png)

**Quelques règles de conceptions :**

- Toutes les entitées doivent avoir un identifiant
- Toutes les propriétés dépendent fonctionnellement de l'identifiant
- le nom d'une propriété ne doit apparaitre q'une seule fois dans le MCD ; si vous avez une entité Eleve et une entité Proffesseur par exemple pour un nom d'une table proffesseur il faudra l'appeler NomProffesseur.
- Les propriétés issues d'un calcul ne doivent pas apparaitre dans le MCD

### Installation d'AnalyseSI 

- Installation de Java
- Installation d'AnalyseSI

### **Les Contraintes d'intégrité fonctionnelle (CIF)**
Definition: Une CIF est définie par le fait qu'une des entités de l'association est completement determineée par la connaissance d'une ou de plusieur entités particiapant a l'association.

Exemple : 
![Alt text](image-18.png)

Une salle peut contenir 0 ou plusieurs ordinateurs. un ordinateur, lui existe dans une seule salle.
Dans ce type de relation une CIF existe si on a une cardinalité 1,1

## Modele Logique des données (MLD)

Le MLD est la suite du processus Merise, on se rapproche un peut plus de la base de données. 

### Cas simple

Partons du MCD suivant : 

![Alt text](image-19.png)

Nous arrivons au MLD suivant : 
![Alt text](image-20.png)

L'`entité` qui possede la cardinalité 1,1 ou 0,1 absorbe l'identifiant de l'entité la plus forte (0,n ou 1,n). Cet identifiant devient alors une clé étrangère. 

### Cas (0,n), (0,n) ou (1,n), (1,n)

Parton du MCD suivant 

![Alt text](image-21.png)

Dans le cas ou la `cardinalité max` est n des deux coté, on crée une entité intermédiaire qui va contenir les deux clés étrangères des deux entités 

![Alt text](image-22.png)

Continuons avec le MCD suivant :

![Alt text](image-23.png)

On optient le MLD suivant en suivant la meme logique : 

![Alt text](image-24.png)

### Cas d'une relation reflexive 

Partons du MCD suivant :

![Alt text](image-25.png)

on obtient le MLD suivant : 

![Alt text](image-26.png)

## Regle de passage du MCD au MLD 

Règles simples de passage du MCD au MLD
L’entité qui possède la cardinalité maximale égale à 1 recevra l’identifiant ou les identifiants des entités ayant les cardinalités maximales les plus fortes.

Les relations ayant toutes leurs entités reliées avec des cardinalités maximales supérieures à 1 se transformeront en entité en absorbant les identifiants des entités jointes.

Toute relation porteuse de propriétés se transformera en entité et absorbera comme clé étrangère les identifiants des entités qui lui sont liées.

Toute relation réflexive se transformera en entité et absorbera comme clé étrangère l’identifiant de l’entité qui lui est liée.

### Exercice Pratique

Passage MLD / MCD

Voici le MCD :

![Alt text](image-27.png)

Voici mon MLD : 

![Alt text](CONVERT_MCD_MLD.png)

Voici le MLD (corrigé) :

![Alt text](image-28.png)

### Modele physique de données 

Voici le schema relationnel correspondant au MLD precedent :

Diplômes (Diplomes)

Possède (#NumEmployé, #Diplôme, Date d’obtention)

Employés (NumEmployé, Nom, Prénom, Adresse, Code Postal, Ville, Téléphone)

Tables (NumTable, Capacité)

Date (Date)

Service (TypeService, Désignation)

Boissons Diverses (NumBoissons, Désignation, Prix de vente)

Contenir (#NumCommande, #NumBoissons, Quantité)

Commande (NumCommande, #Numemployé, #Date, #TypeService, #NumTable)

Comprend (#NumMenu, #NumCommande, Quantité)

Menus (NumMenu, Libellé, Prix de vente)

Constitué (#NumMenu, #NumPlat)

Constituer (#NumCommande, #NumPlat, Quantité)

Sélectionner (#NumCommande, #NumVin, Quantité)

Carte des vins (NumVin, Nom du vin, Millesime, Prix de vente)

Carte des plats (NumPlat, LibelléPlat, Prix de vente, #NumType)

Type des plats (NumType, Désignation)

Bouteilles (NumBouteille, Date Achat, Prix d’achat, # NumVin, #NumViticulteur)

Viticulteur (NumViticulteur, Nom viticulteur, Prénom viticulteur, Adresse viticulteur, Code postal, Ville, Téléphone)

A partir d'ici il est facile de generer le script SQL correspondant.

```SQL
CREATE TABLE CARTE_DES_VINS
   (
   NUMVIN INTEGER(2) NOT NULL ,
   NOM_DU_VIN CHAR(40)   ,
   MILLESIME INTEGER(2)  ,
   PRIX_DE_VENTE REAL(5,2)
,
    PRIMARY KEY (NUMVIN) CONSTRAINT PK_CARTE_DES_VINS
   );

CREATE TABLE BOUTEILLES
   (
   NUMVITICULTEUR INTEGER(2) NOT NULL ,
   NUMVIN INTEGER(2) NOT NULL ,
   NUMBOUTEILLE INTEGER(2) NOT NULL ,
   DATE_ACHAT DATE(8) ,
   PRIX_D_ACHAT REAL(5,2)
,
    PRIMARY KEY (NUMVITICULTEUR, NUMVIN, NUMBOUTEILLE) CONSTRAINT
PK_BOUTEILLES
   );


CREATE TABLE VITICULTEUR
   (
   NUMVITICULTEUR INTEGER(2) NOT NULL ,
   NOM_VITICULTEUR CHAR(20) ,
   PRÉNOM_VITICULTEUR CHAR(20) ,
   ADRESSE_VITICULTEUR CHAR(40) ,
   CODE_POSTAL CHAR(5) ,
   VILLE CHAR(40) ,
   TÉLÉPHONE CHAR(15)
,
    PRIMARY KEY (NUMVITICULTEUR) CONSTRAINT PK_VITICULTEUR
   );
```

### **Exercices 19/07 après-midi :**

Ennoncés dans /Exercice 19072023

#### **Exercice 1 :**

Voici mon MCD : 

![Alt text](MCD_EXO1.png)

Voici mon MLD :

![Alt text](EXO1_MLD.png)

Voici mon MPD :

![Alt text](EXO1_MPD.png)

Voici Mon schéma relationnel : 

`Type_ (id_type_Type_, type_libelle_Type_)  Commande (id_commande_Commande, poid_Commande, prix_Vente_Commande)  Produits (id_produits_Produits, produits_libellés_Produits, Prix_kg_Produits, id_type_Type_)  contient (id_produits_Produits, id_commande_Commande, quantité_contient)`

#### **Exercice 2 :**

Voici le MLD que j'ai recréée en rétroingiénérant :

![Alt text](EXO2_MLD.png)

Voici le MCD que j'en ai déduit :

![Alt text](EXO2_MCD.png)

### Les Formes normales (FN)

Ensemble de regles qui a pour but d'éviter les anomalies au sein des BDDR. 
Pour appliquer les concepts des formes normales il est necessaire de connaitre les trois premières formes normales.

### Forme normale 1 (1FN)

Une relation est en première forme normale si : 
- tous les attributs sont atomiques 
- les attributs ne contiennent pas de valeurs répétitives 

Exemple : 
clients (NumCli, Nom, Prenom, Adresse, Telephone)

![Alt text](image-29.png)

 ![Alt text](image-30.png) 


### Forme normale 2 (2FN)

Une relation est en deuxième forme normale si :
- Elle est en 1FN
- Si elle a tous les attributs qui ne sont pas des clés ne dépendent pas d'une partie de la clé primaire 

Exemple : 

Commande (NumClient, CodeArticle, Date,QteCommande, Designation)

![Alt text](image-31.png)

 ![Alt text](image-32.png)

### Forme normale 3 (3FN)

Une relation est en troisème forme normale si : 

- Elle est en deuxième forme normale 
- Si toutes les dépendances fonctionelles sont directes 

Les attributs non clés primmaire ne dépendent pas d'un attribut non clé primmaire 

Exemple : 

Commande (NumCommande, #CodeClient, #RefArticle)

![Alt text](image-34.png)


### Les diagrammes des flux

Les diagrammes des flux permettent de modéliser les flux d'informations entre les acteurs du systeme d'information et les acteurs du systeme operant.

Quelques definitions:

- Domaine d'etude: le perimetre d'une activite au sein d'une entreprise, d'une activite specifique
- L'acteur: une personne, un service, une entreprise, un systeme informatique qui intervient dans le domaine d'etude au moyen d'un flux d'information
- les flux: les informations qui circulent entre les acteurs, represente par une fleche et porte un nom et peut etre numerote (par soucis de chronologie)

Representation graphique :

![Alt text](image-35.png)

Quelques regles a respecter :

- un flux ne peut pas etre bidirectionnel
- un flux ne doit pas etre reflexif
- on ne represente pas les flux entre les acteurs externes 

## UML 

UML:  Unified Modeling Language(language de modélisation unifié) est un langage de modelisation de données. UML a été normalisé en 1997 par L'OMG (object Management Group). Son but est de mettre en forme les concepts orientés objets au travers de diagramme. 

### Analogie Merise / UML 

1. Cas du MCD et du diagramme des classes

Ont peut comparé certaine structure Du modèle Merise au modèle UML

UML est un language graphique.

MCD : img 36

Diaggrame des classes : img 37

Les cardinalité sont au sens opposée au MCD 

Représentation d'une relation 

img 38

### Exercice 3 :
Dictionnaire de données :
- Client

	   ID_Client 
	   Nom_Client
	   Prénom_Client
	   Adresse_cl
      Ville_cl
      cp_client
	   Tel_client

- Materiel

      ID_Materiel
	   lib_materiel

- Intervention

	   ID_Intervention
	   Date_int
	   Heure_Deb_int
	   Heure_Fin_int

- Type

      ID_type
      lib_type
      prix_horaire

- Composant

	   ID_Composant 
	   Nom_Composant 
	   Prix_Composant
      quantité

MCD du logiciel : 

![Alt text](EXO3_MCD.png)

MLD du logiciel :

![Alt text](EXO3_MLD.png)

MPD du logiciel :

![Alt text](EXO3_MPD.png)

shcéma relationel du logiciel :

Clients (ID_client, Nom_client, Prenom_client, Adresse_cl, Ville_cl, cp_client, tel_client) 

Materiels (ID_Materiel, lib_materiel) 

Intervention (ID_intervention, Date_int, Heure_deb_int, Heure_fin_int, #ID_client, #ID_tyoe)

type (ID_tyoe, lib_type, prix_horaire) 

Composants (ID_Composant, Nom_Composant, Prix_Composant) 

Appartient (ID_client, ID_Materiel, quantité_Appartient)  

intervient (ID_intervention ID_Materiel)  

Vend (ID_intervention, ID_Composant, quantité_Vend) 

### Exercice 4 : 

MCD : 

![Alt text](EXO4_MCD.png)

MLD :

![Alt text](EXO4_MLD.png) 

MPD :

Propriété (ID_propriete, Type_Propriété)

Location (ID_location, Type_Location, #client_id_client)  

Client (ID_client, CP_maison, prenom_client, tel_client)

Maison (ID_maison, Adresse_maison, Ville_maison, CP_maison, #propriété_id_propriete, #location_id_location)  
 
Possede (ID_propriete, ID_client)
