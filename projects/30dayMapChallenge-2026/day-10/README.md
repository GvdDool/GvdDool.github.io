# #30DayMapChallenge 2026 — Day 10: Prompting Only

## 2026 Seismic Pulse

An interactive real-time earthquake map displaying all **M5.5+ earthquakes in 2026** and calculating geodesic crustal wave arrival rings (P-waves & S-waves) radiating from the year's strongest tremor.

- 🌐 **Live Interactive Map:** [https://gvddool.github.io/projects/30dayMapChallenge-2026/day-10/day_10_prompting_only.html](https://gvddool.github.io/projects/30dayMapChallenge-2026/day-10/day_10_prompting_only.html)
- 🖼️ **Preview:** `day_10_preview.png`

---

## Challenge Specifications & Features

1. **Prompting Only:** The HTML and JavaScript were created entirely through prompt engineering, adhering to the challenge rule.
2. **Live Data Stream:** Fetches live GeoJSON directly from the [USGS Earthquake Hazards Program API](https://earthquake.usgs.gov/fdsnws/event/1/query?format=geojson&starttime=2026-01-01&endtime=2026-12-31&minmagnitude=5.5).
3. **Hypocenter Depth Categorization:**
   - **Shallow (< 70 km):** `#00F5D4` (Cyan)
   - **Intermediate (70–300 km):** `#3B82F6` (Electric Blue)
   - **Deep (> 300 km):** `#A855F7` (Violet)
4. **Seismic Wave Propagation Rings:**
   - Automatically detects the strongest recorded earthquake of 2026.
   - Calculates geodesic concentric rings using Turf.js:
     - **P-Wave arrival (6.0 km/s):** 2 min (720 km), 5 min (1800 km), and 10 min (3600 km)
     - **S-Wave arrival (3.5 km/s):** 2 min (420 km), 5 min (1050 km), and 10 min (2100 km)
5. **Interactive Exploration:**
   - Clicking on any earthquake recalculates seismic propagation rings centered on that specific epicenter.
6. **Robust Dual Basemap:**
   - Inverted dark HOTOSM tile basemap with an underlying TopoJSON vector fallback layer to ensure sharp continental rendering even if tile servers are throttled.

---

## Tech Stack
- [Leaflet.js](https://leafletjs.com/) (v1.9.4)
- [Turf.js](https://turfjs.org/) (v6)
- [TopoJSON Client](https://github.com/topojson/topojson-client)
- [USGS Earthquake API](https://earthquake.usgs.gov/)
