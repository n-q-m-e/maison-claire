# Guide : Configurer Google Sheets pour le formulaire Maison Claire

## Objectif
Chaque demande de devis envoyée via le formulaire sera automatiquement ajoutée dans un Google Sheet. Cela permet à David d'avoir un tableau de suivi de toutes les demandes.

---

## Étape 1 — Créer le Google Sheet

1. Se connecter à **Google Drive** avec le compte `maisonclairedebarras@gmail.com`
2. Aller sur **https://sheets.google.com/**
3. Cliquer sur **"+ Nouvelle feuille de calcul"**
4. Renommer la feuille en **"Demandes de devis — Maison Claire"**
5. En **ligne 1**, écrire ces en-têtes dans les colonnes A à H :

| A | B | C | D | E | F | G | H |
|---|---|---|---|---|---|---|---|
| Date | Nom | Prénom | Téléphone | Email | Département | Type de bien | Description |

6. (Optionnel) Mettre la ligne 1 en **gras** et figer la première ligne (Affichage > Figer > 1 ligne)

---

## Étape 2 — Créer le Google Apps Script

1. Dans le Google Sheet, aller dans **Extensions > Apps Script**
2. Un éditeur de code s'ouvre dans un nouvel onglet
3. **Supprimer tout** le code par défaut (`function myFunction() { }`)
4. **Coller** ce code :

```javascript
function doPost(e) {
  var sheet = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();
  var data = JSON.parse(e.postData.contents);
  sheet.appendRow([
    data.date,
    data.nom,
    data.prenom,
    data.telephone,
    data.email,
    data.departement,
    data.type_bien,
    data.description
  ]);
  return ContentService.createTextOutput('OK');
}
```

5. Cliquer sur **💾 Enregistrer** (ou Ctrl+S)
6. Donner un nom au projet si demandé (ex: "Formulaire Devis")

---

## Étape 3 — Déployer l'application web

1. Cliquer sur **Déployer > Nouveau déploiement** (bouton bleu en haut à droite)
2. À côté de "Sélectionner un type", cliquer sur la **roue dentée ⚙️**
3. Sélectionner **"Application Web"**
4. Remplir les champs :
   - **Description** : `Formulaire devis Maison Claire`
   - **Exécuter en tant que** : `Moi (maisonclairedebarras@gmail.com)`
   - **Qui a accès** : `Tout le monde`
5. Cliquer sur **Déployer**

### Autorisation
- Google va demander d'autoriser l'accès → cliquer sur **"Examiner les autorisations"**
- Sélectionner le compte Google
- Si un message "Cette application n'est pas validée" apparaît :
  - Cliquer sur **"Paramètres avancés"** (en bas à gauche)
  - Cliquer sur **"Accéder à Formulaire Devis (non sécurisé)"**
- Cliquer sur **"Autoriser"**

### Récupérer l'URL
- Une fois déployé, une **URL** s'affiche (du type `https://script.google.com/macros/s/XXXXXX/exec`)
- **Copier cette URL** — c'est l'URL à mettre dans le code du site

---

## Étape 4 — Insérer l'URL dans le code du site

Dans le fichier `index.html`, trouver cette ligne (vers la ligne 1532) :

```javascript
const GOOGLE_SHEETS_URL = 'A_REMPLACER';
```

Remplacer `A_REMPLACER` par l'URL copiée :

```javascript
const GOOGLE_SHEETS_URL = 'https://script.google.com/macros/s/XXXXXX/exec';
```

---

## Étape 5 — Tester

1. Ouvrir le site dans un navigateur
2. Remplir le formulaire avec des données de test
3. Cliquer sur "Envoyer ma demande de devis"
4. Vérifier :
   - ✅ Message de succès vert affiché sur le site
   - ✅ Email de notification reçu par David
   - ✅ Email de confirmation reçu à l'adresse test
   - ✅ Nouvelle ligne ajoutée dans le Google Sheet

---

## Dépannage

### Le Google Sheet ne reçoit pas les données
- Vérifier que l'URL est bien copiée dans `GOOGLE_SHEETS_URL`
- Vérifier que le déploiement est en accès "Tout le monde"
- Ouvrir la console du navigateur (F12) et regarder les erreurs

### Modifier le script après déploiement
- Si tu modifies le code dans Apps Script, il faut **re-déployer** :
  - Déployer > Gérer les déploiements > Modifier (crayon) > Nouvelle version > Déployer
  - L'URL reste la même

### Limites
- Google Apps Script : 20 000 requêtes/jour (largement suffisant)
- Pas de limite sur le nombre de lignes dans le Google Sheet
