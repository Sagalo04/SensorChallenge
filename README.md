# Sensor Challenge

## Description

Simulate an industrial sensor network that generates massive data volumes in C++, processes the telemetry, and visualizes it on an animated web interface.

- **How the Backend Works (C++ / C#):**
    1. An autonomous C++ process ("Sensor Simulator") generates continuous metrics (temperature, CPU, memory or any sensors) and transmits them at high speed using **ZMQ**.
    2. The main backend server (built with `httplib`) acts as a **Broker**: it gets the ZMQ data stream and exposes it to the web browser via Realtime communication.
    3. The same HTTP server handles traditional **REST** endpoints to update configurations (e.g., modifying a sensor's alert threshold via a `POST` request).
- **Frontend:** A clean Single Page Application (SPA) built with native HTML/JS or React. It displays real-time animated charts that automatically update upon receiving events from the server.

## Architecture Diagram Proposal

Following architecture is my proposal for how the solution would be, nevertheless the final solutions can change as long as the functionality is there

<img width="3592" height="1404" alt="Untitled" src="https://github.com/user-attachments/assets/b7026461-4c29-4c12-98f3-192447717bb1" />

## Criteria

| Grading Criteria                             | Deliverable Requirements                                                                                                                                                                                                     |
| -------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **System Architecture & Core Functionality** | Seamless data flow: Sensor Simulator → Backend (ZMQ) → Web Frontend. Live metrics must update in real-time without locking the browser UI or freezing the server loop. REST API endpoints must process changes successfully. |
| **Concurrency & Thread Safety**              | Multi-threading infrastructure in C++. The background ZMQ socket must capture streaming payloads safely on its own lifecycle while the `cpp-httplib` engine services active client connections.                              |
| **Clean Code & Modular Design**              | Clear separation between network protocols, processing logic, and visualization. Functions must remain concise, highly expressive, and under 40 lines of code.                                                               |
| **Naming Conventions & Standards**           | Precise and consistent application of the designated casing rules. Strict usage of the naming convention.                                                                                                                    |
| **Memory Management & Compilation**          | Standard Template Library (STL) compliance. Absolute reliance on smart pointers and robust scope management. Compilation must execute cleanly with zero warnings.                                                            |
| **Git Version Control & Tracking**           | Rich repository history containing logical, incremental, and highly descriptive commit messages tracking structural evolution rather than a single massive final push.                                                       |

## Awesome resources

- [libzmq Core](https://github.com/zeromq/libzmq)
- [cpp bindings ZMQ](https://github.com/zeromq/cppzmq)
- [c# .net bindings zmq](https://github.com/zeromq/netmq)
- [httplib](https://github.com/yhirose/cpp-httplib)
- [simdjson](https://github.com/simdjson/simdjson)
- [simdjson c# bindings](https://github.com/EgorBo/SimdJsonSharp)
- [eCharts](https://github.com/apache/echarts?tab=Apache-2.0-1-ov-file)
- [uPlot](https://github.com/leeoniya/uPlot)
- [reCharts](https://recharts.github.io/)
- [Chartjs](https://www.chartjs.org/)
- [Sonner](https://github.com/emilkowalski/sonner)
