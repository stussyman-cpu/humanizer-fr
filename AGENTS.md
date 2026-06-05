# AGENTS.md

Ce fichier fournit des instructions pour les agents IA qui travaillent dans ce dépôt.

## Fichiers clés

- **SKILL.md** — Artefact runtime du skill. Contient le frontmatter YAML (métadonnées) et les 36 patterns numérotés avec exemples. C'est la source de vérité.
- **README.md** — Documentation utilisateur. Contient le tableau des 36 patterns, les guides d'installation, d'usage et l'historique des versions.
- **AGENTS.md** — Ce fichier. Instructions de maintenance pour agents IA.

## Relation avec le repo original

Ce skill est basé sur [blader/humanizer](https://github.com/blader/humanizer). La numérotation suit cette convention :

- **Patterns #1–#29** : patterns originaux anglais, traduits et adaptés au français
- **Pattern #30** : "diff-anchored writing", introduit dans blader/humanizer v2.7.0
- **Patterns #31–#36** : patterns spécifiques au français, sans équivalent dans l'original

Quand blader/humanizer publie une nouvelle version :
1. Lire le CHANGELOG du repo original
2. Si nouveaux patterns EN : les adapter en français et les insérer AVANT `## PATTERNS SUPPLÉMENTAIRES — SPÉCIFIQUES AU FRANÇAIS`
3. Renommer les patterns FR si la numérotation décale (toujours du plus haut vers le plus bas)
4. Mettre à jour le tableau du README et la checklist d'audit en conséquence

## Exigences de maintenance

### Synchronisation SKILL.md ↔ README

**Toujours modifier les deux dans le même commit** quand :
- Un pattern est ajouté, supprimé ou renuméroté
- Un nom de pattern change
- Des mots-clés importants changent

Le tableau du README (`| N° | Pattern | Mots-clés |`) doit refléter exactement ce qui est dans SKILL.md.

### Versioning

Format `MAJOR.MINOR.PATCH` :

| Type | Exemple | Déclenché par |
|------|---------|---------------|
| PATCH | 2.2.0 → 2.2.1 | Typo, clarification d'exemple, reformulation mineure |
| MINOR | 2.2.0 → 2.3.0 | Nouveau pattern, nouveau profil de voix, nouvelle fonctionnalité |
| MAJOR | 2.x → 3.0.0 | Refonte structurelle, incompatibilité avec versions précédentes |

Mettre à jour **dans le même commit** :
1. `version:` dans le frontmatter YAML de SKILL.md
2. Le badge version dans README.md (`version-X.Y.Z-blue.svg`)
3. La ligne dans la table "Version history" du README

### Règles d'édition YAML

Le frontmatter de SKILL.md est du YAML valide. Respecter :
- Indentation 2 espaces
- Le champ `description` est un bloc scalaire `>` — maintenir l'indentation de continuation
- Ne pas modifier `compatibility:` sans tester dans les environnements listés
- Le champ `base:` cite la version exacte de blader/humanizer utilisée comme référence

### Numérotation des patterns

- Ne pas renuméroter sans raison — la stabilité facilite les références croisées
- Si renumérotation nécessaire : mettre à jour TOUS les `(#N)` dans la checklist d'audit de SKILL.md et dans le tableau du README
- Faire les remplacements du numéro le plus haut vers le plus bas pour éviter les collisions
- Les patterns FR (#31–#36 actuellement) restent toujours en fin de fichier, après les patterns EN adaptés
