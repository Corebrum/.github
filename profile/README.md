# Corebrum

## Decentralized Mesh Supercomputing Platform

Corebrum is a revolutionary decentralized mesh (super)computing platform that brings massively parallel and serialized compute capabilities to robotics, physical AI, and distributed computing applications. By combining compute, network, storage, and memory into a unified mesh architecture, Corebrum enables unprecedented scalability and flexibility for next-generation computing workloads.

## 🚀 Platform Overview

Corebrum provides a complete decentralized computing ecosystem designed for:

- **Robotics & Physical AI**: Real-time sensor processing, object detection, autonomous behaviors, and multi-robot coordination
- **Massively Parallel Computing**: Distribute independent tasks across a mesh network for maximum throughput
- **Serialized Workflows**: Chain compute jobs where output of one becomes input of the next
- **Decentralized Mesh Computing**: Scale from single machines to distributed clusters seamlessly

## 🏗️ Architecture

### Core Components

Corebrum's architecture is built on four fundamental pillars:

#### 1. **Compute**
- **Multiple Runtimes**: Python, Docker, WebAssembly, JavaScript support
- **Parallel Execution**: Independent tasks execute simultaneously across workers
- **Sequential Pipelines**: Chain tasks for complex data processing workflows
- **Stream-Reactive Tasks**: Real-time processing of continuous data streams
- **Task Scheduling**: Intelligent distribution across available workers

#### 2. **Network**
- **Zenoh Integration**: High-performance distributed messaging and discovery
- **Mesh Topology**: Automatic worker discovery and network formation
- **ROS2 Integration**: Native support for ROS2 robots via Zenoh
- **Topic Discovery**: Publish/subscribe to mesh topics for real-time communication
- **Multi-Machine Support**: Seamlessly connect workers across networks

#### 3. **Storage**
- **Persistent Backends**: Filesystem, RocksDB, and InfluxDB support
- **Key-Value Storage**: Distributed storage with namespace organization
- **Time-Series Data**: InfluxDB backend for metrics and temporal data
- **High Performance**: RocksDB backend for production workloads

#### 4. **Memory**
- **In-Memory Caching**: Ephemeral high-speed data access via Zenoh backends
- **Distributed Cache**: Shared memory across the mesh network
- **Real-Time Access**: Low-latency memory operations for hot data

## 🛠️ Components

### Corebrum CLI

The command-line interface for interacting with the Corebrum platform:

- **Task Submission**: Submit compute tasks from files (JSON & YAML), URLs, or interactively
- **Task Monitoring**: Real-time status tracking and result retrieval
- **Worker Management**: Discover and monitor workers across the mesh
- **Storage Operations**: Store and retrieve data from persistent storage
- **Memory Operations**: Access distributed in-memory cache
- **Network Discovery**: Explore mesh topology and topics
- **Web Server**: Launch REST API and Web UI with `corebrum web`

**Quick Start:**
```bash
# Submit a task
corebrum submit --file task.yaml --input '{"number": 8}'

# Monitor task status
corebrum status <task-id> --watch

# Get results
corebrum results <task-id>
```

### CMOS (Corebrum Mesh Operating System)

A Linux-like terminal shell for the decentralized mesh supercomputing platform:

- **Familiar Interface**: Unix-like commands (`ls`, `cd`, `ps`, `kill`, etc.)
- **Virtual Filesystem**: Cluster state accessible through file paths
- **Interactive Shell**: REPL with command completion and history
- **Real-Time Monitoring**: Live job dashboard and cluster status
- **Mesh Operations**: Direct integration with Corebrum mesh via Zenoh

**Quick Start:**
```bash
# Launch CMOS shell
corebrum cmos

# Navigate and explore
CMOS[user@local] > ls /jobs
CMOS[user@local] > netstat
CMOS[user@local] > submit task.yaml
```

### REST API

Complete HTTP API for all Corebrum functions, making the platform accessible from any application:

- **Full API Coverage**: All CLI and CMOS functions available via REST endpoints
- **Interactive Documentation**: Swagger UI for testing and exploring the API
- **Real-Time Streaming**: Server-Sent Events (SSE) and WebSocket support
- **OpenAPI Specification**: Standard OpenAPI 3.0 specification for integration

**Quick Start:**
```bash
# Start web server
corebrum web

# Access API documentation
# http://localhost:6502/api/docs

# Example API calls
curl http://localhost:6502/api/jobs
curl http://localhost:6502/api/netstat
```

### Web UI

Modern browser-based interface for monitoring and managing the Corebrum mesh:

- **Cores Tab**: Real-time worker monitoring with capabilities and load information
- **Tasks Tab**: Monitor all jobs and streams, view results, cancel tasks
- **Messages Tab**: Browse Zenoh topics, filter by type, stream messages in real-time
- **API Tab**: Interactive Swagger UI for testing all endpoints
- **WebSocket Support**: Real-time topic streaming with special handling for ROS2 image topics

**Quick Start:**
```bash
# Start web server (automatically opens browser)
corebrum web

# Access Web UI at http://localhost:6502
```

## 🎯 Use Cases

### Robotics & Physical AI

Corebrum excels at offloading compute-intensive tasks from robots to the mesh supercomputer:

- **Object Detection**: Process camera streams with YOLO and other vision models
- **Person Following**: Track and follow detected persons in real-time
- **Multi-Robot Coordination**: Coordinate multiple robots in formation
- **Sensor Processing**: Monitor sensor data and trigger autonomous behaviors
- **Real-Time Control**: Stream-reactive tasks for continuous robot control

**Example: ROS2 Integration**
```bash
# Publish robot commands
corebrum publish rt/cmd_vel '{"linear":{"x":0.5},"angular":{"z":0}}'

# Subscribe to sensor data
corebrum subscribe rt/camera/color/image_raw
```

### Massively Parallel Computing

Distribute independent tasks across the mesh for maximum throughput:

- **AI Inference**: Run multiple model predictions simultaneously
- **Data Processing**: Process multiple datasets in parallel
- **Scientific Computing**: Distribute computational workloads
- **Monte Carlo Simulations**: Run thousands of independent simulations
- **Machine Learning Training**: Distribute training across multiple workers

### Serialized Workflows

Chain compute jobs for complex data processing pipelines:

- **ETL Workflows**: Extract → Transform → Load processes
- **AI/ML Pipelines**: Preprocessing → Inference → Postprocessing chains
- **Multi-Stage Analysis**: Extract → Analyze → Visualize workflows
- **Robotics Computing**: Sensor → Process → Actuate control loops

## 📦 Getting Started

### Installation

```bash
# Clone the main repository
git clone https://github.com/corebrum/corebrum.git
cd corebrum
cargo build --release
```

### Quick Start

1. **Start the daemon:**
   ```bash
   corebrum daemon --worker-count 4
   ```

2. **Submit a task:**
   ```bash
   corebrum submit --file task.yaml --input '{"number": 8}'
   ```

3. **Launch Web UI and REST API:**
   ```bash
   corebrum web
   # Opens browser to http://localhost:6502
   ```

4. **Launch CMOS shell:**
   ```bash
   corebrum cmos
   ```

## 📚 Resources

- **[Corebrum Examples](https://github.com/corebrum/corebrum-examples)**: Comprehensive task definitions and examples


## 🌟 Key Features

- ✅ **Massively Parallel Computing**: Independent tasks execute simultaneously
- ✅ **Sequential Task Execution**: Chain jobs with automatic output-to-input mapping
- ✅ **Multiple Runtimes**: Python, Docker, WebAssembly, JavaScript
- ✅ **ROS2 Integration**: Native support for modern ROS2 robots
- ✅ **Distributed Storage**: Filesystem, RocksDB, and InfluxDB backends
- ✅ **In-Memory Caching**: High-speed distributed memory operations
- ✅ **Zenoh Mesh Networking**: Automatic discovery and topology formation
- ✅ **Interactive Shell**: CMOS provides familiar Unix-like interface
- ✅ **REST API**: Complete HTTP API for all platform functions
- ✅ **Web UI**: Modern browser-based interface for monitoring and management
- ✅ **Stream-Reactive Tasks**: Real-time processing of continuous data streams
- ✅ **Multi-Machine Support**: Scale from single machines to distributed clusters

## 🤝 Contributing

Please see individual repository READMEs for contribution guidelines.

## 📄 License

All Rights Reserved. 

---

**Corebrum** - Bringing massively parallel and serialized compute to robotics, physical AI, and decentralized mesh computing.

