# Python Cheat-Sheet

## Types

### Déclaration d'une string

- myString = 'mon-texte'

### Déclaration d'un integer

- myInt = 12

### Déclaration d'un float

- myFloat = 9.8

### Vérfication d'un Type de variable

- myType = type('mon-texte')
- myType = type(maVariable)

### Modifictaion d'un type de variable

- float(1) => 1.0
- int(1.3) => 1
- str(1) => '1'

### Déclarer un commentaire

- ''' Premier
commentaire'''
- #Deuxième commentaire

## Conditions

if A > B :
    print('A plus grand que B')
elif A== B :
    print ('A égal à B')
else :
    print ('A plus petit que B')

## Pandas

import pandas as pd

### consulter les 5 premières lignes

- data.head(5)

### moyenne

- mean = data[column].mean()

### median

- median = data[column].median()

### valeur la plus représentée du jeu de data

- mode = data[column].mode()

Attention : utilisé avec distplot, les valeurs sont regroupées, le mode sera visuellement faux puisque sur une valeur unique

Il faut changer le display pour afficher les valeurs uniques :

- nbValDif = len(data[column].unique())
- sns.distplot(list(data[column]), bins=nbValDif)
- plt = axvline(float(mode), color='y')

### variance

- variance = data[column].var()

### écart-type (standard deviation)

racine carrée de la variance

- ecartType = data[column].std()

- ou variance**(1/2)

### coefficient d'asymétrie

Fait réf à l'asymétrie des données

- skew = data[column].skew()

### coefficient d'applatissement d'une distribution (kurtosis)

- kurtosis = data[column].kurtosis()

## Charts

from matplotlib import pyplot as plt

import seaborn as sns

## SQL

### Connexion

import sqlite3

path = 'C:\\Users\\omal\\Downloads\\python\\cours_sql\\sf-bay-area-bike-share/database.sqlite'

conn = sqlite3.connect(path)

import pandas as pd

query = pd.read_sql("""[query]""", conn)

list(query.columns) => Voir la liste des colonnes retournées

len(query.columns) => nombre de colonnes retournées

### Avoir des infos sur une table

- infos = pd.read_sql("""PRAGMA table_info([nomde la table]);""", conn)

### liste des tables

- tables = pd.read_sql("""SELECT *
                        FROM sqlite_master
                        Where types='table';""", conn)

## statistiques

### Statistique descriptive

#### Les variables catégorielles

#### Les variables quantitatives
