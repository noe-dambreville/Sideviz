<!--
WORKFLOW (ne s'affiche pas sur GitHub) :
1. Au fil du dev, ajoute tes changements sous "## [Non publié]".
2. Pour sortir une version : renomme "[Non publié]" en "[X.Y.Z] — JJ mois AAAA",
   puis remets un "## [Non publié]" vide tout en haut.
3. Release GitHub : copie/colle la section de la version (gh release ... --notes-file possible).
4. Discord : reprends "En bref" + 2-3 points phares + le lien de téléchargement.
Public = joueurs sourds/malentendants : pas de jargon, un point = une idée, vue utilisateur.
-->

# Changelog — Sideviz

Toutes les modifications notables de Sideviz sont listées ici.

---

## [Non publié]

Rien pour le moment.

---

## [1.1.0] — 15 juin 2026

En bref : le réglage du son devient automatique (fini le calibrage), un bouton « Tester » permet de vérifier en un clic que la lueur s'allume, et l'affichage est corrigé sur les écrans haute résolution.

### Nouveautés
- Bouton « Tester » dans les paramètres : allume la lueur à gauche puis à droite pour vérifier en un coup d'œil que tout fonctionne, sans lancer de jeu. Utile si tu n'entends pas le son.
- Message d'accueil au premier lancement pour bien démarrer.

### Améliorations
- Plus besoin de calibrer : le seuil de détection s'ajuste tout seul, en continu.
- Paramètres simplifiés : un seul curseur « Sensibilité » à l'écran ; les réglages avancés sont rangés dans une section « Avancé » repliable.
- Profils de jeu allégés et plus clairs.

### Corrections de bugs
- Lueur mal placée ou trop grande sur les écrans en haute résolution (mise à l'échelle Windows 125 %, 150 %…) : corrigé.
- Le profil « Generic » est maintenant correctement sélectionné par défaut au démarrage (il basculait par erreur sur « Apex Legends »).
- Le bouton « Supprimer » est désactivé quand « Generic » est sélectionné, pour éviter une suppression accidentelle.

### Changements importants
- Le calibrage manuel a été retiré : devenu inutile, la détection se règle toute seule.
- La détection automatique de jeu a été retirée : choisis ton profil à la main dans les paramètres (c'est plus fiable). Ton choix reste actif tant que l'application tourne.

### Infos techniques
- Les anciens profils de jeu sont obsolètes et refaire les paramètres.
---

## [1.0.0] — 2 juin 2026

Première version publique de Sideviz, l'overlay audio qui aide les joueurs sourds et malentendants à localiser les sons.

### Nouveautés
- Lueur sur le bord gauche ou droit de l'écran selon la direction du son.
- Intensité de la lueur proportionnelle au volume sonore.
- Couleur selon la fréquence du son (grave = rouge, aigu = bleu).
- Filtrage automatique des bruits ambiants constants pour éviter les fausses détections.
- Profils par jeu pour adapter les réglages.
- Fonctionne en overlay, sans rien modifier dans les jeux, avec un impact minimal sur les performances.
- Distribué en un seul fichier `.exe`, sans installation.

### Infos techniques
- Compatible Windows 10 et 11.
- Compatible avec les logiciels audio tiers (Dolby Atmos, SteelSeries Sonar, Nahimic).
- Aucun accès à la mémoire des jeux (aucune injection, aucun hook) : sans risque pour l'anti-cheat.
- Gratuit pour un usage personnel (voir [licence](LICENSE)).

---

## Mettre à jour

Télécharge la dernière version sur la [page Releases](https://github.com/noe-dambreville/Sideviz/releases/latest) et remplace `Sideviz.exe` — voir [INSTALL](INSTALL.md). Tes profils sont conservés.
