# Changelog — Maison Claire

## [1.2.0] — 2026-02-26

### Ajouté
- **SEO : Balises meta** — description, keywords, Open Graph, Twitter Card
- **SEO : Lien canonique** vers https://www.maisonclairedebarras.com/
- **SEO : Schemas JSON-LD** — LocalBusiness, Service, FAQPage
- **Section FAQ** visible avec accordéon (6 questions/réponses) entre Avis et CTA
- **Lien FAQ** dans la navigation principale
- **sitemap.xml** et **robots.txt** à la racine du projet
- **Preload** de la font Google Fonts + preconnect vers fonts.gstatic.com

### Optimisé
- `loading="lazy"` sur toutes les images sauf logo et hero
- `defer` sur le script EmailJS
- Attributs `alt` enrichis avec mots-clés SEO sur toutes les images

---

## [1.1.0] — 2026-02-25

### Ajouté
- **Formulaire de contact fonctionnel** avec EmailJS
  - Envoi d'un email de notification à David pour chaque demande de devis
  - Envoi d'un email de confirmation automatique au client (si email renseigné)
  - États visuels : bouton "Envoi en cours...", message de succès vert, message d'erreur rouge avec numéro de téléphone
  - Validation des champs obligatoires (Nom, Prénom, Téléphone, Département, Type de bien)

- **Templates email HTML** au style Maison Claire
  - `emailjs-template.html` — Notification devis (envoyé à David)
  - `emailjs-template-confirmation-client.html` — Confirmation client
  - Design : polices Cormorant Garamond + Outfit, couleurs or/charcoal/crème, logo, footer sombre
  - Bordure sable compatible Gmail (remplacement du box-shadow non supporté)

- **Préparation Google Sheets** pour suivi des demandes
  - Code prêt dans index.html (URL à configurer)
  - Guide détaillé dans `GUIDE-GOOGLE-SHEETS.md`

- **Documentation**
  - `CONFIG-FORMULAIRE.md` — Récapitulatif complet de la configuration (clés, templates, champs)
  - `GUIDE-GOOGLE-SHEETS.md` — Guide pas-à-pas pour configurer Google Sheets

### Modifié
- `index.html` — Ajout du SDK EmailJS, attributs `name` sur tous les champs du formulaire, script de soumission, message de feedback

---

## [1.0.0] — 2026-02-25

### Ajouté
- Site vitrine Maison Claire Débarras
- Page unique responsive (HTML/CSS/JS)
- Sections : Hero, Services, Zones d'intervention, Avis, Contact, Footer
- Formulaire de devis (placeholder avec alert)
- Animations scroll reveal
- Navigation sticky avec smooth scroll
- Bouton flottant "Appelez-nous"
