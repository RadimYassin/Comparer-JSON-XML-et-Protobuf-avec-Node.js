
 <img width="1560" height="268" alt="Screenshot 2025-11-22 111952" src="https://github.com/user-attachments/assets/6a79c10f-e4a4-4e80-acb0-338c41a3cad8" />

 <img width="948" height="479" alt="image" src="https://github.com/user-attachments/assets/9be275dc-2492-4ff6-8ea2-ee7bec528abe" />

 # Comparaison JSON vs XML vs Protobuf avec Node.js

Ce projet est un laboratoire pratique pour comparer trois formats de sérialisation de données populaires : **JSON**, **XML** et **Protocol Buffers (Protobuf)**.

L'objectif est de générer les mêmes données (une liste d'employés) dans ces trois formats et de comparer la taille des fichiers résultants ainsi que la complexité de mise en œuvre.

## 📋 Prérequis

- Node.js installé sur votre machine.

## 🚀 Installation

1.  Clonez ce dépôt ou téléchargez les fichiers.
2.  Ouvrez un terminal dans le dossier du projet.
3.  Installez les dépendances nécessaires :

```bash
npm install
```

Ceci installera :
- `xml-js` : Pour la conversion JSON vers XML.
- `protobufjs` : Pour l'utilisation de Protocol Buffers avec Node.js.

## 🛠️ Utilisation

### 1. Génération des fichiers et comparaison

Lancez le script principal pour créer les fichiers de données et afficher leurs tailles :

```bash
node index.js
```

**Résultat attendu :**
Le script va créer trois fichiers à la racine :
- `data.json`
- `data.xml`
- `data.proto`

Et afficher un comparatif de taille dans la console, par exemple :
```text
Taille de 'data.json' : 127 octets
Taille de 'data.xml'  : 224 octets
Taille de 'data.proto': 41 octets
```
*Note : Les tailles peuvent varier légèrement selon les options de formatage choisies.*

### 2. Vérification du décodage Protobuf

Comme le fichier `data.proto` est binaire et illisible par un éditeur de texte classique, un script de test est fourni pour vérifier qu'il peut être relu correctement.

```bash
node test_decoding.js
```

Ce script lit le fichier binaire et réaffiche les données sous forme d'objet JavaScript.

## 📂 Structure du projet

- **`index.js`** : Script principal. Crée les données, les sérialise dans les 3 formats, écrit les fichiers et compare les tailles.
- **`employee.proto`** : Définition du schéma de données pour Protocol Buffers.
- **`test_decoding.js`** : Script utilitaire pour tester la lecture du fichier Protobuf généré.
- **`data.*`** : Les fichiers de sortie générés (ne pas modifier manuellement).

## 💡 Observations

- **JSON** : Format texte lisible, standard du web, taille moyenne.
- **XML** : Format texte verbeux (balises ouvrantes/fermantes), taille la plus importante.
- **Protobuf** : Format binaire compact, nécessite un schéma (`.proto`), taille la plus faible (très efficace pour le réseau/stockage).


