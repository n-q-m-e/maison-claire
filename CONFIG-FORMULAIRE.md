# Configuration du formulaire de contact — Maison Claire

## Résumé

Le formulaire de devis du site envoie automatiquement :
1. **Un email de notification** à maisonclairedebarras@gmail.com (pour David)
2. **Un email de confirmation** au client (s'il a renseigné son email)
3. **Les données dans un Google Sheet** pour le suivi (à configurer)

---

## EmailJS — Configuration

- **Compte** : maisonclairedebarras@gmail.com
- **Plan** : Gratuit (200 emails/mois)
- **Public Key** : `x4F1PFaRfSkZXVVv5`
- **Service ID** : `service_vi7js7g` (Gmail)

### Templates

| Template | ID | Rôle |
|---|---|---|
| Notification devis | `template_l1ykr6m` | Envoyé à David quand un client fait une demande |
| Confirmation client | `template_6zmd6me` | Envoyé au client pour confirmer la réception |

### Fichiers de référence (templates HTML)
- `emailjs-template.html` — Template notification devis
- `emailjs-template-confirmation-client.html` — Template confirmation client

### Settings des templates

**Notification devis (template_l1ykr6m)**
- To Email : `maisonclairedebarras@gmail.com`
- From Name : `Maison Claire Devis`
- From Email : Default
- Reply To : `{{email}}`

**Confirmation client (template_6zmd6me)**
- To Email : `{{email}}`
- From Name : `Maison Claire`
- From Email : Default
- Reply To : email de David

---

## Code du site (index.html)

### Variables de configuration (dans le script en bas de page)
```javascript
const EMAILJS_PUBLIC_KEY = 'x4F1PFaRfSkZXVVv5';
const EMAILJS_SERVICE_ID = 'service_vi7js7g';
const EMAILJS_TEMPLATE_ID = 'template_l1ykr6m';    // Notification
const EMAILJS_TEMPLATE_CLIENT = 'template_6zmd6me'; // Confirmation client
const GOOGLE_SHEETS_URL = 'A_REMPLACER';             // À configurer
```

### Champs du formulaire
| Champ | name | Requis |
|---|---|---|
| Nom | `nom` | Oui |
| Prénom | `prenom` | Oui |
| Téléphone | `telephone` | Oui |
| Email | `email` | Non |
| Département | `departement` | Oui |
| Type de bien | `type_bien` | Oui |
| Description | `description` | Non |

### Fonctionnement
1. Le client remplit le formulaire et clique "Envoyer"
2. Le bouton passe en état "Envoi en cours..."
3. EmailJS envoie la notification à David
4. Si le client a mis son email → envoi de la confirmation client
5. Les données sont envoyées au Google Sheet (à configurer)
6. Message de succès vert ou d'erreur rouge affiché sous le bouton

---

## Logos hébergés (imgbb)

| Image | URL directe |
|---|---|
| Logo sans fond (PNG) | `https://i.ibb.co/WN09rGF2/logo-sans-fond.png` |
| Logo complet (JPG) | `https://i.ibb.co/sdV4SqF1/logo.jpg` |

---

## Reste à faire
- [ ] Configurer Google Sheets + Apps Script (voir GUIDE-GOOGLE-SHEETS.md)
- [ ] Insérer l'URL Google Sheets dans le code
- [ ] Tester le formulaire complet en conditions réelles
