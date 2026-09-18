# UAV Gazebo SITL Simulation Environment

Gazebo Sim ve ArduPilot SITL kullanılarak Savaşan İHA için geliştirilen Mini Talon V-tail sabit kanatlı İHA simülasyon ortamı.

## Features
- Mini Talon V-tail UAV simulation
- Gazebo Sim + ArduPilot SITL integration
- ArduPlane fixed-wing simulation
- Single-UAV and multi-UAV scenarios
- Custom runway and environment models
- QR-code mission elements
- Custom ArduPilot parameter files

## Project Structure
```text
models/
worlds/
params/
```

## Requirements
- Gazebo Sim
- ArduPilot SITL
- ArduPlane
- MAVProxy

## Quick Start

### 1. Start Gazebo
```bash
gz sim -r -v4 ~/gazebo/worlds/vtail_runway.sdf
```

### 2. Start ArduPilot SITL
```bash
sim_vehicle.py -v ArduPlane \
  -f JSON:127.0.0.1 \
  --add-param-file="$HOME/SITL_Models/Gazebo/config/mini_talon_vtail.param" \
  --console \
  --map \
  -l 37.978900,41.840400,0,0
```

## Simulation Worlds
- `vtail_runway.sdf` — single-UAV simulation environment
- `vtail_runway2.sdf` — two-UAV simulation environment

## Models
- `mini_talon_vtail` — primary Mini Talon V-tail model
- `mini_talon_vtail2` — second UAV model
- `runway` — runway environment
- `sun` — lighting/environment model
- `qr` and `qr_code*` — QR-code mission elements

## Parameters
- `mini_talon_vtail.param`
- `mini_talon_vtail2.param`

## Use Cases
- Autonomous flight testing
- Guidance and navigation experiments
- Path tracking
- Takeoff and landing testing
- Multi-UAV simulation
- Software-in-the-loop testing
- Computer-vision mission scenarios

## Technologies
| Technology | Purpose |
|---|---|
| Gazebo Sim | Physics and environment simulation |
| ArduPilot | Flight-control software |
| ArduPlane | Fixed-wing flight stack |
| SITL | Software-in-the-loop testing |
| MAVProxy | Console and map interface |
| SDF | Gazebo world description |
| JSON | Gazebo-ArduPilot interface |

## Project Background
Developed for Savaşan İHA autonomous UAV development and simulation studies.

## Author
**Gökhan Eroğlu**

## License
No open-source license has currently been specified.
