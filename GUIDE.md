# Guide des paramètres

Ce guide explique chaque paramètre et comment le régler selon ta situation.

## Profil

Un profil contient un ensemble de réglages sauvegardés pour un jeu précis. Tu peux en créer autant que tu veux.

| Bouton | Ce que ça fait |
|---|---|
| Nouveau | Crée un nouveau profil à partir des valeurs actuelles |
| Supprimer | Supprime le profil sélectionné |

Le profil Generic ne peut pas être supprimé, il sert de base par défaut.

## Device audio

Choisis ici la même sortie audio que celle utilisée par ton jeu. Si tu utilises un logiciel audio tiers comme SteelSeries Sonar ou Nahimic, sélectionne le périphérique virtuel de ce logiciel dans la liste plutôt que ton casque directement.

## Monitoring

Cette section te montre en temps réel ce que Sideviz perçoit.

La barre de niveau affiche l'intensité du son détecté. Si elle ne bouge jamais, vérifie le périphérique audio sélectionné.

L'indicateur de direction affiche G quand un son est détecté à gauche, D quand il est à droite, et un point quand le son est centré ou trop faible.

### Calibrer

La calibration mesure le niveau de bruit ambiant pendant 3 secondes et règle le plancher de bruit automatiquement. C'est le premier réglage à faire avant tout autre chose.

Comment calibrer correctement :
1. Lance ton jeu
2. Place-toi dans une zone calme comme un lobby ou une base
3. Clique sur Calibrer
4. Attends 3 secondes sans déclencher de sons
5. Le plancher de bruit se met à jour automatiquement

## Audio

### Sensibilité
Valeur par défaut : 0.15 - Plage : 0.05 à 0.50

Contrôle à partir de quelle intensité sonore le glow s'active.

```
0.05 ───────────[|||]───────────── 0.50
Très sensible                Peu sensible
(tout s'allume)          (seulement les sons forts)
```

| Valeur basse | Valeur haute |
|---|---|
| Réagit aux sons discrets comme les pas | Réagit seulement aux sons forts comme les tirs |
| Glow fréquent | Glow rare mais précis |

Si le glow s'allume trop souvent, monte vers 0.25 ou 0.35.
Si le glow ne s'allume presque jamais, baisse vers 0.08 ou 0.12.

### Plancher de bruit
Valeur par défaut : 1.0 - Plage : 0.1 à 10.0

Niveau minimal en dessous duquel Sideviz considère que c'est du silence. Utilise le bouton Calibrer plutôt que de régler ce paramètre à la main.

Si le glow s'active sans raison quand il n'y a aucun son dans le jeu, monte ce paramètre vers 2.0 ou 3.0.

### Zone morte centrale
Valeur par défaut : 0.04 - Plage : 0.01 à 0.20

Quand un son vient de face, la différence gauche droite est trop faible pour être utile. Ce paramètre empêche le glow de s'activer pour ces sons-là.

```
                    Zone morte
                  ┌─────────────┐
G ◄───────────────┤      ●      ├───────────────► D
                  └─────────────┘
              Sons frontaux ignorés
```

| Valeur basse | Valeur haute |
|---|---|
| Les sons légèrement décentrés déclenchent le glow | Seuls les sons clairement à gauche ou à droite déclenchent le glow |

Si le glow s'active quand tu cours, monte vers 0.10 ou 0.15.
Si les sons latéraux ne déclenchent rien, baisse vers 0.03 ou 0.06.

### Lissage
Valeur par défaut : 0.25 - Plage : 0.05 à 0.50

Contrôle l'inertie du calcul de direction. Une valeur haute donne des transitions plus douces mais avec un léger délai.

```
0.05                                     0.50
Réactif                                 Lisse
(peut trembler sur les sons courts)     (légèrement en retard)
```

| Valeur basse | Valeur haute |
|---|---|
| Réagit instantanément | Transitions douces |
| Peut alterner gauche droite rapidement | Stable et difficile à faire trembler |

## Visuel


### Opacité globale
Valeur par défaut : 1.0 - Plage : 0.2 à 5.0

Contrôle la luminosité du glow. Une valeur supérieure à 1.0 amplifie le glow, utile si tu ne le vois pas bien en jeu.

```
0.2          1.0          5.0
Discret     Normal     Très brillant
```

### Largeur du glow
Valeur par défaut : 280 px - Plage : 50 à 500 px

Épaisseur maximale du glow sur le bord de l'écran, atteinte lors des sons les plus forts.

```
50 px          280 px              500 px
│█│      │████████████│    │█████████████████████│
Fin           Normal               Large
```

### Durée du fade
Valeur par défaut : 1800 ms - Plage : 300 à 4000 ms

Durée pendant laquelle le glow reste visible après un son avant de disparaître progressivement.

```
Son détecté
     │
     ▼
  ████████▓▓▓▒▒▒░░░─────
  ←────────────────→
       Durée fade
```

Une durée courte entre 500 et 1200 ms convient aux jeux rapides. Une durée longue entre 1500 et 3000 ms convient aux jeux plus posés.

### Mode daltonisme

Palette de couleurs adaptée à ta vision. Ce mode est ignoré si la couleur personnalisée est activée.

| Mode | Couleurs | Pour qui |
|---|---|---|
| none | Rouge, orange et bleu | Vision normale |
| blue_yellow | Bleu et jaune | Deutéranopie et protanopie |
| high_contrast | Blanc et gris | Toutes formes de daltonisme |

## Raccourci clavier

Ctrl + Shift + V met l'application en pause ou la reprend depuis n'importe où sans quitter le jeu.
