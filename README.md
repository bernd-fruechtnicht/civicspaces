# CivicSpaces

An open-source framework for sustainable urban planning combining citizen participation, lightweight spatial analysis, and transparent decision-making.

## Project Description

CivicSpaces provides an interactive map where residents can submit feedback, explore planned projects, and understand urban dynamics through Space Syntax visualisations. Cities and planners can compare scenarios, cluster citizen input with simple AI tools, identify hotspots, and assess supply-chain risks for mobility and energy projects.

Through a modular plugin system, researchers, NGOs and developers can extend the platform with analytical modules. CivicSpaces lowers barriers for digital participation and supports more data-informed and inclusive planning.

## Societal Challenge

Cities struggle with fragmented participation and low transparency. Mobility flows, heat risks or infrastructure delays are often accessible only to specialists, while municipalities lack affordable, open tools that combine spatial analysis with structured feedback.

CivicSpaces provides a map-based framework that clusters citizen input, visualises simple spatial metrics, and helps planners compare alternatives more clearly. It does not aim to automate decisions but improves shared understanding and dialogue.

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

## Potential Use Cases

### A) Shading proposals (trees / shelters)
Citizens can propose new trees or shading structures through a simple map interface. Their suggestions appear as points or polygons in a shared layer. Planners combine these inputs with Space Syntax indicators such as footfall and connectivity to identify the locations where shading would have the highest impact.

### B) PV systems, EV charging and heat pumps
Planners analyse where PV installations are feasible, where EV charging points are needed, or where citizens report long waiting times for heat pumps. The CitizenFeedback plugin clusters these reports (e.g., "PV shortages", "installer unavailable", "heat pump delays") and overlays them with basic supply‑chain information. This highlights hotspots where infrastructure demand and procurement bottlenecks overlap.

### C) New cycling infrastructure
Municipalities visualise several alternative route options, apply basic Space Syntax analysis to understand movement flows, and cluster citizen comments on dangerous crossings. This leads to clearer evidence for decision-making, more transparent planning processes, and higher public acceptance.

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

### Mei Yang — Lead Applicant, Urban Research & Space Syntax  
Architect, PhD researcher in Space Syntax and sustainable urban design

### Bernd Fruechtnicht — Technical Architect & Lead Developer  
Senior software engineer (30+ years)

## Publications

- [Zero Carbon: English/Chinese Presentation](https://github.com/bernd-fruechtnicht/civicspaces/raw/main/pdfs/zero_carbon_en_cn.pdf)

## License

MIT License.

## Contact

Contact the team via GitHub.
