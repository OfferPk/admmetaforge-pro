# ADMMetaForge Pro (v1.0.0)

> **ITU-R BS.2076-2 Immersive Audio Definition Model (ADM) & EBU Tech 3364 (axml) Workstation & CLI Auditor**

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](http://LICENSE) [![ITU Standard](https://img.shields.io/badge/Standard-ITU--R%20BS.2076--2%20ADM-cyan.svg)](https://www.itu.int/rec/R-REC-BS.2076) [![EBU Standard](https://img.shields.io/badge/Standard-EBU%20Tech%203364%20\(axml\)-indigo.svg)](https://tech.ebu.ch) [![Python](https://img.shields.io/badge/Python-3.8%2B-brightgreen.svg)](https://www.python.org/) ![Platform](https://img.shields.io/badge/Platform-Web%20%7C%20CLI%20%7C%20Docker-purple.svg)

---

## 🎧 Overview

**ADMMetaForge Pro** is an autonomous engineering workstation designed for spatial audio mixers, re-recording sound designers, mastering engineers, and Next-Generation Audio (NGA) delivery technicians. Operating within the **ITU-R BS.2076-2 Audio Definition Model (ADM)** and **EBU Tech 3364 Broadcast Wave Format (`<axml>` chunk)** ecosystem, it delivers:

1. **ITU-R BS.2076-2 ADM XML Synthesis**: Generates compliant, production-ready spatial audio metadata documents modeling the complete 8-level ADM hierarchy: `audioProgramme`, `audioContent`, `audioObject`, `audioPackFormat`, `audioChannelFormat`, `audioBlockFormat`, `audioStreamFormat`, and `audioTrackFormat`.  
2. **Immersive Soundstage & Bed Layouts**: Built-in support for standard loudspeaker beds (7.1.4 and 5.1 DirectSpeakers) and dynamic 3D point objects with time-varying Cartesian coordinates (`X, Y, Z`).  
3. **EBU Tech 3364 (`<axml>`) Container Wrapping**: Automatically packages raw ADM XML payloads for direct embedding into Broadcast Wave Format (`.wav`) files and SMPTE ST 2067-2 IMF packages.  
4. **Interactive 3D Soundstage Monitor**: Real-time graphical visualization of listener position, bed loudspeaker arrays, and dynamic 3D audio object placement within a normalized spatial hemisphere.  
5. **10-Point Normative NGA Auditor**: Automated compliance verification engine validating BS.2076-2 schemas, EBU-ADM ID conventions (`APR_xxxx`, `ACO_xxxx`, `AO_xxxx`), 3D coordinate cube boundaries (`[-1.0, 1.0]`), and PCM stream-to-track linkages.  
6. **Standalone Python CLI (`adm-cli.py`)**: Zero-dependency command-line utility for automated ingest pipelines and mastering automation.

---

## 🚀 Key Features

- **Strict ITU-R BS.2076-2 & BS.2051 Conformance**: Declares official namespaces (`urn:itu:bs:2076:2`) and adheres to standardized speaker labels (`M+030`, `M-030`, `M+000`, `LFE`, `U+045`, etc.).  
- **Dynamic 3D Cartesian Object Positioning**: Full support for point-source objects with precise coordinates (`X` azimuth, `Y` elevation, `Z` height), gain, and diffusivity attributes.  
- **Loudness Integration**: Compliant with ITU-R BS.1770 / EBU R128 integrated loudness metadata (`bsl:loudness="-24.0"` LUFS, `bsl:maxTruePeak="-1.0"` dBTP).  
- **Zero Heavy Runtime Dependencies**: Pure standard library Python 3 CLI and modern HTML5/ES6 web studio.

---

## 🛠 Quick Start

### 1\. Interactive Web Studio

Open `source-code/index.html` directly in any modern web browser:

- Enter Programme Title and choose Bed Configuration (7.1.4 or 5.1).  
- Adjust Dynamic 3D Objects and position coordinates (X, Y, Z).  
- Click **"Synthesize ADM XML"** to view and copy standard XML.  
- Check the **3D Soundstage Monitor** to inspect speaker and object placement.  
- Click \*\*"Wrap in BWF Chunk"\*\* to export for Broadcast Wave files.  
- Run the **10-Point Normative Auditor**.

### 2\. Standalone Python CLI

\# Display CLI help

python3 build/adm-cli.py \--help

\# Generate an ITU-R BS.2076-2 ADM XML file

python3 build/adm-cli.py create master\_mix.xml \--title "Atmos\_Feature" \--layout 7.1.4 \--duration 120

\# Audit an existing ADM XML file

python3 build/adm-cli.py audit master\_mix.xml

\# Wrap ADM XML in EBU Tech 3364 \<axml\> container

python3 build/adm-cli.py axml master\_mix.xml \--out master\_mix\_axml.xml

### 3\. Run Automated Test Suite

python3 test\_adm.py

---

## 📁 Repository Structure

product\_281/

├── README.md                          \# Main project overview & user manual

├── test\_adm.py                        \# 10-point automated unit test suite

├── source-code/

│   ├── index.html                     \# Interactive multi-tab Studio UI

│   ├── adm.css                        \# Spatial audio dark theme stylesheet

│   ├── adm-engine.js                  \# ITU-R BS.2076-2 synthesis engine

│   ├── adm-auditor.js                 \# 10-point normative compliance rules

│   └── app.js                         \# Application event controller & UI glue

├── build/

│   ├── adm-cli.py                     \# Standalone executable CLI utility

│   └── admmetaforge-pro-v1.0.0.zip    \# Complete production release package

├── documentation/

│   ├── ARCHITECTURE.md                \# ITU-R BS.2076 specification deep-dive

│   ├── USER\_GUIDE.md                  \# Comprehensive operational manual

│   └── MONETIZATION\_AND\_MARKETING\_PLAYBOOK.md \# Commercial strategy & pricing tiers

└── screenshots/

    └── adm-studio-preview.svg         \# High-resolution vector preview of GUI

---

## 📄 License

Released under the MIT License. Copyright © 2026 Autonomous Digital Product Factory.