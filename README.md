# rep_pkg_builder_doc

This repository contains documentation and diagrams for the Replication Package Builder project, a platform for performing systematic literature reviews.

## Diagrams

The project uses C4 Model diagrams created with PlantUML. The diagrams include:
- System Context Diagram
- Container Diagram
- Component Diagram
- Domain Model

## Setting Up C4-PlantUML

To render the C4 diagrams, you need PlantUML with C4-PlantUML support.

### Download C4-PlantUML

1. Clone or download the C4-PlantUML repository from GitHub:
   ```
   git clone https://github.com/plantuml-stdlib/C4-PlantUML.git
   ```
   Or download the ZIP from: https://github.com/plantuml-stdlib/C4-PlantUML/archive/refs/heads/master.zip

2. Extract or move the contents to `/opt/C4-PlantUML/` for system-wide access:
   ```
   sudo mv C4-PlantUML /opt/
   ```

### Using with PlantUML

#### Option 1: Local PlantUML Installation
- Install PlantUML (e.g., via Java: download plantuml.jar from https://plantuml.com/download).
- When running PlantUML, specify the include path to the C4-PlantUML directory:
  ```
  java -jar plantuml.jar -I /opt/C4-PlantUML/ your_diagram.puml
  ```

#### Option 2: PlantUML Server with Docker Alias
- Use Docker to run PlantUML as a local web server with C4 support.
- Ensure Docker is installed and C4-PlantUML is available at `/path/to/libs/C4-PlantUML` (adjust the path as needed).
- Add the following alias to your shell profile (e.g., ~/.bashrc or ~/.zshrc):
  ```
  alias plantuml='docker run -d -p 8080:8080 -v /path/to/libs/C4-PlantUML:/opt/C4-PlantUML -e JAVA_TOOL_OPTIONS='\''-DRELATIVE_INCLUDE=/opt/C4-PlantUML'\'' plantuml/plantuml-server:jetty'
  ```
- Start the server:
  ```
  plantuml
  ```
- Open http://localhost:8080 in your browser to access the PlantUML web interface for rendering diagrams with C4 support.

#### Option 3: VS Code Extension
- Install the PlantUML extension for VS Code.
- In settings, add the C4-PlantUML path to the include path:
  - Open VS Code settings (Ctrl+,).
  - Search for "plantuml.includes".
  - Add `/opt/C4-PlantUML/`.
- Then, preview diagrams directly in VS Code.

### Rendering Diagrams
- Open any .puml file in this repository.
- Use your PlantUML tool to generate PNG/SVG/PDF.
- Example command:
  ```
  plantuml SystemContext.puml
  ```

For more details, refer to the [C4-PlantUML documentation](https://github.com/plantuml-stdlib/C4-PlantUML).

## Project Overview

The Replication Package Builder is designed to assist researchers in conducting systematic literature reviews by querying multiple external databases, analyzing retrieved data, and generating replication packages.