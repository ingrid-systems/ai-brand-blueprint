# Plugins van Ingrid Staal

Deze repo is een plugin-marketplace voor Claude. Je voegt de marketplace één keer toe, daarna komen updates automatisch mee.

Op dit moment staat hier één plugin in:

| Plugin | Wat het is |
|---|---|
| `ai-brand-blueprint` | De 5 AI Brand Blueprint-AI's: Personal Brand, Business Blueprint, Offer Snapshot, Dream Client Profile en Brand Voice Guide. |

## Installeren (Claude chat, Claude Desktop, Cowork)

1. Open **Customize** in de linker sidebar en ga naar de tab **Plugins**.
2. Klik bij **Personal plugins** op de "+" en kies **Add marketplace**.
3. Kies **Add from a repository** en plak: `https://github.com/ingrid-systems/claude-plugins`
4. Klik op **Install** bij `ai-brand-blueprint`.

In Cowork open je eerst de Cowork-tab en daarna Customize.

## Installeren (Claude Code)

```
/plugin marketplace add ingrid-systems/claude-plugins
/plugin install ai-brand-blueprint@ingrid-staal
```

## Gebruiken

Typ `/` in een gesprek en kies een van de vijf skills, bijvoorbeeld `aibb-personal-brand` of `aibb-brand-voice-guide`. Aanbevolen volgorde: Personal Brand, Business Blueprint, Offer Snapshot, Dream Client Profile, Brand Voice Guide.

## Een update publiceren

1. Pas het SKILL.md-bestand aan in `plugins/ai-brand-blueprint/skills/<skill-naam>/`.
2. Hoog het versienummer op in **twee** bestanden, met dezelfde waarde:
   - `plugins/ai-brand-blueprint/.claude-plugin/plugin.json`
   - `.claude-plugin/marketplace.json` (het `version`-veld bij de plugin-entry)
3. Commit en push.

Iedereen die de marketplace heeft toegevoegd, krijgt de nieuwe versie zonder iets te downloaden of opnieuw te uploaden.

## Structuur van deze repo

```
.
├── .claude-plugin/
│   └── marketplace.json          catalogus: welke plugins staan hier
└── plugins/
    └── ai-brand-blueprint/
        ├── .claude-plugin/
        │   └── plugin.json       manifest: naam, versie, beschrijving
        ├── README.md
        └── skills/
            ├── aibb-personal-brand/
            ├── aibb-business-blueprint/
            ├── aibb-offer-snapshot/
            ├── aibb-dream-client-profile/
            └── aibb-brand-voice-guide/
```
