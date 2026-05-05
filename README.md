# humanizer-fr

Extension française de [blader/humanizer](https://github.com/blader/humanizer) — un skill pour Claude Code et OpenCode qui supprime les marqueurs d'écriture IA pour rendre un texte plus naturel et humain.

## Ce qui change par rapport à l'original

Le skill original est calibré sur l'anglais. Cette version ajoute :

- **Traduction complète** des 29 patterns originaux avec exemples en français
- **6 patterns spécifiques au français** (voir ci-dessous)
- **Checklist d'audit structurée** pour le second pass — remplace la question ouverte "what makes this obviously AI generated?" par des critères binaires organisés en 5 catégories

## Les 6 patterns supplémentaires

| # | Pattern | Exemple avant | Exemple après |
|---|---------|---------------|---------------|
| 30 | **Transitions de dissertation** | "Dans un premier temps… dans un second temps…" | Enchaîner directement les idées |
| 31 | **Formules de politesse IA-françaises** | "Je me permets de… N'hésitez pas à me solliciter" | "Voici l'analyse. Si tu veux qu'on creuse, dis-moi." |
| 32 | **Sur-structuration** | Liste à puces pour 4 adjectifs | Un paragraphe fluide |
| 33 | **Nominalisation excessive** | "La mise en œuvre de la facilitation de…" | "Mettre en place… faciliter…" |
| 34 | **Inflation modale** | "Il est évident que… il semblerait que…" | "C'est le cas. / Ça pose un problème." |
| 35 | **Conclusion en "En conclusion"** | "En conclusion, l'avenir s'annonce prometteur." | Finir sur un fait concret |

## Installation

### Claude Code

```bash
mkdir -p ~/.claude/skills
git clone https://github.com/[stussyman-cpu]/humanizer-fr.git ~/.claude/skills/humanizer-fr
```

### OpenCode

```bash
mkdir -p ~/.config/opencode/skills
git clone https://github.com/[stussyman-cpu]/humanizer-fr.git ~/.config/opencode/skills/humanizer-fr
```

> OpenCode scanne aussi `~/.claude/skills/` pour la compatibilité, donc un seul clone suffit pour les deux.

## Utilisation

### Claude Code / OpenCode

```
/humanizer-fr

[colle ton texte ici]
```

Ou directement :

```
Humanise ce texte : [ton texte]
```

### Calibration de voix

Pour que la réécriture colle à ton style personnel :

```
/humanizer-fr

Voici un exemple de mon écriture pour caler le style :
[2-3 paragraphes de ta propre écriture]

Humanise maintenant ce texte :
[texte à humaniser]
```

## Crédits

- 29 patterns originaux : [blader/humanizer](https://github.com/blader/humanizer) — MIT
- 6 patterns français + checklist d'audit : ce repo — MIT

## Licence

MIT
