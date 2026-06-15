# Guide des paramètres

Ce guide explique chaque paramètre et comment le régler selon ta situation.

Pour bien démarrer : choisis ton jeu dans **Profil**, puis clique sur **Tester** pour vérifier que la lueur s'allume bien à gauche et à droite. Dans la plupart des cas, le seul réglage à toucher est la **Sensibilité**.

## Profil

Un profil contient un ensemble de réglages sauvegardés pour un jeu précis. Tu peux en créer autant que tu veux.

| Bouton | Ce que ça fait |
|---|---|
| Nouveau | Crée un nouveau profil à partir des valeurs actuelles |
| Supprimer | Supprime le profil sélectionné |

Choisis ton profil dans la liste : il reste actif tant que l'application tourne. Le profil **Generic** sert de base par défaut et ne peut pas être supprimé (le bouton Supprimer est grisé quand il est sélectionné).

Les modifications sont enregistrées automatiquement dès que tu déplaces un curseur.

## Périphérique audio

Choisis ici la même sortie audio que celle utilisée par ton jeu, puis clique sur **Appliquer**. Si tu utilises un logiciel audio tiers comme SteelSeries Sonar ou Nahimic, sélectionne le périphérique virtuel de ce logiciel dans la liste plutôt que ton casque directement.

## Monitoring

Cette section te montre en temps réel ce que Sideviz perçoit.

La barre de niveau affiche l'intensité du son détecté. Si elle ne bouge jamais, vérifie le périphérique audio sélectionné.

L'indicateur de direction affiche **G** quand un son est détecté à gauche, **D** quand il est à droite, et un point quand le son est centré ou trop faible.

### Tester

Le bouton **Tester** allume la lueur à gauche puis à droite, l'une après l'autre. Il sert à vérifier d'un coup d'œil que l'affichage fonctionne, sans avoir à lancer un jeu — pratique si tu n'entends pas le son. Le test s'affiche même si l'application est en pause.

## Sensibilité

Valeur par défaut : 0.15 — Plage : 0.05 à 0.50

C'est le réglage principal. Il contrôle à partir de quelle intensité sonore la lueur s'active.

```
0.05 ───────────[|||]───────────── 0.50
Très réactif                  Peu réactif
(tout s'allume)          (seulement les sons forts)
```

| Valeur basse | Valeur haute |
|---|---|
| Réagit aux sons discrets comme les pas | Réagit seulement aux sons forts comme les tirs |
| Lueur fréquente | Lueur rare mais précise |

Si la lueur s'allume trop souvent, monte vers 0.25 ou 0.35.
Si la lueur ne s'allume presque jamais, baisse vers 0.08 ou 0.12.

> Le seuil de silence (bruit de fond) se règle désormais **tout seul** : il n'y a plus de calibrage ni de réglage « plancher de bruit » à faire à la main.

## Avancé

Ces réglages sont rangés dans la section **Avancé** des paramètres, repliée par défaut. La plupart des joueurs n'ont besoin que de la **Sensibilité** ci-dessus.

### Zone morte centrale
Valeur par défaut : 0.04 — Plage : 0.01 à 0.20

Quand un son vient de face, la différence gauche/droite est trop faible pour être utile. Ce paramètre empêche la lueur de s'activer pour ces sons-là.

```
                    Zone morte
                  ┌─────────────┐
G ◄───────────────┤      ●      ├───────────────► D
                  └─────────────┘
              Sons frontaux ignorés
```

| Valeur basse | Valeur haute |
|---|---|
| Les sons légèrement décentrés déclenchent la lueur | Seuls les sons clairement à gauche ou à droite déclenchent la lueur |

Si la lueur s'active quand tu cours, monte vers 0.10 ou 0.15.
Si les sons latéraux ne déclenchent rien, baisse vers 0.03 ou 0.06.

### Lissage
Valeur par défaut : 0.25 — Plage : 0.05 à 0.50

Contrôle l'inertie du calcul de direction. Une valeur haute donne des transitions plus douces mais avec un léger délai.

```
0.05                                     0.50
Réactif                                 Lisse
(peut trembler sur les sons courts)     (légèrement en retard)
```

| Valeur basse | Valeur haute |
|---|---|
| Réagit instantanément | Transitions douces |
| Peut alterner gauche/droite rapidement | Stable et difficile à faire trembler |

### Opacité
Valeur par défaut : 1.0 — Plage : 0.2 à 5.0

Contrôle la luminosité de la lueur. Une valeur supérieure à 1.0 l'amplifie, utile si tu ne la vois pas bien en jeu.

```
0.2          1.0          5.0
Discret     Normal     Très brillant
```

### Largeur de la lueur
Valeur par défaut : 280 px — Plage : 50 à 500 px

Épaisseur maximale de la lueur sur le bord de l'écran, atteinte lors des sons les plus forts.

```
50 px          280 px              500 px
│█│      │████████████│    │█████████████████████│
Fin           Normal               Large
```

### Durée du fondu
Valeur par défaut : 1800 ms — Plage : 300 à 4000 ms

Durée pendant laquelle la lueur reste visible après un son avant de disparaître progressivement.

```
Son détecté
     │
     ▼
  ████████▓▓▓▒▒▒░░░─────
  ←────────────────→
       Durée du fondu
```

Une durée courte entre 500 et 1200 ms convient aux jeux rapides. Une durée longue entre 1500 et 3000 ms convient aux jeux plus posés.

### Mode daltonisme

Palette de couleurs adaptée à ta vision.

| Mode | Couleurs | Pour qui |
|---|---|---|
| Désactivé | Rouge, orange et bleu | Vision normale |
| Bleu / Jaune | Bleu et jaune | Deutéranopie et protanopie |
| Contraste élevé | Blanc et gris | Toutes formes de daltonisme |

## Raccourci clavier

**Ctrl + Shift + V** met l'application en pause ou la reprend depuis n'importe où, sans quitter le jeu.

## Dépannage

### La lueur ne s'affiche pas pendant le jeu

Certains jeux en **plein écran exclusif** prennent la main complète sur l'affichage et masquent **tous** les overlays (Sideviz, mais aussi parfois ceux de Discord ou Steam). Ce n'est pas un bug de Sideviz, c'est une limite de ce mode d'affichage.

**La solution : passe le jeu en « plein écran fenêtré ».**

Dans les paramètres **Vidéo / Graphismes** du jeu, choisis **Plein écran fenêtré** (parfois appelé *Borderless* ou *Fenêtré sans bordure*) au lieu de **Plein écran**. L'image reste identique et en plein écran — mais Sideviz peut alors s'afficher par-dessus.

Exemples :
- **Valorant** : Paramètres → Vidéo → Général → *Mode d'affichage* → **Plein écran fenêtré**

Astuce : après avoir changé le mode, clique sur le bouton **Tester** dans Sideviz pour vérifier que la lueur s'allume bien à gauche et à droite.
