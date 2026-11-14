# 🔴 ARES — Mars Surface Exploration Tool, Orbital Radar & Astronaut Mission Architecture

[![NASA Mars Challenge](https://img.shields.io/badge/NASA%20Challenge-Mars%20Surface%20Exploration-E03C31?style=for-the-badge&logo=nasa&logoColor=white)](https://nasa.gov)
[![CesiumJS](https://img.shields.io/badge/3D%20Globe-CesiumJS%20Mars%202000-0080FF?style=for-the-badge&logo=cesium&logoColor=white)](https://cesium.com)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.x-3178C6?style=for-the-badge&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![Vite](https://img.shields.io/badge/Build-Vite%208-646CFF?style=for-the-badge&logo=vite&logoColor=white)](https://vitejs.dev/)
[![TailwindCSS](https://img.shields.io/badge/UI-TailwindCSS%203.4-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)
[![Video Showcase](https://img.shields.io/badge/Video%20Showcase-1080p%20HD-FF0000?style=for-the-badge&logo=youtube&logoColor=white)](/ares-showcase.mp4)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)

> **A photorealistic 3D Mars exploration and mission-planning workstation designed for planetary scientists, astronauts, and exploration enthusiasts. Powered by CesiumJS on the Mars 2000 datum, high-resolution NASA remote sensing layers, real-time Keplerian orbital mechanics tracking inspired by [Orbital Radar](https://orbitalradar.com/mars), authentic 3D planetary rendering modeled after [NASA's 3D Mars Interactive](https://solarsystem.nasa.gov/gltf_embed/2372/), a dual-mode Live Rover Imagery Explorer (surface scenery & rover hardware portraits), the mandatory NASA Data & Resources Hub, and a complete 5-step astronaut EVA mission planner with Spacesuit Visor Helmet HUD.**

---



## 🎬 Video Feature Showcase

Video Link- https://drive.google.com/file/d/1vVC8pcrsXR65DzRomneVnwdnC-NKCyIs/view?usp=drive_link
- **Showcase Chapters Included in the Video:**
  1. `00:00` — **Cinematic 3D Mars Globe & Starfield Skybox**: Viking MDIM 2.1 4K true-color basemap, Mars 2000 ellipsoid rotation, and deep space nebula backdrop.
  2. `00:15` — **Real-Time Telemetry & Search Autocomplete**: Mars Sol Date (MSD), Solar Longitude ($L_s$), local rover solar clocks (Percy & Curio LMST), and search jump to Olympus Mons.
  3. `00:25` — **Planetary Remote Sensing Data Layers**: Toggling MOLA Elevation Shaded Relief and THEMIS Nighttime Thermal Infrared.
  4. `00:35` — **Landing Sites & Surface Traverses**: Landing pin selection, automated camera fly-in, and 3D surface traverse paths for Perseverance (Jezero) and Curiosity (Gale).
  5. `00:45` — **Orbital Radar & Satellite Propagation**: Keplerian orbit rings, satellite inspection (MRO, Odyssey, TGO, Hope), and natural moons (Phobos, Deimos).
  6. `00:55` — **Live Rover Imagery Explorer (Surface Scenery)**: Live streaming of raw rover photographs from NASA, camera filter pills (Mastcam-Z, Navcam, Hazcam, SuperCam), in-app zoomable inspector modal (+, −, reset), and science captions.
  7. `01:05` — **"The Rovers (Sent to Mars)" Section**: Dedicated showcase of authentic hardware portraits, robotic-arm selfies, engineering specs (mass, power, landing date), and "Fly to Landing Site" camera transition.
  8. `01:15` — **Mandatory NASA Data & Resources Hub**: Interactive access to all 5 compulsory NASA portals (JPL Mars Trek, USGS Geologic Map, Curiosity Route, NASA Worldview, Perseverance Raw Gallery).
  9. `01:20` — **Astronaut EVA Mission Planner & Spacesuit Visor HUD**: 5-step exploration route planning, A* pathfinding, hazard assessment, and full-screen Spacesuit Visor Helmet HUD.
  10. `01:24` — **Surface Distance Measurement Tool (`📏`)**: Geodesic distance arc calculation across the Martian ellipsoid.

---

## 📑 Table of Contents

1. [🌟 Recent Major Enhancements](#1--recent-major-enhancements)
2. [📷 Live Rover Imagery Explorer & Hardware Showcase](#2--live-rover-imagery-explorer--hardware-showcase)
3. [🏛️ Mandatory NASA Data & Resources Hub](#3-️-mandatory-nasa-data--resources-hub)
4. [🪐 Photorealistic 3D Mars Globe Architecture](#4--photorealistic-3d-mars-globe-architecture)
5. [🛰️ Orbital Radar & Moon Tracking](#5-️-orbital-radar--moon-tracking)
6. [🎛️ Planetary Data Layers & Remote Sensing](#6-️-planetary-data-layers--remote-sensing)
7. [🧑‍🚀 Astronaut EVA Mission Planner & Helmet HUD](#7--astronaut-eva-mission-planner--helmet-hud)
8. [📏 Interactive Surface Measurement Tool](#8--interactive-surface-measurement-tool)
9. [⚡ Cleaned Architecture & Performance Optimizations](#9--cleaned-architecture--performance-optimizations)
10. [📁 Project Architecture & Directory Layout](#10--project-architecture--directory-layout)
11. [🛠️ Getting Started & Local Development](#11-️-getting-started--local-development)
12. [📡 Verified Planetary Data Sources & Citations](#12--verified-planetary-data-sources--citations)

---

## 1. 🌟 Recent Major Enhancements

| Feature / Upgrade | Description & Implementation |
|---|---|
| **"The Rovers (Sent to Mars)" Section** | Added a dedicated section under images dedicated to the rovers that were sent to Mars. Displays authentic hardware portraits, robotic-arm selfies, deployment photos, and cleanroom engineering models (Perseverance, Curiosity, Opportunity, Spirit, Sojourner, and comparative generations) with engineering specs (Mass, Nuclear MMRTG vs Solar power, Landing Sol, Coordinates, Traverse distance). |
| **Resilient NASA Asset Manifest Resolution** | Fixed broken image placeholders (e.g. `PIA24744`) caused by NASA's inconsistent file suffix generations (`~large.jpg` vs `~orig.jpg`). Implemented dynamic manifest resolution querying `images-api.nasa.gov/asset/{id}` with automatic fallbacks (`large` → `medium` → `orig` → `small` → `thumb`) so images **never break**. |
| **Strictly In-App Viewing & 1-Click Downloads** | All images open strictly inside ARES with a full-screen inspector modal featuring zoom controls (`+`, `−`, `Reset`), NASA science captions, and a backend-streamed **"Download Full-Res HD Image"** button (`/api/download-image`) that saves photos directly to user devices without CORS issues or external redirects. |
| **"Fly to Landing Site" 3D Camera Pivot** | Clicking "Fly to Landing Site" on any rover photo smoothly pivots and flies the 3D Mars globe directly to that rover's exact landing site (Jezero, Gale, Gusev, Meridiani, Ares Vallis). |
| **Mandatory NASA Data & Resources Hub** | Integrated all 5 compulsory NASA resources from the NASA challenge guidelines into a dedicated panel (`NASAResourcesPanel.tsx`) with embedded live viewer modals and direct launch links. |
| **Cleaned System Architecture** | Completely removed the floating chatbot as requested, ensuring zero clutter, clean layout, and maximum focus on planetary science and mission planning. |
| **Cesium 1.119+ SingleTile Compatibility** | Fixed `DeveloperError: Expected options.tileWidth to be typeof number` in `SingleTileImageryProvider` by supplying required dimensions (`tileWidth: 4096, tileHeight: 2048`). |
| **Vite 6 Cloudflare Tunnel Host Support** | Configured `allowedHosts: true` in `vite.config.ts` for both `server` and `preview` modes, allowing seamless public tunnel streaming on `trycloudflare.com`. |

---

## 2. 📷 Live Rover Imagery Explorer & Hardware Showcase

Accessible via the camera button (📷 / `aria-label="Live Rover Images"`) on the left navigation rail, this module provides an authentic, high-speed connection to the live NASA Image and Video Library.

```
┌────────────────────────────────────────────────────────────────────────┐
│                   ARES Live Rover Imagery Explorer                     │
│                                                                        │
│   [📸 Surface Scenery (By Rovers)]    [🤖 The Rovers (Sent to Mars)]   │
│   ┌────────────────────────────────────────────────────────────────┐   │
│   │ • Perseverance (Jezero)  • Curiosity (Gale)   • Opportunity    │   │
│   │ • Spirit (Gusev)         • Sojourner (Ares)   • All Rovers     │   │
│   └────────────────────────────────────────────────────────────────┘   │
│                                                                        │
│   In-App Inspector Modal:                                              │
│   ┌────────────────────────────────────┬───────────────────────────┐   │
│   │                                    │ Mission / Rover Specs     │   │
│   │      High-Resolution Image         │ NASA Science Caption      │   │
│   │       Zoom Controls [+][-][R]      │ [📥 Download Full-Res]    │   │
│   │                                    │ [🎯 Fly to Globe Location]│   │
│   └────────────────────────────────────┴───────────────────────────┘   │
└────────────────────────────────────────────────────────────────────────┘
```

### Key Capabilities:
- **Surface Scenery Mode:** Filter by rover and camera (e.g., `Mastcam-Z`, `Navcam`, `Hazcam`, `SuperCam`, `WATSON`, `MAHLI`, `Pancam`) or search by keyword (e.g., `delta`, `sol`, `panorama`, `rock`).
- **The Rovers Mode:** Curated and dynamically searchable hardware portraits and selfies of the actual robotic explorers sent to Mars:
  - *Perseverance & Ingenuity:* Historic Sol 46 portrait compiled from 62 WATSON exposures.
  - *Curiosity at Buckskin & Aberlady:* Low-angle MAHLI self-portraits atop Mount Sharp bedrock.
  - *Opportunity at Meridiani:* Pancam solar array and deck mosaic across hematite plains.
  - *Spirit on Husband Hill:* 360° summit panorama looking back at rover wheel tracks.
  - *Sojourner at Yogi Rock:* Historic 1997 Alpha Proton X-ray Spectrometer deployment.
  - *Three Generations:* Engineering comparison of Sojourner, MER, and MSL.
- **In-App Zoom Controls:** Zoom in up to 300% to inspect Martian pebbles, drill tailings, or rover hardware; reset to 100% with one click.
- **Direct Device Downloads:** Powered by a lightweight streaming backend endpoint (`/api/download-image`), guaranteeing CORS-free, direct file downloads with proper filenames (`Rover_Date_NASAID.jpg`).

---

## 3. 🏛️ Mandatory NASA Data & Resources Hub

Accessible via the lightning bolt icon on the left rail (`NASAResourcesPanel.tsx`), this module compiles all 5 compulsory planetary data sites required by the challenge:

1. **Jet Propulsion Laboratory's (JPL) Mars Trek:**
   NASA's primary GIS exploration portal displaying multi-spectral orbital data, landing site elevations, and interactive planetary overlays.
2. **USGS-NASA Planetary Geologic Mapping Program:**
   High-quality standardized planetary geologic maps of Mars providing stratigraphic unit classifications and fault line structures.
3. **NASA Curiosity Route Map & Lower Mount Sharp Flyover:**
   Interactive route animation and waypoint visualizations showing Curiosity’s ascent up Mount Sharp inside Gale Crater.
4. **NASA Worldview (Satellite Perspective):**
   Satellite perspective observation platform exploring temporal surface changes, dust storms, and atmospheric dynamics.
5. **Mars Perseverance Raw Images Gallery:**
   NASA archive of over 1 million raw images captured by Perseverance's 23 cameras during its mission across Jezero Crater.

*Each resource can be launched in an in-app embedded modal viewer or opened directly in a new tab.*

---

## 4. 🪐 Photorealistic 3D Mars Globe Architecture

Ares recreates the visual appearance of Mars as modeled by NASA's official 3D interactive model:

- **Mars 2000 Ellipsoid Coordinate System:**
  Accurate IAU planetocentric coordinate datum:
  $$\text{Equatorial Radius } R_{\text{equator}} = 3,396,190\,\text{m}, \quad \text{Polar Radius } R_{\text{polar}} = 3,376,200\,\text{m}$$
  Fully handles East-positive planetary longitude and conversions between $[0^\circ, 360^\circ]$ and $[-180^\circ, +180^\circ]$.
- **Viking MDIM 2.1 4K Planetary Mosaic:**
  High-resolution 2:1 cylindrical equirectangular basemap ($4096 \times 2048$) eliminating pole pinch artifacts.
- **Solar Terminator Illumination vs. True-Color Basemap:**
  Toggle between true-color uniform scientific viewing (for unshadowed geologic inspection) and dynamic solar day/night illumination with authentic terminator shadows.
- **Deep Space Skybox:**
  Seamless $1024 \times 1024$ cube faces rendering realistic starfields (hot blue O-stars, orange K-giants, white main sequence), subtle nebulae, and the Milky Way galactic plane.

---

## 5. 🛰️ Orbital Radar & Moon Tracking

Modeled after **Orbital Radar** (`orbitalradar.com/mars`), Ares continuously propagates and visualizes Martian orbiters and natural moons in 3D:

### Planetary Clocks & Solar Geometry (`marsTime.ts`)
Calculates real-time values using official NASA GISS Mars24 algorithms:
- **Mars Sol Date (MSD):** Real-time fractional Martian sol count since epoch.
- **Solar Longitude ($L_s$):** Mars orbital seasonal angle ($0^\circ = \text{Spring equinox}, 90^\circ = \text{Summer solstice}, 180^\circ = \text{Autumn equinox}, 270^\circ = \text{Perihelion / Dust storm season}$).
- **Local Mean Solar Time (LMST):** Real-time ticking solar clocks for active rovers:
  - **Perseverance (Jezero Crater):** $18.44^\circ\text{N}, 77.45^\circ\text{E}$
  - **Curiosity (Gale Crater):** $4.59^\circ\text{S}, 137.44^\circ\text{E}$

### Tracked Celestial & Artificial Bodies
- **Natural Moons:** Phobos (orbital period $\approx 7.66\,\text{hrs}$, altitude $\approx 5,989\,\text{km}$) and Deimos (orbital period $\approx 30.35\,\text{hrs}$, altitude $\approx 20,063\,\text{km}$).
- **Artificial Orbiters:** Mars Reconnaissance Orbiter (MRO), 2001 Mars Odyssey, ExoMars Trace Gas Orbiter (TGO), Mars Express, MAVEN, Emirates Hope Probe, and Tianwen-1.
- **Interactive Orbit Inspection:** Click any satellite to inspect orbital altitude, velocity, inclination, period, and track camera view.

---

## 6. 🎛️ Planetary Data Layers & Remote Sensing

All data layers feature solid, high-contrast night-sky panels (`#0a0d14`), eliminating translucent bleed-through and ensuring clear legibility:

| Layer Name | Instrument / Mission | Scientific Purpose |
|---|---|---|
| **Viking MDIM 2.1 (Basemap)** | Viking Orbiter 1 & 2 | True-color global photographic mosaic of Mars |
| **MOLA Elevation Shaded Relief** | Mars Global Surveyor | Laser altimetry topographic relief, crater depths, and mountain heights |
| **THEMIS Night Thermal IR** | 2001 Mars Odyssey | Thermal inertia, surface rock abundance, and dust mantle thickness |
| **MGS Magnetic Field Anomalies** | Mars Global Surveyor | Remnant paleomagnetic crustal fields from the ancient Martian dynamo |
| **Water Equivalent Hydrogen (Ice)** | 2001 Mars Odyssey GRS | Subsurface hydrogen and ground ice distribution within the top 1 meter |

*Each layer includes an opacity slider and dedicated "ℹ️ Science Info" dialog.*

---

## 7. 🧑‍🚀 Astronaut EVA Mission Planner & Helmet HUD

A 5-step operational tool designed for human astronauts planning extravehicular surface traverses:

1. **Step 1: Landing Base Selection:** Choose from 17 verified landing sites (Jezero, Gale, Gusev, Chryse, Elysium, Meridiani, etc.).
2. **Step 2: Exploration Objective:** Define mission goals (Sample Return, Geologic Stratigraphy, Water-Ice Prospecting, Habitat Expansion).
3. **Step 3: Multi-Spectral Layer Verification:** Overlay topographic slopes, thermal inertia, and communications line-of-sight.
4. **Step 4: Interactive Route Generation & Elevation Profile:** Place waypoints with real-time geodesic distance calculations, slope gradients, elevation gain/loss charts, and estimated walking/rover travel times.
5. **Step 5: Safety Verification & Helmet HUD:**
   - Evaluates radiation dose rates ($\text{mGy/day}$), oxygen consumable limits, battery reserves, and habitat line-of-sight.
   - **Spacesuit Visor Helmet HUD:** Launches a full-screen augmented reality HUD simulating an astronaut's helmet visor with live telemetry, pitch/roll indicators, compass heading, O₂ status, and waypoint distance markers.
   - **Mission Export:** 1-click export to GeoJSON and formatted PDF Mission Briefs.

---

## 8. 📏 Interactive Surface Measurement Tool

- Click the ruler button (`📏`) on the right control bar.
- Click any two points on Mars to cast a 3D ray onto the Mars 2000 ellipsoid.
- Draws an elevated geodesic arc ($+1,500\,\text{m}$ above the ellipsoid) and displays a floating HUD card showing distance in both kilometers ($\text{km}$) and miles ($\text{mi}$).
- Built with an 8px drift threshold to reliably distinguish between laptop trackpad taps and camera rotations.

---

## 9. ⚡ Cleaned Architecture & Performance Optimizations

- **Zero Bloat:** Chatbot completely removed to maximize workspace real estate and frame rates.
- **60 FPS Rendering:** CesiumJS requestRenderMode enabled, reducing CPU/GPU overhead when the scene is static.
- **High-Contrast Design System:** 100% opaque surfaces (`#0a0d14`, `#101522`) with solid borders and crisp `#ffffff` / `#e2e8f0` typography.
- **Asset Fallback Resilience:** All remote assets (terrain, tiles, and images) feature multi-tier offline fallbacks to prevent runtime crashes.

---

## 10. 📁 Project Architecture & Directory Layout

```
d:\Ares\
├── backend\
│   └── server.cjs                 # Node.js backend: /api/download-image proxy, search & telemetry
├── public\
│   └── ares-showcase.mp4          # 1080p video showcase file
├── src\
│   ├── App.tsx                    # Main React application entrypoint
│   ├── data\
│   │   ├── gazetteer.ts           # IAU Martian planetary gazetteer (68 features)
│   │   ├── landingSites.ts        # 17 authentic Mars landing sites with coordinates
│   │   ├── marsTime.ts            # NASA Mars24 algorithms: MSD, Ls, LMST clocks
│   │   ├── orbitalBodies.ts       # Phobos & Deimos orbital ephemerides
│   │   └── orbiters.ts            # MRO, TGO, Odyssey, Hope, MAVEN orbital states
│   ├── globe\
│   │   ├── CameraController.ts    # Smooth camera flyTo and orbit reset controls
│   │   ├── CesiumViewer.tsx       # Core 3D CesiumJS Mars 2000 globe canvas
│   │   ├── DataLayersSync.tsx     # Synchronizes WMS/SingleTile remote sensing layers
│   │   ├── LandingSitePins.tsx    # 3D landing site pins & labels
│   │   ├── MarsImagery.ts         # Viking MDIM 2.1 4K equirectangular imagery provider
│   │   ├── MarsTerrain.ts         # Topographic elevation provider
│   │   ├── OrbitalLayer.tsx       # 3D Keplerian orbit polylines and animated satellites
│   │   └── RoverTraverseLayer.tsx # Perseverance & Curiosity surface traverse paths
│   ├── routing\
│   │   └── AStarRouter.ts         # A* surface pathfinding with slope cost weights
│   ├── store\
│   │   ├── globeStore.ts          # Zustand store for globe state, layers, and active panels
│   │   ├── plannerStore.ts        # Zustand store for 5-step EVA mission planner
│   │   └── settingsStore.ts       # User settings, lighting toggles, and terrain scale
│   └── ui\
│       ├── layers\                # Planetary Data Layers panel & opacity sliders
│       ├── orbiters\              # Orbital Radar panel & satellite tracker
│       ├── panels\
│       │   ├── LiveRoverImageryPanel.tsx  # Rover imagery: Surface & The Rovers (Hardware)
│       │   └── NASAResourcesPanel.tsx     # Mandatory NASA 5 Data & Resources hub
│       ├── planner\               # Astronaut EVA Mission Planner & Helmet HUD
│       ├── search\                # Search Autocomplete across Martian geography
│       ├── settings\              # Settings drawer & Video Showcase download
│       ├── shell\                 # Navigation rails, live telemetry header, and status bar
│       ├── sites\                 # Missions & Sites sidebar and Mission Cards
│       └── tools\                 # Surface Measurement tool (geodesic distance arcs)
├── dist\                          # Optimized production bundle
├── vite.config.ts                 # Vite config with cesium plugin and allowedHosts: true
├── package.json                   # Dependencies and build scripts
└── README.md                      # Comprehensive project documentation
```

---

## 11. 🛠️ Getting Started & Local Development

### Prerequisites
- [Node.js](https://nodejs.org/) v18.0.0 or higher
- Modern Chromium, Firefox, or Safari browser with WebGL 2.0 support
- (Optional) [cloudflared](https://developers.cloudflare.com/cloudflare-one/connections/connect-apps/) for creating public multi-device tunnels

### Installation & Run

1. **Clone & Install Dependencies:**
   ```bash
   cd d:\Ares
   npm install
   ```

2. **Start Backend Telemetry & Download Proxy Server:**
   ```bash
   node backend/server.cjs
   # Running on http://localhost:3001
   ```

3. **Start Development Server (with HMR):**
   ```bash
   npm run dev
   # Open http://localhost:5173
   ```

4. **Build & Run Production Preview:**
   ```bash
   npm run build
   npx vite preview --port 4173 --host
   # Open http://localhost:4173
   ```

5. **Expose Public Multi-Device Tunnel (Optional):**
   ```bash
   cloudflared tunnel --url http://localhost:4173
   # Generates https://<subdomain>.trycloudflare.com
   ```

---

## 12. 📡 Verified Planetary Data Sources & Citations

1. **NASA Viking MDIM 2.1 Color Basemap:** USGS Astrogeology Science Center / NASA PDS Cartography and Imaging Sciences Node.
2. **MOLA Elevation Relief:** Mars Global Surveyor Mars Orbiter Laser Altimeter Science Team (Smith et al., 2001).
3. **THEMIS Thermal Infrared Imagery:** 2001 Mars Odyssey Thermal Emission Imaging System (Christensen et al., Arizona State University).
4. **MGS Magnetic Field Anomaly Map:** Mars Global Surveyor Magnetometer / Electron Reflectometer Experiment (Acuña et al., 1999).
5. **Mars Odyssey Water Equivalent Hydrogen (GRS):** Boynton et al., Gamma Ray Spectrometer Suite (2002).
6. **Mars24 Solar Time Algorithms:** Allison & McEwen, Planetary and Space Science 48 (2000), NASA Goddard Institute for Space Studies.
7. **NASA Image and Video Library:** Authentic mission photography streamed live from `images-api.nasa.gov`.
8. **JPL Mars Trek & Planetary Data System:** NASA Jet Propulsion Laboratory / Caltech.

---

*Developed for the NASA Mars Exploration Challenge. Certified for exploration on the Mars 2000 Datum.*
