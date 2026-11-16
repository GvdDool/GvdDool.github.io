# #30DayMapChallenge 2026 — Day 16: Collaborative Map

## UN Mappers: Nigeria ↔ Cameroon

An interactive humanitarian crowd-mapping dashboard monitoring cross-border road and settlement digitization along the Nigeria–Cameroon corridor for **HOT Tasking Manager Project #69009**, organized in support of the **#OSMGeoWeek2026 UN Mappers Challenge** (November 16–20, 2026).

- 🌐 **Live Interactive Map:** [https://gvddool.github.io/projects/30dayMapChallenge-2026/day-16/Day16_collaborative_map.html](https://gvddool.github.io/projects/30dayMapChallenge-2026/day-16/Day16_collaborative_map.html)
- 🖼️ **Preview / Snapshot:** `Day-16-LandingPage.png`

---

## What This Folder Does & Architecture

This folder contains a self-contained, client-side web mapping application designed to track and visualize humanitarian volunteer mapping progress in near-real-time:

1. **Collaborative Task Grid Tracking:**
   - Visualizes **401 task squares** covering the remote border corridor between southeast Nigeria (Cross River / Benue) and northwest Cameroon.
   - Categorizes each grid square by volunteer state:
     - 🟩 **Validated (Completed):** Inspected and approved by experienced validators.
     - 🟦 **Mapped by Volunteers:** Digitized features pending validation.
     - 🟧 **Locked / Active:** Currently being edited by a volunteer mapper.
     - ⬛ **Ready to Map:** Awaiting volunteer assignment.

2. **Corridor Infrastructure Layers:**
   - Overlays **934 OSM road segments** providing connectivity across rugged terrain.
   - Highlights **291 settlement place nodes** (Obudu, Sankwala, Akwaya, Benakuma, Wum, Essu).

3. **Dual Pipeline & Resilience:**
   - Queries the live **HOT Tasking Manager API v2** (`tasking-manager-tm4-production-api.hotosm.org/api/v2/projects/69009/tasks/`) on launch.
   - Automatically falls back to high-resolution embedded GeoJSON snapshots if the user is offline or if remote API rate limits occur.

---

## Tech Stack

- **Mapping Engine:** [Leaflet.js](https://leafletjs.com/) (v1.9.4)
- **Data Source:** [Humanitarian OpenStreetMap Team (HOT) Tasking Manager](https://tasks.hotosm.org/projects/69009/instructions) & [UN Mappers](https://maps.un.org/)
- **Basemap:** Esri World Imagery & Dark CartoDB basemap styling
