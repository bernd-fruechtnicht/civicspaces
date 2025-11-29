# CivicSpaces

An open-source framework for sustainable urban planning that combines citizen participation, spatial analysis, and transparent decision-making.

## Project Description

CivicSpaces is an open-source framework for sustainable urban planning that combines citizen participation, spatial analysis, and transparent decision-making.

The framework provides an interactive map where residents can submit feedback, explore planned projects, and understand urban dynamics through Space Syntax visualizations.

Cities and planners can compare scenarios, cluster citizen input with simple AI applications, identify hotspots, and assess supply-chain risks for energy and mobility projects.

Through a modular plugin system, researchers, NGOs and developers can extend the platform with new analytical tools. CivicSpaces enables data-driven, participatory and transparent planning for more resilient and sustainable cities.

## Societal Challenge

Many cities struggle to advance sustainable urban development because:

- Public participation is fragmented
- Planning processes are difficult to understand
- Key information — such as mobility patterns, heat risks, or supply-chain delays — remains inaccessible to citizens

This leads to low transparency, reduced trust, and frequent conflicts around projects such as cycling infrastructure, solar expansion, or heating networks. At the same time, municipalities often lack affordable, open digital tools that help them combine citizen feedback with spatial analysis and basic scenario comparisons.

CivicSpaces addresses this challenge by providing an open-source framework that makes urban planning more transparent, participatory, and data-informed.

The project does not claim to solve all problems through technology; instead, it offers a practical tool that helps different actors understand each other better. Citizens can express needs in a structured, map-based way, while cities can identify problem hotspots, compare options, and communicate decisions more clearly.

By lowering the technical and financial barriers for digital participation, CivicSpaces supports fairer, more comprehensible and socially inclusive planning processes.

## Technical Implementation

CivicSpaces will be implemented as a modular, open-source web framework:

- **Frontend**: React + TypeScript
- **Backend**: Node.js or Spring Boot API
- **Database**: PostgreSQL with PostGIS for efficient queries for geometry, routing data, and heatmaps
- **Maps**: MapLibre and Leaflet, enabling customizable layers for projects, feedback points, and Space Syntax visualizations

A core element of the project is a plugin engine that allows external modules—such as Space Syntax analysis or citizen feedback clustering—to be dynamically registered. The initial prototype will reuse and adapt existing open-source libraries for basic Space Syntax metrics, integrating them as a standalone example plugin.

Citizen feedback will be processed through a simple embedding-based clustering pipeline using lightweight, locally runnable models. All components will communicate through clearly defined REST or GraphQL APIs. The goal is a clean, extensible architecture that demonstrates how cities, NGOs or researchers can develop and plug in additional analytical tools without modifying the core system.

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
            │     └─ "Battery delivery delays"
            └─ "Heat pump waiting times"
```

## Project Goals

- Enable transparent, participatory urban planning processes
- Provide accessible spatial analysis tools for cities and citizens
- Support data-driven decision-making through scenario comparison
- Lower technical and financial barriers for digital participation
- Create an extensible platform for urban planning research and tools

## Planned Milestones

- **CivicSpaces Core**: Plugin loader, map engine integration, base schema
- **Basic Map Component**: Layer management and import of example city data
- **SpaceSyntaxBasic Plugin**: Simple connectivity analysis
- **CitizenFeedback Plugin**: Points, text, clustering
- **Demo Instance**: Hamburg-Altona
- **Documentation**: API, plugin guide, setup instructions

## Team

- **Mei Yang** – Lead Applicant, Urban Research & Space Syntax  
  Architect, PhD researcher in Space Syntax and sustainable urban design

- **Bernd Fruechtnicht** – Technical Architect & Lead Developer  
  Senior software engineer (30+ years experience)

## Related Approaches

There are many tools around urban planning, but none covers the combination CivicSpaces aims for:

- **Proprietary GIS / Smart-City suites** (ArcGIS Urban, Bentley, Hexagon) are powerful but closed, expensive and not focused on participatory processes or open plugins.
- **Participation platforms** (CONSUL, adhocracy+) support democratic deliberation but lack spatial analysis, sustainability layers and geospatial modelling.
- **Space Syntax tools** (DepthmapX) are academic, desktop-based and not integrated with citizen participation or sustainability planning.

CivicSpaces fills a missing layer: an open, plugin-driven framework combining map-based feedback, lightweight spatial analysis and sustainability-related modules (PV, mobility, supply chains).

## Target Audience

- Citizens and residents
- Urban management departments (construction bureau, energy department)
- Urban planning and architectural firms
- Energy and charging operation enterprises
- NGO organizations
- Universities and research institutions

## Publications and Materials

### Presentations

- [Zero Carbon: English/Chinese Presentation](pdfs/zero_carbon_en_cn.pdf) - PDF document in the `pdfs/` folder

### Additional Publications

- Additional links and publications will be added here

## License

Project results will be made publicly available under an open-source license (MIT License).

## Contact

For more information about the project, please contact the team via Github.
