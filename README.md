# prompt-architect

Un skill pour [Claude Code](https://claude.com/claude-code) qui transforme une **idée brute** en **prompt complet**, à travers un vrai dialogue.

Tu donnes juste une idée ou une ébauche. Claude te pose des questions pour comprendre ce que tu veux vraiment, te propose des pistes en expliquant pourquoi, puis écrit le prompt et t'explique ce qu'il contient en langage humain.

## Pourquoi

Quand on lance un projet avec une IA, deux problèmes reviennent :

1. L'idée de départ est floue, donc l'IA comble les trous au hasard.
2. Le prompt contient des choix techniques qu'on ne comprend pas, alors que ce qu'on veut savoir, c'est **ce que ça change** : la maniabilité (comment on s'en sert) et les fonctionnalités (ce que ça sait faire).

## Comment ça marche

1. **Reformulation** : Claude résume ce qu'il a compris et vérifie avec toi.
2. **Dialogue de questions**, en plusieurs tours de 3 à 5 questions :
   - questions de *compréhension* (sur ce que tu as dit),
   - questions d'*exploration* (sur ce qui pourrait te convenir), avec sa recommandation.
   Chaque question vient avec son « je demande ça parce que… », et chaque tour se termine par un récapitulatif.
3. **Propositions** : pour chacune, ce que ça apporte, l'effet sur la maniabilité, pourquoi Claude la propose, et le prix à payer.
4. **Fiche de validation** : objectif, fonctionnalités retenues et écartées, contraintes, critère de réussite.
5. **Prompt complet**, prêt à copier-coller.
6. **Explication en clair** de chaque partie du prompt, et des réglages possibles.

## Installation

Un skill Claude Code est un dossier contenant un fichier `SKILL.md`.

### Pour tous tes projets (recommandé)

```bash
git clone https://github.com/lacitebo/prompt-architect-skill.git
mkdir -p ~/.claude/skills
cp -r prompt-architect-skill/prompt-architect ~/.claude/skills/
```

### Pour un seul projet

```bash
mkdir -p .claude/skills
cp -r prompt-architect-skill/prompt-architect .claude/skills/
```

Ensuite, **relance Claude Code** pour qu'il charge le skill. Tape `/` : `prompt-architect` doit apparaître dans la liste.

## Utilisation

- Manuellement : `/prompt-architect je voudrais un bot qui surveille mon serveur`
- Automatiquement : décris simplement ton idée (« j'ai une idée de projet, aide-moi à faire un prompt »). Claude déclenche le skill d'après sa description.

Réponds aux questions à ton rythme. Tu peux dire « je sais pas » : Claude propose alors des pistes avec sa recommandation. Si tu veux aller vite, dis-le explicitement et il réduira à un seul tour de questions.

## Personnaliser

Le comportement est entièrement dans `prompt-architect/SKILL.md`, en français. Tu peux y changer le nombre de questions par tour, les axes explorés ou la structure du prompt final.

## Mise à jour

```bash
cd prompt-architect-skill && git pull
cp -r prompt-architect ~/.claude/skills/
```

## Licence

[MIT](LICENSE) © 2026 lacitebo
