# CivicSpaces

An open-source framework for sustainable urban planning combining citizen participation, lightweight spatial analysis and transparent decision-making.

## Project Description

CivicSpaces provides an interactive map where residents can submit feedback, explore planned projects and understand urban dynamics through Space Syntax visualisations. Cities and planners can compare scenarios, cluster citizen input with simple AI tools, identify hotspots and assess supply-chain risks for mobility and energy projects.

Through a modular plugin system, researchers, NGOs and developers can extend the platform with analytical modules. CivicSpaces lowers barriers for digital participation and supports more data-informed and inclusive planning.

## Societal Challenge

Cities struggle with fragmented participation and low transparency. Mobility flows, heat risks or infrastructure delays are often accessible only to specialists, while municipalities lack affordable, open tools that combine spatial analysis with structured feedback.

CivicSpaces provides a map-based framework that clusters citizen input, visualises simple spatial metrics and helps planners compare alternatives more clearly. It does not aim to automate decisions but improves shared understanding and dialogue.

## Target Audience

Citizens, urban departments, planning firms, energy providers, NGOs, universities, research groups.

## Related Approaches

- Proprietary GIS tools: powerful but closed and expensive  
- Participation platforms: limited spatial analysis  
- Space Syntax tools: academic and not integrated with participation  

CivicSpaces provides an open, plugin-driven framework combining map-based feedback, spatial indicators and sustainability modules.


## Technical Implementation

- **Frontend**: React + TypeScript  
- **Backend**: Node.js or Spring Boot  
- **Database**: PostgreSQL/PostGIS  
- **Maps**: MapLibre / Leaflet  

A plugin engine allows modules—such as SpaceSyntaxBasic or CitizenFeedback—to be dynamically registered. Space Syntax serves as an example of integrating algorithmic spatial analysis as an optional plugin.

Citizen feedback is processed via lightweight embedding-based clustering. All components communicate through REST or GraphQL APIs. The architecture demonstrates how cities, NGOs and researchers can extend the system without modifying the core.

## Architecture Overview

### Core Components
```
CivicSpaces Core
      |
      +-- Plugin Loader
      |         |
      |         +-- load("SpaceSyntaxBasic")
      |         +-- load("CitizenFeedback")
      |
      +-- Map Engine (MapLibre)
      |
      +-- Data API (Supabase/Postgres)
```

### Citizen Feedback Processing
```
Citizen Feedback Layer
       └── GeoPoint
       └── Text
       └── Photo (optional)
               │
               ▼
        Embedding Model
               │
               ▼
       Clustering Engine (AI)
               │
               ▼
       Thematic Groups (Heatmap)
            │     │     │
            │     │     └─ "PV shortages"
            │     └─ "Battery delays"
            └─ "Heat pump waiting times"
```

# “Embedding Model” in the context of CivicSpaces

An embedding model converts text (citizen comments) into numerical vectors — 
a mathematical representation that captures meaning (“semantics”).  
This allows the system to automatically detect, cluster, and group similar content.

## Why do we need embeddings in CivicSpaces?

Citizen feedback often appears as free text:

- “PV installer has a three-month waiting time”
- “Photovoltaic technician unavailable”
- “Solar panels delayed again”

An embedding model recognises that these statements share similar meaning  
→ they belong to the group **“PV shortages”**.

This also works across languages (German / English / Chinese).

## What does the model actually do?

It transforms each text into a high-dimensional vector, for example:

"I need a charging point" → [0.21, -0.13, 0.88, ...]  
"The EV station is missing" → [0.22, -0.15, 0.85, ...]

Vectors expressing similar meaning lie close together.  
These vectors then enter the clustering engine, forming thematic groups:

- “PV shortages”
- “Battery delivery delays”
- “Heat pump waiting times”
- “Dangerous crossings”
- “Need more shading / trees”

## Which models could we use?

### 1) Lightweight (local, browser/server)

- SentenceTransformers MiniLM  
- MPNet-base-v2  
- bge-small-en / bge-m3 (multilingual)

→ fast, can run offline, ideal for prototype

### 2) High-quality (API-based)

- OpenAI text-embedding-3-small  
- Jina Embeddings  
- Cohere Embed  

→ better accuracy, but requires API  
→ for Prototype Fund: prefer **local + open-source alternative**

## Potential Use Cases

### A) Shading proposals (trees / shelters)
Citizens can propose new trees or shading structures through a simple map interface. Their suggestions appear as points or polygons in a shared layer. Planners combine these inputs with Space Syntax indicators such as footfall and connectivity to identify the locations where shading would have the highest impact.

### B) PV systems, EV charging and heat pumps
Planners analyse where PV installations are feasible, where EV charging points are needed, or where citizens report long waiting times for heat pumps. The CitizenFeedback plugin clusters these reports (e.g., "PV shortages", "installer unavailable", "heat pump delays") and overlays them with basic supply‑chain information. This highlights hotspots where infrastructure demand and procurement bottlenecks overlap.

### C) New cycling infrastructure
Municipalities visualise several alternative route options, apply basic Space Syntax analysis to understand movement flows and cluster citizen comments on dangerous crossings. This leads to clearer evidence for decision-making, more transparent planning processes and higher public acceptance.

## Project Goals

- Transparent and participatory planning  
- Accessible spatial analysis for cities and citizens  
- Evidence-informed scenario comparison  
- Lower barriers for digital participation  
- Extensible research & planning platform  

## Planned Milestones

- Core framework: plugin loader, map engine, base schema  
- Basic map component with example data  
- SpaceSyntaxBasic plugin  
- CitizenFeedback plugin  
- Demo instance (Hamburg-Altona)  
- Documentation: API + plugin guide  

## Team

### Mei Yang — Urban Research & Space Syntax Lead
Architect, PhD researcher in Space Syntax and sustainable urban design

### Bernd Fruechtnicht — Technical Architect & Lead Developer  
Senior software engineer (30+ years)

## Publications

- [Zero Carbon: English/Chinese Presentation](https://github.com/bernd-fruechtnicht/civicspaces/raw/main/pdfs/zero_carbon_en_cn.pdf)

## License

MIT License.

## Contact

Contact the team via GitHub.
