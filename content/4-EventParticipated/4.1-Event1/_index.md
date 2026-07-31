---
title: "Event 1"
date: 2026-06-06
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

# MULTIPLAYER GAME NETWORKING WORKSHOP SUMMARY REPORT

## Event Objectives
* **Cover networking protocols** used in multiplayer game development.
* **Walk through the workflow** for building Serverless WebSocket systems on AWS.
* **Demonstrate client-side network programming** using the Godot Game Engine.
* **Introduce application packaging** with Containerization technology (Docker).

---

## Key Highlights

### 1. Comparing Multiplayer Game Networking Protocols
* **HTTP Polling:**
  * Mechanism: Client repeatedly requests updates from the server.
  * Drawbacks: High latency, adding overhead to the system.
  * Use Cases: Fine for simple features like login or leaderboards, nothing more.
* **UDP (User Datagram Protocol):**
  * Mechanism: Fast packet delivery that tolerates packet loss in exchange for very low latency.
  * Use Cases: The go-to for fast-paced games (FPS, MOBA, racing).
  * In Godot: Wrapped as the ENet library.
* **WebSocket:**
  * Mechanism: A persistent two-way connection that beats HTTP Polling on real-time performance and gives more reliable data control.
  * Use Cases: Chosen as the best fit for the Rock-Paper-Scissors demo.

### 2. Building a Serverless WebSocket Setup on AWS
The network logic runs on 4 core services:
* **API Gateway:** Routes connections through `$connect`, `$disconnect`, and `$default` routes (JSON-based, keyed on `request.body.action`).
* **Lambda Function:** Handles the business logic for connect/disconnect events and message delivery.
* **DynamoDB Table:** Stores match data and player state across 5 main columns: `Connection ID`, `Status` (waiting/playing), `Opponent ID`, `Choice` (rock/paper/scissors), and `Create At` (timestamp).
* **CloudWatch:** Logs system activity automatically to help trace data flow and debug issues.

### 3. Client-Side Programming in Godot Engine
Four main jobs keep the game connection alive:
* **Initialization:** Opens a connection to the API Gateway URL through the `WebSocketPeer` object.
* **Message Polling:** Continuously checks for data from the server (like checking a mailbox) without overloading the system.
* **State Management:** Tracks the 4 WebSocket states — `Connecting`, `Open`, `Closing`, `Closed` — to trigger the right matchmaking requests.
* **Data Processing:** Parses incoming JSON packets from the server to resolve game outcomes.

### 4. Applying Containerization (Docker)
* **Solving Environment Mismatches:** Kills the classic "works on my machine, breaks on yours" problem for good.
* **VM vs. Container:** VMs are heavy since each one boots its own OS; containers are far lighter because they share the host OS through a container engine.
* **Docker Cache/Layer Mechanism:** Images build in layers that cache earlier steps, so only changed layers get rebuilt — cutting packaging time significantly.

---

## Key Takeaways

### Design Mindset
* **Real-World Failure Scenarios:** Learned how to handle sudden disconnects (an unavoidable network reality) to avoid "ghost connections" in DynamoDB that break matchmaking for new players.
* **Performance Optimization:** Realized that `Scan Table` calls on DynamoDB for matchmaking become a bottleneck once concurrency ramps up, which is why centralized, purpose-built management matters.
* **System Resource Management:** Understood Lambda's stateless nature well enough to design the right storage structure for reconnection features.

### Technical Architecture
* **Deep Network Programming:** Got comfortable with JSON packet structures and writing sync logic between the game client and cloud server.
* **Practical Docker Skills:** Learned to write a complete `Dockerfile` (`FROM`, `RUN`, `COPY`, `EXPOSE`, etc.) and understood what `docker run -it` actually does under the hood — enough to spin up fully isolated sandboxes for security testing and malware isolation.

### Future Directions
* **AWS GameLift:** Took away a mental model for hosting game servers on dedicated EC2 clusters and layering in advanced automated matchmaking for larger projects.

---

## Practical Applications to Work

1. **Applying WebSocket Mechanics:** Swap in real-time WebSocket communication for personal projects or coursework instead of defaulting to plain HTTP.
2. **Building Serverless Clusters on AWS:** Try combining API Gateway and Lambda for apps that need asynchronous data pipelines.
3. **Standardizing Packaging Workflows:** Use Docker to package deliverables so every team member runs the exact same environment, streamlining the dev workflow.
4. **Using Sandbox Containers:** Lean on Docker's isolation model to make software testing and security checks safer.

---

## Lessons Learned & Personal Reflections

This workshop turned out to be genuinely valuable — deep technical grounding in networking for gaming, plus a solid dose of modern DevOps thinking.

### 1. Learning from Real-World Insights
* The speaker shared hard-won lessons on system failures, design patterns, and running network infrastructure that balances performance against cost.
* Digging into UDP, WebSocket, and DynamoDB's storage model gave me a much clearer picture of how asynchronous data gets handled in distributed systems.

### 2. Hands-On Technical Experience
* Watched a live connection demo between the game client (Godot) and the server (AWS), tracing the data flow from the client's first request all the way to DynamoDB's status update.
* Picked up debugging and monitoring techniques using CloudWatch, plus some deeper terminal-level interaction with Docker containers.

### 3. Applying Modern Technology Mindsets
* Came to appreciate just how much Docker's virtualization and packaging model saves developers from environment-configuration headaches.
* Learned to treat Docker containers as a flexible, secure "sandbox" for testing and security checks.

### 4. Conclusion & Core Lessons
* **Every system design is a trade-off** between performance, reliability, and cost — no protocol or technology wins across the board, only the one that best fits a given problem.
* **Cloud cost discipline matters:** stay in the habit of auditing and shutting down unused resources (EC2 clusters, databases, etc.) so a development sprint doesn't turn into a surprise bill (a lesson learned the hard way from a "cloud invoice" moment).

> **Summary:** Beyond the technical depth on networking, this event shifted how I think about system architecture, cloud infrastructure optimization, and standardizing software packaging for real engineering work.

![Event1](/images/4-EventParticipated/event_6-6-26/1.png)
![Event1](/images/4-EventParticipated/event_6-6-26/2.png)
![Event1](/images/4-EventParticipated/event_6-6-26/3.png)
![Event1](/images/4-EventParticipated/event_6-6-26/4.png)
