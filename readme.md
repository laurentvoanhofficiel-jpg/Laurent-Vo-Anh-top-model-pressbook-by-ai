# README — Laurent Vo Anh Top Model Pressbook by AI

## 📌 Présentation

Ce dépôt regroupe **trois applications web autonomes** (fichiers HTML uniques) qui exploitent l'API **Agnès AI** pour générer des visuels cohérents à partir d'une photo de référence ou d'un avatar. Chaque code est un outil complet de création de **pressbooks**, **storyboards**, **affiches**, **flyers**, **portraits artistiques**, etc.

Les trois codes partagent le même moteur : analyse du visage, génération de prompts par IA, production d'images en série, sauvegarde de sessions et base de connaissances persistante. Ils diffèrent par leur **mode de préservation du sujet** :

| Code | Nom | Principe | Lien GitHub |
|------|-----|----------|-------------|
| **Code 1** | **Avatar Inspiré** | Analyse une photo → génère une description textuelle → crée un **avatar** (le visage n'est pas pixel-perfect, il est inspiré). | [deepseek_html_20261014_8a875b.html](https://github.com/laurentvoanhofficiel-jpg/Laurent-Vo-Anh-top-model-pressbook-by-ai/blob/main/deepseek_html_20261014_8a875b.html) |
| **Code 2** | **Pressbook Fidèle** | Envoie la **photo de référence directement à Agnès** (mode `image + strength`) → le visage est **préservé à l'identique** sur toutes les images. | [deepseek_html_20261014_d858dd (1).html](https://github.com/laurentvoanhofficiel-jpg/Laurent-Vo-Anh-top-model-pressbook-by-ai/blob/main/deepseek_html_20261014_d858dd%20(1).html) |
| **Code 3** | **Pressbook Hybride** | **Mélange les deux options** : un menu déroulant permet de choisir « Ma propre image » (fidélité) ou « Mon avatar » (inspiration). | [deepseek_html_20261014_d858dd (2).html](https://github.com/laurentvoanhofficiel-jpg/Laurent-Vo-Anh-top-model-pressbook-by-ai/blob/main/deepseek_html_20261014_d858dd%20(2).html) |

> **Différence clé** : les codes 2 et 3 envoient l'image à Agnès (`body.image = refDataUrl` + `strength = 0.42`), ce qui verrouille les traits du visage. Le code 1 envoie uniquement une description texte (analyse forensique) — l'IA recrée un visage « inspiré », pas identique.

---

## 🚀 Comment utiliser ces codes

1. **Téléchargez** le fichier HTML souhaité (un seul fichier suffit, aucune installation).
2. **Ouvrez-le** dans un navigateur moderne (Chrome, Edge, Firefox, Safari).
3. **Obtenez une clé API Agnès** (voir section suivante).
4. **Collez la clé** dans le champ « Clés API Agnès » (une clé par ligne, plusieurs clés possibles).
5. **Ajoutez une ou plusieurs photos** de vous (visage bien visible).
6. **Choisissez le mode** : « Ma propre image » ou « Mon avatar » (codes 2 et 3).
7. **Lancez** : l'IA analyse le visage, conçoit des catégories créatives, puis génère les images par lots de 120 (6 catégories × 20 concepts).
8. **Ajoutez des onglets personnalisés** à tout moment (avant ou pendant la génération) : l'IA optimise votre prompt et crée 20 variations prioritaires.
9. **Exportez** vos sessions en JSON pour les sauvegarder ou les partager.

---

## 🔑 Obtenir une clé API Agnès

1. Rendez-vous sur [platform.agnes-ai.com](https://platform.agnes-ai.com).
2. Créez un compte gratuit.
3. Allez dans **Settings → API Keys**.
4. Générez une clé (commence par `sk-`).
5. Copiez-la et collez-la dans l'application.

> Vous pouvez ajouter **plusieurs clés** (une par ligne) pour accélérer la génération : chaque clé tourne en parallèle.

---

## ⚠️ Limites de la clé gratuite Agnès

D'après la documentation officielle :

| Ressource | Limite gratuite |
|-----------|-----------------|
| **Modèles texte** (analyse, auto-définition, optimisation) | **10 RPM** (requêtes par minute) |
| **Modèles image** (1K résolution) | **20 RPM** · ~**4 000 images/jour** |
| **Modèles image** (2K résolution) | **10 RPM** · ~4 000 images/jour |
| **File d'attente globale** | Peut renvoyer des erreurs `503` (file saturée) en période de forte demande |

> **Recommandation** : utilisez plusieurs clés (2 à 5) et espacez les requêtes (4,5 s minimum entre deux appels sur la même clé). Le code gère automatiquement les `503` par une pause globale avec reprise.

---

## 🧩 Différences détaillées entre les trois codes

| Fonctionnalité | Code 1 (Avatar) | Code 2 (Fidèle) | Code 3 (Hybride) |
|---------------|----------------|-----------------|------------------|
| **Mode de préservation** | Description texte uniquement | Image + strength 0.42 | Les deux (menu déroulant) |
| **Fidélité du visage** | Inspiré (peut varier) | Identique (verrouillé) | Au choix |
| **Nombre de catégories/ronde** | 6 | 6 | 6 |
| **Images par catégorie** | 20 | 20 | 20 |
| **Auto-évolution (nouvelles rondes)** | ✅ | ✅ | ✅ |
| **Base de connaissances persistante** | ✅ | ✅ | ✅ |
| **Onglets personnalisés** | ✅ | ✅ | ✅ |
| **Gestion 503 / pause globale** | Version la plus aboutie | Version intermédiaire | Version initiale |
| **Affichage des onglets pendant la conception** | ✅ (pulse) | ❌ | ❌ |
| **Analyse visage** | 1 seule requête | 1 seule requête | 1 seule requête |

> Le **Code 1** est le plus récent et le plus robuste (gestion avancée des pauses, onglets de chargement visibles, concurrence optimisée). Le **Code 3** est le plus ancien et le plus simple.

---

## 🌐 40 exemples de sites/outils à créer avec ces codes

| # | Domaine | Exemple de site | Utilisation |
|---|---------|----------------|-------------|
| 1 | Cinéma | **StoryboardAI** | Transforme un scénario en storyboard visuel plan par plan |
| 2 | Cinéma | **Previs Studio** | Prévisualisation de scènes avec le réalisateur comme personnage principal |
| 3 | Cinéma | **PitchDeck Filmmaker** | Génère un pitch deck illustré pour financer un film |
| 4 | Cinéma | **Affiche de film** | Crée des affiches de film avec l'utilisateur en star |
| 5 | Cinéma | **Film Kung-Fu** | Génère les premières images de chaque plan d'un film d'arts martiaux |
| 6 | Cinéma | **Court-métrage** | Visualise les scènes clés d'un court-métrage |
| 7 | Publicité | **Campaign Studio** | Crée des visuels publicitaires avec le client comme mannequin |
| 8 | Publicité | **Affiches urbaines** | Génère des affiches pour une campagne d'affichage |
| 9 | Publicité | **Spots TV** | Storyboard pour publicités télévisées |
| 10 | Mode | **Pressbook Model** | Génère un pressbook complet pour un mannequin |
| 11 | Mode | **Lookbook E-commerce** | Crée des lookbooks pour boutiques en ligne |
| 12 | Mode | **Catalogue PDF** | Produit un catalogue de mode personnalisé |
| 13 | Art | **Portrait Gallery** | Génère des portraits dans le style des grands maîtres |
| 14 | Art | **Musée virtuel** | Crée une galerie d'art personnalisée |
| 15 | Musique | **Pochette d'album** | Génère des pochettes d'albums avec l'artiste en vedette |
| 16 | Musique | **Flyer de concert** | Crée des flyers pour des concerts fictifs ou réels |
| 17 | Musique | **Clip vidéo** | Storyboard pour clips musicaux |
| 18 | Sport | **Affiche de match** | Génère des affiches pour des événements sportifs |
| 19 | Sport | **Portrait d'athlète** | Crée des portraits héroïques d'athlètes |
| 20 | Édition | **Couverture de livre** | Génère des couvertures de romans avec l'auteur en personnage |
| 21 | Édition | **BD / Manga** | Crée des planches de bande dessinée avec un personnage cohérent |
| 22 | Jeux vidéo | **Concept Art** | Génère des concept arts pour jeux vidéo |
| 23 | Jeux vidéo | **Avatar de jeu** | Crée un avatar de jeu vidéo personnalisé |
| 24 | Architecture | **Visualisation 3D** | Place l'utilisateur dans des rendus architecturaux |
| 25 | Immobilier | **Visite virtuelle** | Génère des visuels pour des biens immobiliers |
| 26 | Tourisme | **Brochure voyage** | Crée des brochures avec l'utilisateur dans des destinations |
| 27 | Gastronomie | **Menu illustré** | Génère des menus avec le chef en vedette |
| 28 | Beauté | **Avant/Après** | Simule des transformations esthétiques |
| 29 | Automobile | **Catalogue auto** | Place l'utilisateur dans des voitures de luxe |
| 30 | Technologie | **Mockup produit** | Crée des visuels de produits tech avec l'utilisateur |
| 31 | Événementiel | **Invitation mariage** | Génère des faire-part personnalisés |
| 32 | Événementiel | **Affiche festival** | Crée des affiches pour festivals |
| 33 | Réseaux sociaux | **Avatar profile** | Génère des avatars pour les réseaux sociaux |
| 34 | Réseaux sociaux | **Contenu Instagram** | Produit du contenu visuel pour influenceurs |
| 35 | Éducation | **Illustration cours** | Crée des illustrations pour supports pédagogiques |
| 36 | Santé | **Visualisation médicale** | Génère des visuels pour la communication médicale |
| 37 | Politique | **Affiche campagne** | Crée des affiches de campagne électorale |
| 38 | Religion | **Art sacré** | Génère des œuvres d'art religieux personnalisées |
| 39 | Histoire | **Reconstitution** | Place l'utilisateur dans des scènes historiques |
| 40 | Science-fiction | **Univers SF** | Crée des visuels pour des romans de science-fiction |

---

## 🔮 Possibilités de développement futur

- **Génération vidéo** : les prompts vidéo sont déjà inclus dans chaque carte photo (action, caméra, style). Il suffit de les envoyer à un modèle vidéo (Agnès `agnes-video-v2.0` ou autre).
- **Export PDF automatique** : compiler les images d'une session en un pressbook PDF paginé.
- **Mode multi-personnages** : permettre plusieurs visages de référence pour créer des scènes de groupe (couples, familles, équipes).
- **Interface collaborative** : partager une session en temps réel entre plusieurs utilisateurs.
- **Marketplace de prompts** : les utilisateurs peuvent vendre ou échanger leurs onglets personnalisés.
- **Intégration WordPress / Shopify** : plugin pour générer des visuels produits directement depuis une boutique.
- **API publique** : exposer le moteur sous forme d'API REST pour que d'autres développeurs l'intègrent.
- **Fine-tuning du modèle** : entraîner un modèle LoRA sur le visage de l'utilisateur pour une fidélité encore supérieure.
- **Reconnaissance vocale** : dicter le prompt personnalisé au lieu de l'écrire.
- **Mode hors-ligne** : version PWA installable avec cache des sessions.

---

## 📄 Licence

Ces codes sont fournis à titre éducatif et créatif. L'utilisation de l'API Agnès est soumise aux conditions d'utilisation de la plateforme. Les images générées sont la propriété de leurs créateurs selon les règles d'Agnès AI.

---

*Dernière mise à jour : octobre 2026*
