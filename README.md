# Phoenix - E80 Autonomous Warehouse Solution

Phoenix is a warehouse automation system developed for E80 Group to manage LGV (Laser-Guided Vehicle) workflows at scale. It automates pallet handling across unloading, storage, and reloading processes, operating 15+ LGVs and processing over 10,000 pallets weekly. The solution combines real-time 3D simulation with backend orchestration and intelligent multi-agent pathfinding to reduce manual intervention by 70% and boost routing efficiency by 50%.

## Features

- **Autonomous LGV Workflows**: End-to-end automation of unloading, storage, and truck reloading.
- **Intelligent Pathfinding**: Optimized A* and Dijkstra pathfinding algorithms with conflict avoidance and dynamic agent awareness.
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
- **Dijkstra’s *Algorithm** – Optimal shortest-path routing for weighted graphs with guaranteed minimum cost.



## Installation

### Prerequisites

- **Python 3.8+** - Required for Mesa simulation and backend services
- **Unity 2021.3 LTS+** - For 3D visualization (optional for simulation-only setup)
- **.NET 6.0+** - For ASP.NET integration layer

### Quick Start

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-org/phoenix-warehouse.git
   cd phoenix-warehouse
   ```

2. **Set up Python environment**
   ```bash
   # Create virtual environment
   python -m venv phoenix-env
   
   # Activate virtual environment
   # On Windows:
   phoenix-env\Scripts\activate
   # On macOS/Linux:
   source phoenix-env/bin/activate
   ```

3. **Install Python dependencies**
   ```bash
   pip install mesa numpy heapq fastapi uvicorn
   ```

4. **Run the simulation**
   ```bash
   python server.py
   ```

5. **Access the simulation**
   - Open your web browser and navigate to: `http://localhost:8521`
   - The Mesa visualization interface will load with interactive controls

### Simulation Configuration

The simulation can be customized through the web interface sliders:

- **Number of Robots**: 5-10 LGVs (default: 6)
- **Initial Total Packages**: 0-200 packages (default: 100)
- **Max Simulation Time**: 100-10,000 steps (default: 1,000)
- **Initial Shelf Load Factor**: 0-3 packages per shelf (default: 1)

### File Structure

```
phoenix-warehouse/
├── agent.py          # LGV, Shelf, Truck, and Package agent definitions
├── model.py          # Main warehouse simulation model
├── server.py         # Mesa visualization server
├── images/           # Project documentation images
└── README.md         # This file
```

### Running Different Components

#### 1. Simulation Only (Mesa)
```bash
python server.py
```
This launches the warehouse simulation with real-time visualization at `http://localhost:8521`.

#### 2. Backend API (FastAPI)
```bash
# If you have FastAPI components
uvicorn main:app --reload --port 8000
```

#### 3. Unity 3D Visualization
- Open the Unity project in Unity Editor
- Load the warehouse scene
- Connect to the Python backend via configured endpoints
- Press Play to start 3D visualization

### Simulation Controls

Once the simulation is running:

1. **Start/Stop**: Use the Start/Stop buttons in the web interface
2. **Step Control**: Step through simulation manually or run continuously
3. **Parameter Adjustment**: Modify robot count, packages, and timing via sliders
4. **Real-time Monitoring**: View charts for:
   - Package distribution across trucks and shelves
   - Total robot movements
   - Delivery performance metrics
   - Battery levels (when implemented)

### Industrial Integration

For deployment in industrial environments:

1. **ASP.NET Integration**: Deploy the ASP.NET components for hardware interfacing
2. **Hardware Configuration**: Configure LGV communication protocols
3. **Safety Systems**: Ensure proper safety interlocks and emergency stops
4. **Performance Monitoring**: Set up logging and monitoring for production use

### Troubleshooting

**Common Issues:**

- **Port 8521 already in use**: Change the port in `server.py` line: `server.port = 8522`
- **Module not found**: Ensure all dependencies are installed in your virtual environment
- **Simulation not loading**: Check browser console for JavaScript errors, try refreshing

**Performance Optimization:**

- Reduce grid size for faster simulation
- Lower the number of LGVs for better performance
- Adjust visualization update frequency in Mesa settings

