# Project Structure

This document provides an overview of the structure of the
VECTORFIELD repository and the purpose of its main components.

The repository is organized to make the architecture methodology,
technical documentation, and supporting materials easy to navigate.

---

## Core Project Files

These files define the conceptual foundation of the architecture study.

- **ARCHITECTURE_PRINCIPLES.md**  
  Describes the architectural philosophy and design principles guiding the security architecture.

- **THREAT_MODEL.md**  
  Documents the primary threat scenarios considered in the architecture and the corresponding mitigation strategies.

- **VIDEO_WALKTHROUGH.md**  
  Provides a guided video explanation of the architecture and the design process behind the study.

- **CITATION.cff**  
  Provides citation metadata for the architecture study, enabling
  automatic citation generation by GitHub and academic tools.

---

## Documentation

- **docs/**  
  Contains the detailed technical documentation of the architecture, including:

  - `overview.md` — general overview of the architecture study  
  - `architecture-summary.md` — condensed explanation of the network architecture model  
  - `architecture-decisions.md` — documented architecture design decisions  
  - `architecture-diagram.md` — explanation of the network architecture diagram  
  - `requirements-traceability.md` — traceability from stakeholder requirements to architectural controls  
  - `validation.md` — validation criteria and acceptance goals for the architecture  
  - `soc-readiness.md` — monitoring design and SOC-readiness concept  
  - `references.md` — supporting references and sources used in the study  

---

## Study Publications

- **pdfs/**  
  Contains the published study documents:

  - full architecture study version  
  - condensed portfolio version of the project

---

## Assets

- **assets/**  
  Stores supporting visual and documentation materials used throughout the repository:

  - architecture diagrams  
  - documentation images  
  - project visual assets

  Subdirectories include:

  - `assets/images/` — images used in documentation and presentation materials  
  - `assets/diagrams/` — architecture diagrams and editable design files

---

## Repository Governance

The repository also contains standard governance and project management files:

- `README.md` — main project introduction and repository entry point  
- `LICENSE.md` — licensing terms for the project materials  
- `CHANGELOG.md` — version history of the repository  
- `SECURITY.md` — security disclosure policy  
- `CONTRIBUTING.md` — contribution guidelines  
- `CODE_OF_CONDUCT.md` — community conduct guidelines  
- `SUPPORT.md` — information about supporting the ESKme projects  
- `.gitignore` — repository ignore rules for build artifacts and local files

---

## Repository Layout Overview

A simplified view of the repository structure:

```
README.md
ARCHITECTURE_PRINCIPLES.md
THREAT_MODEL.md
VIDEO_WALKTHROUGH.md
docs/
assets/
pdfs/
```

The documentation in `docs/` contains the detailed architectural documentation,
while the `pdfs/` directory provides the complete published study versions.
