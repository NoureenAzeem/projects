
Smart Home IoT Simulator

A configurable simulator for smart-home IoT devices and environments. Use this project to prototype device behaviors, test home automation rules, simulate sensor data, and evaluate integrations with cloud or local hubs.

Key features
- Simulate multiple device types (sensors, actuators, lights, thermostats, locks).
- Configurable device behaviors and schedules.
- Virtual network/hub to route messages between devices and controllers.
- Multiple protocols supported (e.g., MQTT / HTTP) — adjust in config.
- Logging and telemetry export for testing and analytics.
- Example scenarios and scripts to reproduce typical smart-home use cases.

Getting started

Prerequisites
- OS: Windows / macOS / Linux
- Runtime: Node.js >= 16.x OR Python 3.8+ (replace with actual runtime used)
- Package manager: npm / pip (adjust according to project)
- Optional: Docker (if project includes a Dockerfile / containers)

Install
1. Unzip the project:
   unzip smart-home-iot-simulator.zip
2. Change into the project directory:
   cd smart-home-iot-simulator
3. Install dependencies:
   - Node.js example:
     npm install
   - Python example:
     pip install -r requirements.txt

Configuration
- Copy the example config and edit to tailor the simulation:
  cp config.example.json config.json
- Common config options:
  - devices: list of device definitions (type, id, initial state)
  - network: protocol settings (MQTT broker url, HTTP port)
  - runtime: simulation speed, seed, logging level
- Environment variables (optional):
  - SIM_SPEED — simulation speed multiplier
  - MQTT_BROKER — broker url (if using MQTT)

Run the simulator
- Local run (Node.js example):
  npm start
- Python example:
  python -m simulator.main --config config.json
- Docker (if available):
  docker build -t smart-home-sim .
  docker run -it -p 1883:1883 -p 8080:8080 smart-home-sim

Examples and usage
- Start a sample scenario:
  scripts/run-scenario.sh examples/away-mode.json
- Publish synthetic temperature data to MQTT:
  scripts/publish_temperature.py --device thermostat-01 --rate 1s
- Connect a client (e.g., Home Assistant) to the simulator's MQTT broker at:
  mqtt://localhost:1883

Project structure (example)
- /src — main source code
- /config — example configuration files
- /examples — ready-to-run scenarios
- /scripts — helper scripts for running and testing
- /docs — additional documentation and architecture notes

Testing
- Unit tests:
  npm test
- Integration tests:
  scripts/integration_tests.sh
- Test coverage:
  npm run coverage

Logging and telemetry
- Logs are written to ./logs by default (change in config)
- Telemetry exports are available in CSV / JSON formats under ./telemetry

Extending the simulator
- Add a new device type by creating a device class in src/devices and registering it in the device factory.
- Add protocol support by implementing the protocol adapter interface in src/protocols.

Contributing
- Contributions welcome — open an issue to propose major changes.
- Fork the repo, create a feature branch, and open a pull request.
- Please follow the code style in the repository and add tests for new behaviors.

Contact
- Author: NoureenAzeem
- GitHub: https://github.com/NoureenAzeem


 

 
