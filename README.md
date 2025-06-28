# Phoenix - E80 Autonomous Warehouse Solution

Phoenix is a warehouse automation system developed for E80 Group to manage LGV (Laser-Guided Vehicle) workflows at scale. It automates pallet handling across unloading, storage, and reloading processes, operating 15+ LGVs and processing over 10,000 pallets weekly. The solution combines real-time 3D simulation with backend orchestration and intelligent multi-agent pathfinding to reduce manual intervention by 70% and boost routing efficiency by 50%.

## Features

- **Autonomous LGV Workflows**: End-to-end automation of unloading, storage, and truck reloading.
- **Intelligent Pathfinding**: Optimized A* search with conflict avoidance and dynamic agent awareness.
- **Multi-Agent Behavior Simulation**: Mesa-powered modeling for coordination and scenario testing.
- **Real-Time 3D Simulation**: Unity-based visualization of warehouse operations and LGV behavior.
- **Configurable Scenarios**: Customizable warehouse layouts and LGV parameters.
- **Backend Integration**: FastAPI enables low-latency communication between logic and simulation.

## Tech Stack

### Backend
- **Python** – Core logic for LGV coordination and system control.
- **ASP.NET** – Integration layer for industrial interfacing.
- **FastAPI** – Real-time data exchange across simulation and backend services.

### Simulation
- **Unity (C#)** – Interactive 3D modeling of warehouse and LGV tasks.
- **Mesa** – Multi-agent simulation library for behavior modeling and testing.

### Algorithms
- **A* Search Algorithm** – High-efficiency pathfinding with dynamic route optimization.

## Team

<div align="center">
  <img src="images/Phoenix_collaborators.jpg" width="518" />
</div>
