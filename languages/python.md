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

