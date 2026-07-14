# humanizer-fr

> Supprime les marqueurs d'écriture IA pour rendre un texte plus naturel et humain.

[![Version](https://img.shields.io/badge/version-2.3.0-blue.svg)](https://github.com/stussyman-cpu/humanizer-fr)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![Compat](https://img.shields.io/badge/compat-Claude%20Code%20%7C%20OpenCode-purple.svg)]()
[![Version](https://img.shields.io/badge/version-2.4.0-blue.svg)](https://github.com/stussyman-cpu/humanizer-fr)

Extension française de [blader/humanizer](https://github.com/blader/humanizer) — 36 patterns (30 originaux adaptés + 6 spécifiques au français), 5 profils de voix, 3 modes d'opération, mode interactif.

---

## Installation

**Claude Code**
```bash
git clone git@github.com:stussyman-cpu/humanizer-fr.git ~/.claude/skills/humanizer-fr
```

**OpenCode**
```bash
git clone git@github.com:stussyman-cpu/humanizer-fr.git ~/.config/opencode/skills/humanizer-fr
```

---

## Utilisation

**Mode interactif** (sans flags — pose 3 questions avant de lancer) :
```
/humanizer-fr "votre texte ici"
```

**Avec flags :**
```bash
/humanizer-fr "texte"                              # rewrite, voix auto
/humanizer-fr "texte" --voice casual               # rewrite, voix décontractée
/humanizer-fr "texte" --mode detect                # détection uniquement
/humanizer-fr "texte" --mode edit                  # corrections légères
/humanizer-fr "texte" --voice direct --aggressive  # transformation maximale
/humanizer-fr --mode edit --file mon-document.md   # éditer un fichier
```

**Calibration de voix** (optionnel) :
```
Humanise ce texte. Voici un exemple de mon écriture pour caler le style : [échantillon]
```

---

## Modes

| Mode | Description | Usage idéal |
|------|-------------|-------------|
| `rewrite` | Réécriture complète avec injection de voix *(défaut)* | Blog, posts, mails |
| `detect` | Rapport de détection sans réécriture | Auditer avant de travailler |
| `edit` | Corrections minimales ciblées | Nettoyer une doc, polir un README |

---

## Profils de voix (`--voice`)

| Profil | Style | Idéal pour |
|--------|-------|------------|
| `casual` | Contractions, "je", phrases courtes | Posts, réseaux sociaux, blogs |
| `professionnel` | Registre soutenu mais concret | Rapports, mails, documents formels |
| `technique` | Précision, termes exacts, direct | Docs, READMEs, spécifications |
| `chaleureux` | Empathie, "nous/notre", paragraphes courts | Tutoriels, onboarding, support |
| `direct` | Zéro hedging, voix active, minimal | Feedback, comms internes, avis |

Sans `--voice` : adaptation automatique au registre du texte original.

---

## Les 36 patterns

### Contenu

| N° | Pattern | Mots-clés |
|----|---------|-----------|
| 1 | Inflation de l'importance | vital, crucial, charnière, témoignage, paysage |
| 2 | Insistance sur la notoriété | cité dans, couverture médiatique, présence sur les réseaux |
| 3 | Analyses superficielles en -ant | soulignant, reflétant, symbolisant, illustrant |
| 4 | Langage promotionnel | niché, époustouflant, emblématique, révolutionnaire |
| 5 | Attributions vagues | les experts estiment, selon des observateurs |
| 6 | Section "Défis et perspectives" | malgré ces défis, continue de prospérer |

### Langage et grammaire

| N° | Pattern | Mots-clés |
|----|---------|-----------|
| 7 | Vocabulaire IA sur-utilisé | de plus, crucial, explorer, durable, favoriser, tapisserie |
| 8 | Évitement de "est"/"sont" | sert de, fait office de, constitue, dispose de |
| 9 | Parallélismes négatifs | Non seulement…mais aussi, Ce n'est pas juste X c'est Y |
| 10 | Règle de trois | A, B et C ; innovation, inspiration et insights |
| 11 | Variation synonymique | protagoniste / personnage principal / figure centrale |
| 12 | Fausses plages | du Big Bang à la toile cosmique |
| 13 | Voix passive et fragments sans sujet | Aucun fichier nécessaire. Les résultats sont conservés. |

### Style

| N° | Pattern | Mots-clés |
|----|---------|-----------|
| 14 | Tirets cadratins *(règle dure — zéro tolérance)* | — et – : suppression obligatoire |
| 15 | Abus de gras | **OKR**, **KPI**, **terme** en milieu de prose |
| 16 | Listes avec en-têtes inline | **Expérience :** texte qui suit |
| 17 | Majuscules dans les titres | ## Négociations Stratégiques Et Partenariats |
| 18 | Emojis | 🚀 💡 ✅ en contexte prose ou titres |
| 19 | Guillemets non-français | "…" au lieu de « … » |

### Communication

| N° | Pattern | Mots-clés |
|----|---------|-----------|
| 20 | Artefacts chatbot | J'espère que ça aide, Bien sûr !, N'hésitez pas à |
| 21 | Disclaimers et langage spéculatif | selon les infos disponibles, il semblerait que X soit discret |
| 22 | Ton sycophantique | Excellente question !, Tu as tout à fait raison |

### Remplissage et hedging

| N° | Pattern | Mots-clés |
|----|---------|-----------|
| 23 | Phrases de remplissage | Afin d'atteindre, Il est important de noter |
| 24 | Hedging excessif | pourrait potentiellement, dans une certaine mesure |
| 25 | Conclusions génériques positives | L'avenir s'annonce prometteur, des jours passionnants |
| 26 | Mots composés avec trait d'union | cross-fonctionnel, basé-sur-les-données |
| 27 | Rhétorique d'autorité persuasive | La vraie question est, au fond, ce qui compte vraiment |
| 28 | Annonces et signposting | Plongeons dans, voici ce qu'il faut savoir |
| 29 | En-têtes fragmentés | titre suivi d'une seule ligne, puis saut |
| 30 | Écriture diff-ancrée *(v2.2.0)* | Cette version introduit, contrairement à avant |

### Spécifiques au français

| N° | Pattern | Mots-clés |
|----|---------|-----------|
| 31 | Transitions de dissertation | Dans un premier temps, dans un second temps, dès lors |
| 32 | Formules de politesse IA-françaises | Je me permets, N'hésitez pas à me solliciter |
| 33 | Sur-structuration | liste à puces pour ce qui devrait être un paragraphe |
| 34 | Nominalisation excessive | la mise en œuvre de, la réalisation de, l'amélioration de |
| 35 | Inflation modale | il est évident que, il semblerait que, force est de constater |
| 36 | Conclusion formelle | En conclusion, Pour conclure, Il ressort de cette analyse |

---

## Version history

| Version | Base | Changements |
|---------|------|-------------|
| 2.3.0 | blader/humanizer v2.7.0 | Section anti-détection : TTR, diversité syntaxique, paragraph burstiness, imperfections contrôlées (cible < 25% Compliatio) |
| 2.2.1 | blader/humanizer v2.7.0 | Mode interactif groupé (1 message au lieu de 3), `--aggressive` avec critères concrets, "Personnalité et âme" compressée |
| 2.2.0 | blader/humanizer v2.7.0 | Pattern #30 (diff-anchored writing), tirets → règle dure, #21 élargi au langage spéculatif |
| 2.1.0 | blader/humanizer v2.5.1 | Mode interactif (3 questions avant lancement), flag `--aggressive` |
| 2.0.0 | blader/humanizer v2.5.1 | Version initiale — 35 patterns (29 EN + 6 FR), 5 profils de voix, 3 modes, audit structuré |

---

## Crédits

- [blader/humanizer](https://github.com/blader/humanizer) (MIT) — 30 patterns originaux, base v2.7.0
- [Aboudjem/humanizer-skill](https://github.com/Aboudjem/humanizer-skill) (MIT) — modes, profils de voix, burstiness/perplexité
- [Wikipedia:Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) — référence de base
- ---

---

## Mode Académique (Mémoires & Thèses)

Voir [`ACADEMIA.md`](ACADEMIA.md) pour le prompt spécialisé Compilatio dédié aux travaux universitaires (Master/Doctorat).

**Utilisation recommandée :**
- `--voice professionnel` ou `--voice technique`
- Optionnellement `--aggressive` (à utiliser avec modération sur les textes très théoriques)

Ce mode doit être employé **section par section** comme indiqué dans le fichier.

---


## Mode Académique (Mémoires & Thèses)

Voir le fichier [`ACADEMIA.md`](ACADEMIA.md) pour le prompt spécialisé Compilatio.  
Ce mode est conçu pour les travaux universitaires longs et doit être utilisé section par section.

**Recommandation** : `--voice professionnel --aggressive` (ou sans aggressive pour les parties très théoriques).
