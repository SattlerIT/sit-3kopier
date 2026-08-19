# Journal des modifications — S-IT-3Copier

Toutes les modifications notables de S-IT-3Copier, les plus récentes en premier.

## v3.3.2.9 — août 2026 · Édition internationale

- **Nouveau :** l'outil parle quatre langues – allemand, anglais, français et espagnol. La langue se choisit à l'installation et se change à tout moment sous ⚙ ; la sélection affiche le drapeau correspondant à chaque langue. Le nom du programme change avec elle : 3Kopier, 3Copy, 3Copier, 3Copiar.
- Sont traduits l'interface, toutes les boîtes de dialogue, les messages affichés pendant la copie, le planificateur et les journaux. Chaque langue a sa propre page d'aide ; les pages sont reliées entre elles.
- Les noms de fichiers et les réglages restent identiques dans toutes les langues (`3Kopier.ini`, profils en `.3ko`, dossier `Logs`) – changer de langue ne modifie rien aux profils, filtres et réglages existants.
- **Amélioré :** les réglages (⚙) sont désormais présentés sur deux colonnes – langue et mise à l'échelle à gauche, conservation et niveau de détail des journaux à droite. La fenêtre est ainsi nettement moins haute et tient entièrement à l'écran, même à forte mise à l'échelle.
- **Amélioré :** les boutons de la barre de profils s'adaptent à la longueur de leur libellé, afin que le texte garde une marge suffisante dans chaque langue.

## v3.3.2.8 — août 2026

- **Nouveau :** tolérance d'horodatage contre les écarts sur les NAS et lecteurs réseau – en mode « seulement si plus récent », des fichiers inchangés ne sont plus pris à tort pour des fichiers plus récents à cause d'écarts de quelques secondes, ni recopiés à chaque exécution (tolérance de 2 secondes, comme Robocopy /FFT).
- **Nouveau :** symbole 🛡 par profil (à côté de 🚫) – il règle cette tolérance (Automatique / Toujours / Désactivé) ; « Automatique » n'agit que sur les chemins réseau `\\` et constitue le réglage par défaut, « Toujours » aide pour les lecteurs réseau montés sur une lettre (`X:`, `Y:` …).
- **Amélioré :** les chemins dans l'aperçu des tâches ne sont plus coupés au bord mais raccourcis proprement (début…fin) ; le chemin complet apparaît en info-bulle.
- **Corrigé :** la fenêtre d'exécution ne pouvait pas être réduite lorsqu'elle était lancée depuis la fenêtre du planificateur ouverte ; la croix de fermeture (X) agit désormais comme ⏹ Stop et interrompt proprement cette seule exécution.

## v3.3.2 — juillet 2026

- **Nouveau :** affichage de la vitesse – pendant la copie, la ligne d'état indique le débit du moment (`157.4 MB/s`, par exemple), y compris dans la fenêtre de progression du planificateur.
- **Nouveau :** filtre par tâche (🔰) – exclusions supplémentaires pour cette tâche uniquement, ou règle UNIQUEMENT (« ne copier que certains types de fichiers »), par exemple la tâche 1 seulement en `*.pdf`. Le symbole 🔰 passe au vert dès qu'une règle est définie ; les exclusions valables pour tout le profil s'appliquent toujours en plus.
- **Nouveau :** niveau de détail du journal au choix (⚙) – Compact (par défaut) avec une ligne de synthèse par tâche, Détaillé avec une ligne par dossier ; les erreurs figurent toujours intégralement dans le journal.
- **Nouveau :** file d'attente pour le planificateur – les exécutions qui se chevauchent ne sont plus perdues mais s'enchaînent ; les fenêtres de résultat ne bloquent pas l'exécution suivante, ⏹ Stop n'interrompt que celle en cours. La fenêtre d'exécution apparaît aussi en mode zone de notification et peut être réduite ; les interruptions figurent dans le journal sous la mention « FAZIT (ABGEBROCHEN) ».

## v3.3.1 — juillet 2026 · Passage à Python

- Passage complet d'AutoIt à Python – utilisation et déroulement inchangés, les fichiers `3Kopier.ini` et les profils `.3ko` existants continuent de fonctionner sans adaptation.
- Les copies s'effectuent en arrière-plan – l'interface reste réactive même avec un très grand nombre de fichiers ou des lecteurs réseau lents ; copie par blocs, « Stop » agit immédiatement.
- **Nouveau :** planificateur automatique – exécuter des profils selon un horaire en arrière-plan, mode silencieux et fonctionnement dans la zone de notification avec démarrage automatique compris.
- **Nouveau :** liste d'exclusion – écarter de la copie des fichiers et des dossiers entiers (caches de navigateurs, fichiers temporaires, grands formats d'image) ; avec des valeurs par défaut d'origine, adaptables par profil.
- **Nouveau :** mise en veille après la copie, en alternative à l'arrêt (les deux options s'excluent mutuellement).
- Nouveaux réglages (⚙) : mise à l'échelle de 90 à 200 %, conservation des journaux (de 1 jour à illimité) avec nettoyage immédiat ; les journaux sont désormais un fichier distinct par exécution dans le dossier `Logs`.
- Fenêtre de résultat revue (une colonne par tâche) ; la liste déroulante des profils charge immédiatement, sans bouton « Charger » ; les chemins très longs sont affichés raccourcis (début…fin), le chemin complet en info-bulle.
- Chemins réseau/NAS (UNC) améliorés, calcul du volume de données sans blocage ; le bilan figure désormais en haut ; corrections de mise en page mineures ; `Lizenz.txt` est joint.

## v3.2.1 — version AutoIt

- Traitement automatique des chemins longs (MAX_PATH) : les chemins cibles à partir de 260 caractères sont raccourcis automatiquement – d'abord le nom du fichier, au besoin également le dernier sous-dossier. Les noms raccourcis reçoivent la marque `-3k`.
- Volume de données également pris en compte correctement pour les chemins longs, dans l'affichage comme dans la barre de progression.
- Taille du journal limitée automatiquement à 512 Ko – les entrées les plus anciennes sont supprimées, les exécutions récentes sont conservées.

## v3.2.0 — version AutoIt

- Les options écraser/déplacer par tâche sont désormais enregistrées aussi bien dans le fichier INI que dans les profils `.3ko`.
- Les dossiers cibles sont créés avant la vérification ; les chemins réseau sont ignorés lors du calcul du volume de données, sans blocage.
- Corrections visuelles : espacements de l'en-tête, largeurs des libellés et positions des cases à cocher revus.

---

© 2026 Sattler IT-Service, Greifenstein · Auteur : Hans Udo Sattler
