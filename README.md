# Crew Health Ops

**A 3D health monitor that helps astronauts read their own health, get clear guidance, and act first when Earth is minutes away.**

NASA Space Apps Challenge 2026 (Universal Event) · Challenge: *Create Health Monitoring Software for Astronauts on Space Missions* · Team **Cloud Catalyst** (Edmund Anthony, Nandani Chauhan)

- **Live app:** https://edmundzen.github.io/crew-health-ops/
- **User manual (PDF):** [docs/Crew_Health_Ops_User_Manual.pdf](docs/Crew_Health_Ops_User_Manual.pdf)

> Prototype. Crew members and vital signs are simulated. Not medical advice. Not endorsed by NASA.

## The problem
Long missions expose crews to NASA's five hazards of human spaceflight: space radiation, isolation and confinement, distance from Earth, altered gravity, and a hostile closed environment. On a Mars mission a message to Earth can take up to about 22 minutes each way, so astronauts must assess and act on many health problems themselves.

## What it does
- **3D astronaut with 5 clickable health sites:** head (sleep, mood), forehead (body temperature), heart (heart rate, blood pressure), left arm (blood sugar), dosimeter (radiation). Each is green (OK), amber (Watch) or red (Act).
- **Guidance card for every site:** what it is · which hazard · what to do now · when to escalate, with the NASA source.
- **Alerts that never clear themselves:** Acknowledge or Escalate to the flight surgeon; the reply delay matches the location.
- **Mission timeline:** 30 days of alerts and actions per crew member.
- **60-second self-check:** energy, mood, sleep and symptoms update today's readings.
- **4 crew with personalities** whose habits explain their health stories, and **5 locations** (space station, lunar orbit, Mars transit, Moon base, Mars base) where the astronaut floats or walks.

## NASA data
| Data | Type | Use |
|---|---|---|
| [NASA OSDR RadLab](https://visualization.osdr.nasa.gov/radlab/gui/overview/) – ISS Columbus, DOSTEL 1+2, 1 Mar 2022 (`data/radlab_iss_2022-03-01.txt`) | **Real** | Space-station radiation: ~0.28 mGy/day absorbed dose and the 24-hour dose-rate chart (spikes = South Atlantic Anomaly) |
| [HRP: 5 Hazards](https://www.nasa.gov/hrp/hazards/), [HRP: Risks](https://www.nasa.gov/hrp/risks/), [Human Research Roadmap](https://humanresearchroadmap.nasa.gov/Risks/) | Reference | Hazard and risk wording for the guidance cards |
| Crew vital signs, mood, symptoms | Simulated | Generated with a fixed seed (42) so every demo is identical; labelled in the app |
| Radiation for lunar and Mars settings | Placeholder | Approximate rates, labelled; to be replaced with real data |

Full resource list, including partner-agency links: [`data/DATA.md`](data/DATA.md).

Alert thresholds (Watch / Act) are design choices for this prototype, informed by NASA HRP material; they are not NASA standards or clinical limits.

## How to run
It is a single static page. Open the live link, or download `index.html` and open it in Chrome, Edge or Firefox (internet needed once to load Three.js and fonts).

## Use of AI / Attribution
| Part | AI involvement |
|---|---|
| `index.html` (3D app: scene, astronaut, animations, alert rules, UI) | Written with **Claude** (Anthropic) as a coding assistant, directed and tested by the team |
| 3D visuals and screenshots in the app, deck and manual | **AI-generated with Claude** (procedural 3D graphics); labelled in the app header and on every slide |
| Banner image, user manual (`docs/`), pitch deck layout | Made with AI assistance (Claude); labelled |
| Guidance card text | Written by the team (Nandani Chauhan) from NASA HRP sources; edited for accuracy |
| Data choice and processing | Team selected the NASA RadLab file; daily dose and chart computed from it |
| `data/` | NASA OSDR RadLab export (unchanged) and the team's resource list |

No AI-generated photos are presented as real. NASA data is unmodified apart from the daily-dose calculation.

## Built with
Three.js (3D), plain HTML/CSS/JavaScript, GitHub Pages hosting. Built with Claude as a coding assistant; guidance text written by the team from NASA HRP sources.

## Next steps
Real lunar and Mars radiation data · wearable sensor input · offline storage for the crew · thresholds reviewed with medical input · an Earth version for remote clinics.

## License
MIT
