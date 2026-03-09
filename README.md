# Vue Spatiale · Spatial View

**Interfaces 3D géospatiales pilotées par l'IA — du terrain à l'agent**  
**AI-Driven 3D Geospatial Interfaces — from Terrain to Agent**

> *"The screen no longer waits for the right click. It waits for intent."*  
> — mcp-for-babylon, 2025

---

## En une phrase

Ce dépôt contient le manuscrit en cours de *Vue Spatiale*, un livre technique bilingue (FR/EN) qui documente la conception d'interfaces 3D géospatiales pilotables par un LLM via le **Model Context Protocol (MCP)** — ancré dans une implémentation open source réelle.

*This repository contains the working manuscript of Vue Spatiale, a bilingual (FR/EN) technical book documenting the design of 3D geospatial interfaces drivable by an LLM via the Model Context Protocol (MCP) — grounded in a real open-source implementation.*

---

## La question centrale · The Central Question

> Comment concevoir une interface 3D géospatiale que n'importe quel LLM peut piloter par langage naturel — sans plugins, sans backend supplémentaire, sans sacrifier la précision géodésique ?

> How do you design a 3D geospatial interface that any LLM can drive in natural language — without plugins, without an additional backend, without sacrificing geodetic precision?

**La réponse · The answer:** *Le LLM est le parser. Vous écrivez la grammaire.*  
*The LLM is the parser. You write the grammar.*

---

## Implémentation de référence · Reference Implementation

Ce livre est ancré dans le code réel de :

> **[mcp-for-babylon](https://github.com/pandaGaume/mcp-for-babylon)** — Apache 2.0  
> par [@pandaGaume](https://github.com/pandaGaume)

Les sources sont importées dans `source/mcp-for-babylon/` et `source/spacexr/`.  
Chaque concept du livre est tracé vers une ligne de code qui tourne.

---

## Structure du dépôt · Repository Structure

```
vue-spatiale/
├── work/                        ← Manuscrit en cours
│   ├── introduction.md          ✓ rédigé (bilingue)
│   ├── chapitre_01.md           ✓ rédigé — Les données géospatiales
│   ├── chapitre_02.md           ✓ rédigé — BabylonJS comme canvas géospatial
│   ├── chapitre_03.md           ✓ rédigé — MCP : le protocole
│   ├── PLAN_V3_FINAL.md         ← Plan complet (12 chapitres + annexes)
│   ├── NOTES_EDITORIALES.md     ← Décisions architecturales et rédactionnelles
│   └── NOTES_SOURCES_MCP.md     ← Cartographie des sources de code
│
├── source/
│   ├── mcp-for-babylon/         ← Sources dézippées (référence)
│   ├── spacexr/                 ← Sources SpaceXR (DEM, géodésie, BabylonJS)
│   └── tile3d_beta/             ← POC tile3D beta
│
└── versions/
    └── v0.0_original.docx       ← Brouillon d'origine
```

---

## Plan du livre · Book Outline

### Introduction — L'interface qui vous comprend / The Interface That Understands You ✓

### Partie I — Fondations / Foundations

| # | Titre FR | Title EN | Statut |
|---|----------|----------|--------|
| 1 | Les données géospatiales | Geospatial Data | ✓ rédigé |
| 2 | BabylonJS comme canvas géospatial | BabylonJS as a Geospatial Canvas | ✓ rédigé |
| 3 | MCP : le protocole | MCP — The Protocol | ✓ rédigé |

### Partie II — L'Architecture Behavior/Adapter

| # | Titre FR | Title EN | Statut |
|---|----------|----------|--------|
| 4 | Le browser comme serveur MCP | The Browser as MCP Server | en cours |
| 5 | Le pattern Behavior | The Behavior Pattern | à rédiger |
| 6 | Le pattern Adapter | The Adapter Pattern | à rédiger |

### Partie III — Étendre vers le Géospatial / Extending to Geospatial

| # | Titre FR | Title EN | Statut |
|---|----------|----------|--------|
| 7 | TerrainBehavior | TerrainBehavior | à rédiger |
| 8 | CesiumTerrainBehavior | CesiumTerrainBehavior | à rédiger |
| 9 | Behaviors avancés | Advanced Behaviors | à rédiger |

### Partie IV — Cas d'usage / Use Cases

| # | Titre FR | Title EN | Statut |
|---|----------|----------|--------|
| 10 | Navigation géospatiale par langage naturel | Natural Language Geospatial Navigation | à rédiger |
| 11 | Analyse de terrain par l'IA | AI Terrain Analysis | à rédiger |
| 12 | Le Babylon : démo géospatiale finale | The Babylon — Final Geospatial Demo | à rédiger |

### Conclusion + Annexes A–D

---

## Ce qui rend ce livre unique · What Makes This Book Unique

**🛸 Basé sur du code qui tourne** — Pas de pseudocode. Chaque concept est ancré dans `mcp-for-babylon`, un repo GitHub actif sous Apache 2.0.

**🏗 Un pattern architectural original** — Le duo **Behavior/Adapter** sépare la grammaire MCP (framework-free, testable) de la couche moteur (BabylonJS, Cesium). Ce pattern n'est documenté nulle part ailleurs.

**👥 Double public** — Développeurs IA qui veulent donner une présence spatiale à leur agent. Développeurs 3D/GIS qui veulent exposer leur moteur à un LLM.

**🚀 Fil narratif SF** — Le vaisseau *Babylon* navigue de l'orbite lunaire (Shackleton) à StarBase (Boca Chica). Chaque chapitre s'ouvre sur une scène concrète avant de descendre dans le code.

**🌍 Extensible par construction** — Même grammaire MCP, deux moteurs différents (BabylonJS et Cesium). Le chapitre 8 prouve que le pattern tient à l'échelle.

---

## Technologies documentées · Technologies Covered

| Technologie | Rôle dans le livre |
|-------------|-------------------|
| **BabylonJS** | Moteur 3D WebGL, pipeline terrain, EXT_structural_metadata, double précision |
| **Cesium** | WGS84 natif, 3D Tiles, données terrain mondiales |
| **Model Context Protocol** | Spec Anthropic nov. 2024 / mars 2025 — le protocole central |
| **JSON Schema** | Contrat LLM, signal de pertinence, anti-hallucination |
| **WebSocket / SSE / Streamable HTTP** | Les trois transports MCP documentés |
| **DEM** | ASTER, ALOS/JAXA, NASA LROC (Lune), MOLA (Mars), HiRISE |
| **TypeScript** | Tout le code de référence |

---

## Fil narratif · Narrative Thread

Le livre suit le vaisseau **Babylon** comme démonstrateur géospatial :

| Chapitre | Scène d'ouverture |
|----------|-------------------|
| Introduction | Orbite lunaire basse — cratère Shackleton, flux de données DEM |
| Chapitre 2 | Retour vers la Terre — saut ontologique : du relief à la civilisation |
| Chapitre 3 | Approche finale sur StarBase, Boca Chica — premier ordre en langage naturel |
| Chapitre 12 | Navigation inter-planétaire complète : Terre → Lune → Mars |

---

## Cas d'usage cibles · Target Use Cases

- **Mission planning spatial** — analyse de zones d'atterrissage lunaires/martiennes (Artemis, IDEAS2)
- **Space architecture** — planification d'habitats déployables sur terrain DEM réel
- **Navigation conversationnelle** — GIS, défense, gestion de crise
- **Formation et simulation** — exploration planétaire interactive pour étudiants
- **Interfaces agentiques** — exposer n'importe quel moteur 3D à un agent IA

---

## Statut · Status

```
Manuscrit  :  ~1 750 lignes rédigées (introduction + chapitres 1, 2, 3)
Git        :  20 commits
Version    :  v1.1
Langue     :  Bilingue FR/EN — chapitres complets dans les deux langues
Format     :  Markdown (source) · DOCX (livrable)
```

---

## Contribuer · Contributing

Ce dépôt est principalement un espace de travail pour le manuscrit.  
Les retours techniques sur l'architecture Behavior/Adapter et les corrections factuelles sont bienvenus via **Issues**.

Pour toute collaboration (recherche, édition, cas d'usage) → ouvrir une Issue ou contacter via le profil GitHub.

---

## Licence · License

- **Manuscrit** : © auteur — tous droits réservés pendant la phase de rédaction
- **Code de référence** : [mcp-for-babylon](https://github.com/pandaGaume/mcp-for-babylon) — Apache 2.0
- **Sources SpaceXR** : voir licences dans `source/spacexr/`

---

*Vue Spatiale est un projet actif. Ce dépôt reflète l'état du manuscrit à la date du dernier commit.*
