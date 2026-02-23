# Maison Claire Débarras — Roadmap & Améliorations

Analyse concurrentielle réalisée le 23/02/2026 sur 8 sites concurrents (Les Compagnons, Hexa Debarras, DébaRapide, Diogene France, Debarrasseurs Bretons, etc.)

---

## 🔴 CRITIQUE — À faire maintenant

### 1. Section FAQ + Schema FAQPage
- Ajouter 5-8 questions/réponses visibles sur le site
- Questions à couvrir :
  - Combien coûte un débarras ?
  - Le débarras peut-il être gratuit ?
  - Combien de temps dure une intervention ?
  - Que deviennent les objets récupérés ?
  - Intervenez-vous dans tout Paris / IDF ?
  - Comment se passe un débarras après succession ?
- Implémenter le schema JSON-LD `FAQPage` pour les résultats enrichis Google

### 2. Schema markup JSON-LD
- **LocalBusiness** : nom, adresse, téléphone, horaires, coordonnées GPS
- **Service** : type de service, zone, fourchette de prix
- **AggregateRating** : note moyenne + nombre d'avis (étoiles dans Google)
- **FAQPage** : voir point 1
- **BreadcrumbList** : hiérarchie de navigation

### 3. Section Tarifs transparente
- Requête n°1 des gens : "prix débarras m3"
- Afficher des fourchettes indicatives :
  - Studio / duplex (25-60 m²) : 500 – 900 €
  - Appartement (70-100 m²) : 1 200 – 1 800 €
  - Maison (100-150 m²) : 1 600 – 2 500 €
  - Cave / grenier (6-15 m²) : 250 – 700 €
- Expliquer les 3 modèles de prix :
  1. **Débarras gratuit** — la valeur des objets couvre le coût
  2. **Débarras facturé** — le client paie quand les objets ont peu de valeur
  3. **Débarras indemnisé** — l'entreprise paie le client si les objets sont très valorisables

### 4. Meta description + Open Graph
- Balises meta description pour Google
- Balises Open Graph pour le partage sur les réseaux sociaux
- Favicon à créer

---

## 🟡 IMPORTANT — Avantage concurrentiel

### 5. Bouton WhatsApp flottant
- Facile à ajouter, gros impact sur les conversions
- Bouton flottant avec message pré-rempli
- Ex: "Bonjour, je souhaite un devis pour un débarras à [ville]. Merci !"

### 6. Compteurs animés
- Remplacer la trust bar statique par des compteurs animés :
  - +500 interventions réalisées
  - 10+ ans d'expérience
  - 98% de clients satisfaits
  - 48h délai d'intervention

### 7. Galerie Avant/Après
- Quand David aura des photos réelles de chantier
- Slider interactif avant/après (drag handle)
- Ou grille simple côte à côte avec lieu + description

### 8. Upload photos dans le formulaire
- Permettre aux clients de joindre jusqu'à 5-10 photos
- Améliore la précision du devis et le taux de conversion

### 9. Demande de rappel
- Formulaire simplifié : nom, téléphone, créneau préféré
- Moins engageant qu'un formulaire complet → plus de conversions

---

## 🔵 PLUS TARD — Croissance long terme

### 10. Pages dédiées par service
- `/debarras-appartement-paris/`
- `/debarras-maison-paris/`
- `/debarras-cave-grenier/`
- `/debarras-succession/`
- `/nettoyage-diogene/`
- `/debarras-professionnel/`
- Chaque page : 700+ mots uniques, H1 dédié, FAQ, témoignages spécifiques

### 11. Pages par ville / arrondissement (SEO local)
- Une page par département (75, 77, 78, 91, 92, 93, 94, 95)
- Pages pour les villes clés : L'Haÿ-les-Roses, Arcueil, Cachan, Montrouge, Bourg-la-Reine, Sceaux
- Pages par arrondissement de Paris (13e, 14e, 15e en priorité)

### 12. Blog / Conseils
- Articles à écrire :
  - Guide succession : comment organiser un débarras après un décès
  - Syndrome de Diogène : comprendre et intervenir
  - Comment préparer un débarras
  - Guide du recyclage : que deviennent vos meubles ?
  - Estimer le volume de son débarras
  - Débarras gratuit : conditions et explications

### 13. Simulateur de prix interactif
- Modal en 3-5 étapes :
  1. Surface du bien (m²)
  2. Espaces supplémentaires (cave, garage, grenier)
  3. Niveau d'encombrement (normal / encombré / accumulation)
  4. État sanitaire (normal / poussiéreux / insalubre)
  5. Accessibilité (RDC / ascenseur / escaliers étroits)
- Calcul instantané basé sur ~15 €/m² avec modificateurs

### 14. Intégration Google Reviews / Trustpilot
- Remplacer les 3 témoignages statiques par un widget live
- Afficher la note agrégée (ex: 4.8/5 — 50+ avis)
- Lien vers la fiche Google Business

### 15. Logos partenaires
- Si David travaille avec des agences immo (Century 21, Laforêt, etc.), notaires, ou associations (Emmaüs, Secours Populaire)
- Afficher les logos dans une barre dédiée

### 16. Vidéo
- Vidéo courte (1-2 min) de l'équipe en intervention
- Schema VideoObject pour le SEO
- Peut servir de fond hero ou dans la section entreprise

### 17. Espace Pro
- Page dédiée aux gestionnaires d'immeubles, notaires, agences immobilières
- Tarification volume, facturation entreprise

### 18. Mentions légales & RGPD
- Page mentions légales (obligatoire)
- Politique de confidentialité (obligatoire avec formulaire)
- Bandeau cookies

---

## Sites concurrents analysés
- lescompagnonsdebarrasseurs.com — le plus complet, simulateur de prix
- hexadebarras.com — multi-villes, intégration Trustpilot
- debarras-nettoyage.fr — 15 ans, 4.9/5, bonne conversion
- debarras-gratuit.net — logos partenaires, formulaire avancé
- debarapide.com — WhatsApp, prix transparent (29€/m³)
- diogene-france.fr — niche Diogène, paiement en plusieurs fois
- debarrasseursbretons.fr — 40 ans, vidéos, preuve assurance
- debarras.fr — 25 ans, expertise brocante
