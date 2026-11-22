# 🌳 CKOALA

Application Java de recherche dans des arbres de typologies à partir de caractéristiques observées, avec intégration continue, tests automatisés et rapport de couverture (https://aminenakrou.github.io/ckoala-recherche-typologies/).

## Auteur

**Amine Nakrou**

---

## Présentation du projet

Ce dépôt contient le cœur de l’application **CKOALA**, un outil qui permet de rechercher dans des arbres de typologies en fonction de caractéristiques définies dans un fichier XML.

Le principe du projet est simple :

- une typologie est décrite dans un fichier XML ;
- cette typologie est chargée dans l’application ;
- l’utilisateur fournit une observation ;
- l’application retourne les catégories compatibles avec cette observation.

Ce projet met en œuvre :
- la modélisation orientée objet en Java ;
- la manipulation de fichiers XML ;
- la classification d’observations selon des caractéristiques ;
- la validation du code via des tests et une chaîne CI/CD.

---

## Fonctionnement général

Une typologie est chargée depuis un fichier XML dans la classe `Typologie`.

Cette typologie est composée de plusieurs éléments :
- `Categorie` pour représenter les catégories de l’arbre ;
- `Caracteristique` pour représenter les attributs ;
- `Domaine` pour représenter les domaines de valeurs ;
- `Observation` pour représenter les données fournies par l’utilisateur.

L’application compare ensuite une observation avec les catégories disponibles afin de déterminer les catégories compatibles.

---

## Fichiers XML utilisables

Le projet peut utiliser les fichiers suivants :

- `arbres.xml`
- `nuages.xml`

Il est aussi possible d’utiliser un autre fichier XML personnel, à condition qu’il respecte la même structure que ceux attendus par l’application.

---

## Technologies utilisées

- **Java 17**
- **JUnit** pour les tests
- **JaCoCo** pour la couverture du code
- **Checkstyle** pour l’analyse statique du style
- **PMD CPD** pour la détection de duplications
- **GitLab CI/CD**
- **GitHub Actions**
- **GitHub Pages** pour publier les rapports

---

## Compiler et lancer

Prérequis : Java 17 (JDK).

```bash
javac -d out src/*.java
java -cp out Main nuages.xml     # ou arbres.xml, ou un autre fichier XML
```

Les tests unitaires (`tests/`) utilisent JUnit 5.

---

## Structure du dépôt

```bash
.
├── .github/workflows/static.yml   # Publication du site sur GitHub Pages
├── src/                           # Code source Java (Main, Typologie, Categorie, ...)
├── tests/                         # Tests unitaires JUnit
├── arbres.xml                     # Exemple de typologie
├── nuages.xml                     # Exemple de typologie (fichier par défaut)
├── checkstyle.xml                 # Règles de style
├── index.html                     # Site du projet
├── CONTRIBUTING.md
└── README.md
```
