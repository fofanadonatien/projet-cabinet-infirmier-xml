# 🏥 Projet Cabinet Infirmier

## 📌 Présentation

Ce projet universitaire (L3 MIAGE – Grenoble) vise à **modéliser et manipuler les données d’un cabinet infirmier**.
L’objectif est de construire progressivement une application capable de :

* représenter un cabinet, ses infirmiers et ses patients,
* gérer les visites et actes médicaux (NGAP),
* valider et transformer les données (XML, XSD, XSLT),
* préparer l’exploitation par une application C# (validation, parsing, sérialisation, serveur HTTP, etc.).

---

## ✅ Ce qui est déjà fait

* Commencer la modélisation UML avec PlantUML.
* Création des premiers fichiers XML et XSD :

  * `cabinet.xsd` (structure du cabinet, infirmiers, patients, visites).
  * `cabinet.xml` (première instance XML du cabinet et de patients).
  * `ngap.xml` (liste des actes infirmiers et nomenclature NGAP fournie par le prof).
  * `actes.xsd` (schéma des actes NGAP – version à revoir pour plus de cohérence).
* Début de validation des fichiers XML ↔ XSD.
* Organisation de l’arborescence du projet (`data/xml`, `data/xsd`).
* Vérifier la **cohérence du schéma `actes.xsd`** avec l’exemple `ngap.xml` fourni par le professeur.


---

## 🚧 En cours


  ⚠️ Certains choix de types et contraintes sont encore à ajuster (ex. attributs `coef`, `clé`, références croisées `id`).
* Compléter `cabinet.xml` avec les patients demandés dans l’énoncé (Orouge Elvire, Pien Oscare, Kapoëtla Xavier).
* Vérification stricte des numéros de sécurité sociale (regex et cohérence avec la date de naissance).

---

## 📅 À faire

* Finaliser `cabinet.xsd` avec :

  * contraintes d’unicité (`xs:unique`) pour les identifiants infirmiers/patients,
  * contraintes d’existence (`xs:key` / `xs:keyref`) pour lier infirmiers ↔ patients ↔ visites.
* Écrire les transformations XSLT :

  * Page HTML des visites d’une infirmière,
  * Fiche patient XML + fiche patient HTML.
* Mettre en place la validation en C# (`XMLUtils.ValidateXmlFileAsync`).
* Utiliser XPath et DOM pour vérifier certaines conditions (ex. 3 infirmiers, adresses complètes, NSS valides).
* Sérialisation en C# des classes `Adresse`, `Infirmier`, `Patient`, `Cabinet`.
* Génération des factures (HTML/JS).

---

## 📝 Notes importantes pour l’équipe

* ⚠️ **Revoir attentivement le schéma `actes.xsd`** : le prof a fourni un `ngap.xml` et une structure type, il faut s’assurer que notre schéma correspond bien.
* Respecter les **noms de fichiers exacts** :

  * `cabinet.xsd`, `cabinet.xml`, `actes.xsd`, `ngap.xml`.
* Respecter les namespaces :

  * Cabinet : `http://www.univ-grenoble-alpes.fr/l3miage/medical`
  * Actes NGAP : `http://www.univ-grenoble-alpes.fr/l3miage/actes`
* Organisation du projet :

  ```
  projet-cabinet/
  ├── data/
  │   ├── xml/
  │   │   ├── cabinet.xml
  │   │   └── ngap.xml
  │   └── xsd/ en cours juste revoir
  │       ├── cabinet.xsd
  │       └── actes.xsd
  ├── xslt/  l'etape à faire
  │   ├── infirmier.xsl   
  │   └── patient.xsl
  ├── js/
  │   └── facture.js
  └── README.md
  ```

---

## 👥 Travail collaboratif

* Utiliser des **branches** pour chaque fonctionnalité (ex. `feature-xslt`, `fix-actes-xsd`). j'ai pas fait
* Créer une **Pull Request** avant de fusionner sur `main` ou `master`
* Lister les tâches sous forme d’**Issues GitHub** pour suivre l’avancée.

---
