# Ex.No.4-EXP 4 Generate the Prompt and evaluate that for following prompt patterns - Zero-shot Prompting.•	Few-shot Prompting - Chain of Thought -	Persona Pattern - Reverse Prompting - Graph Prompting - Active Prompting
                                                                           
### REGISTER NUMBER : 212223230051
### NAME : Divyashree V
### Aim: 
To write the prompt for the following prompt types and compare that with different AI tools and evaluate that using any one evaluation method (Ex. Rubrics). Zero-shot Prompting.•	Few-shot Prompting - Chain of Thought -	Persona Pattern - Reverse Prompting - Graph Prompting - Active Prompting 


### Explanation - Use engineering case studies such as - Smart Irrigation, Drone Navigation, Robot Path Planning

# Prompt Engineering for Engineering Case Studies

## Overview

This project demonstrates the implementation and evaluation of seven prompt engineering techniques using real-world engineering case studies.

The prompting techniques implemented are:

1. Zero-shot Prompting
2. Few-shot Prompting
3. Chain-of-Thought Prompting
4. Persona Pattern
5. Reverse Prompting
6. Graph Prompting
7. Active Prompting

The techniques are applied to three engineering problems:

* Smart Irrigation
* Drone Navigation
* Robot Path Planning

The generated responses are evaluated based on:

* **Reasoning**
* **Correctness**
* **Token Usage**

---

## Objectives

The objectives of this experiment are:

* To understand different prompt engineering techniques.
* To implement different prompting strategies on engineering problems.
* To compare how prompt structure affects AI-generated responses.
* To evaluate the reasoning quality of generated solutions.
* To evaluate the technical correctness of generated solutions.
* To compare token consumption across prompting techniques.
* To identify the most suitable prompting technique for different engineering applications.

---

# 1. Engineering Case Studies

## 1.1 Smart Irrigation

### Problem Statement

Design an intelligent irrigation system that determines when and how much water should be supplied to crops using:

* Soil moisture
* Temperature
* Humidity
* Weather forecast
* Crop type
* Water availability

The system should reduce water wastage while maintaining appropriate soil moisture for healthy crop growth.

---

## 1.2 Drone Navigation

### Problem Statement

Design an autonomous drone navigation system that moves from a starting point to a destination while:

* Avoiding obstacles
* Minimizing travel distance
* Conserving battery power
* Maintaining safe navigation
* Reacting to unexpected obstacles

---

## 1.3 Robot Path Planning

### Problem Statement

Design a path-planning system for an autonomous warehouse robot that moves from a starting location to a target location while:

* Avoiding static obstacles
* Avoiding dynamic obstacles
* Minimizing travel distance
* Maintaining a safety margin
* Replanning when the environment changes

---

# 2. Zero-shot Prompting

## Description

Zero-shot prompting provides the model with a task or question without providing examples.

It is useful as a baseline because it requires minimal prompt preparation and generally consumes fewer tokens.

---

## 2.1 Smart Irrigation

### Prompt

```text
Design an intelligent irrigation system for agricultural fields. The system should use soil moisture, temperature, humidity, weather forecast, crop type, and water availability to determine when irrigation is required and how much water should be supplied.

Explain:
1. System inputs
2. Decision-making process
3. Sensors required
4. Control mechanism
5. Benefits of the proposed system
```

### Output

```text
An intelligent irrigation system can automatically determine irrigation requirements using environmental and crop-related data.

1. System Inputs
- Soil moisture level
- Temperature
- Humidity
- Weather forecast
- Crop type
- Water availability

2. Decision-Making Process
The system continuously monitors soil moisture and environmental conditions. If soil moisture falls below the required threshold for the crop and rainfall is not expected, irrigation is activated. Temperature and humidity can be used to estimate evaporation and water demand.

3. Sensors Required
- Soil moisture sensor
- Temperature sensor
- Humidity sensor
- Rain sensor or weather API
- Water-level sensor

4. Control Mechanism
A microcontroller receives sensor data and sends it to a decision-making algorithm. If irrigation is required, the controller activates a water pump through a relay or motor driver. The pump can be stopped when the required soil moisture level is reached.

5. Benefits
- Reduces water wastage
- Automates irrigation
- Improves crop health
- Reduces manual intervention
- Conserves water and energy
```

---

## 2.2 Drone Navigation

### Prompt

```text
Design an autonomous drone navigation system that moves from a starting point to a destination while avoiding obstacles, minimizing travel distance, and conserving battery power.

Explain the sensors, navigation algorithm, obstacle avoidance mechanism, and safety features.
```

### Output

```text
An autonomous drone navigation system can combine GPS, IMU, cameras or LiDAR, and a path-planning algorithm.

Sensors:
- GPS for global position
- IMU for acceleration and orientation
- Camera or LiDAR for obstacle detection
- Battery sensor for monitoring remaining energy

Navigation:
The drone first determines a route from the starting point to the destination. A path-planning algorithm such as A* can be used for route generation.

Obstacle Avoidance:
Real-time sensor data is used to detect obstacles. If an obstacle blocks the planned path, the route is recalculated.

Battery Management:
The system should consider battery level and estimated energy consumption when selecting a route.

Safety:
The drone should maintain collision margins, monitor battery status, and enter a safe landing or return-to-home mode when required.
```

---

## 2.3 Robot Path Planning

### Prompt

```text
Design a path-planning system for an autonomous warehouse robot that moves from a starting location to a target location while avoiding static and dynamic obstacles.

Explain the algorithm, environment representation, obstacle avoidance strategy, and safety considerations.
```

### Output

```text
An autonomous warehouse robot can use a map-based path-planning system.

The warehouse can be represented as a grid where free cells are traversable and occupied cells represent obstacles.

Algorithm:
A* can be used to find a short path between the start and target positions.

Obstacle Avoidance:
Sensors such as LiDAR or cameras detect obstacles. If a dynamic obstacle appears, the local planner can modify the path.

Safety:
The robot should maintain a minimum safety distance from obstacles and reduce speed when obstacles are nearby.

The system should continuously update the map and replan when necessary.
```

---

# 3. Few-shot Prompting

## Description

Few-shot prompting provides the model with examples before asking it to solve a new problem.

The examples demonstrate the expected reasoning pattern, format, or type of answer.

---

## 3.1 Smart Irrigation

### Prompt

```text
You are solving an agricultural irrigation decision problem.

Example 1:
Input:
Soil moisture = 20%
Temperature = 35°C
Rain probability = 5%

Output:
Irrigation should be activated because soil moisture is low, temperature is high, and rainfall is unlikely.

Example 2:
Input:
Soil moisture = 75%
Temperature = 27°C
Rain probability = 80%

Output:
Irrigation should not be activated because soil moisture is already sufficient and rainfall is likely.

Now solve this case:

Soil moisture = 30%
Temperature = 33°C
Humidity = 45%
Rain probability = 10%
Crop = Tomato

Determine whether irrigation should be activated and explain the decision.
```

### Output

```text
Irrigation should be activated.

Reason:
- Soil moisture is only 30%, which may be insufficient for tomato crops.
- Temperature is relatively high at 33°C, increasing water demand.
- Humidity is moderate at 45%.
- Rain probability is only 10%, so natural rainfall is unlikely.

Therefore, the system should start irrigation with a controlled amount of water. The exact irrigation duration should depend on soil type, crop growth stage, field area, and available water.
```

---

## 3.2 Drone Navigation

### Prompt

```text
Example 1:
A drone has sufficient battery and a clear path to the destination.
Output: Follow the shortest safe path.

Example 2:
A drone detects an obstacle directly in its planned path.
Output: Recalculate the path around the obstacle while maintaining a safe distance.

Now solve:

A drone has 65% battery remaining, detects two obstacles along the shortest route, and has an alternative route that is 15% longer but safer.

Recommend a navigation strategy and explain why.
```

### Output

```text
The drone should select the safer alternative route.

Although the alternative route is 15% longer, the shortest route contains two obstacles. Avoiding obstacles is more important than minimizing distance alone.

The navigation system should:

1. Detect both obstacles.
2. Calculate safe alternative paths.
3. Estimate the energy required for each path.
4. Verify that the remaining battery is sufficient.
5. Select the safest route within the available energy budget.

With 65% battery remaining, the drone has a reasonable energy reserve, but the system should still continuously monitor battery consumption.
```

---

## 3.3 Robot Path Planning

### Prompt

```text
Example 1:
A robot has a clear grid map and no obstacles.
Output: Use A* to find the shortest path between the start and target.

Example 2:
A static obstacle blocks the shortest path.
Output: A* should find an alternative collision-free path.

Example 3:
A moving obstacle enters the planned path.
Output: The robot should stop or slow down and replan using updated sensor information.

Now solve:

A warehouse robot is moving toward its destination when a moving forklift enters its planned path. The robot has LiDAR and sufficient computing power.

What should the robot do?
```

### Output

```text
The robot should immediately reduce speed or stop depending on the distance to the forklift.

The LiDAR detects the forklift and updates the robot's local environment map. The path planner should then calculate a new collision-free path around the forklift.

The robot should resume movement only after verifying that the new path provides an adequate safety margin.

Therefore:

Detect → Slow/Stop → Update Map → Replan → Verify Safety → Continue
```

---

# 4. Chain-of-Thought Prompting

## Description

Chain-of-thought prompting asks the model to approach a problem through a sequence of reasoning steps.

For evaluation, this experiment measures the **quality of the provided justification and final answer**, rather than requiring disclosure of private internal reasoning.

---

## 4.1 Smart Irrigation

### Prompt

```text
Analyze the following smart irrigation problem systematically.

Soil moisture = 28%
Temperature = 34°C
Humidity = 40%
Rain probability = 15%
Crop = Tomato

Consider:
- Current soil moisture
- Temperature
- Humidity
- Rainfall probability
- Crop water requirements

Determine whether irrigation should be activated. Provide a concise justification showing how each factor affects the decision, followed by the final recommendation.
```

### Output

```text
Analysis:

1. Soil Moisture:
The soil moisture is 28%, which indicates relatively dry soil. This increases the need for irrigation.

2. Temperature:
The temperature is 34°C. Higher temperatures generally increase evaporation and crop water demand.

3. Humidity:
Humidity is 40%, which is moderate to relatively low. This can increase evaporation compared with highly humid conditions.

4. Rainfall Probability:
The probability of rainfall is only 15%, so relying on natural rainfall is unlikely to satisfy the crop's water requirement.

5. Crop:
Tomatoes require adequate and consistent soil moisture for healthy growth.

Final Recommendation:
Irrigation should be activated. However, the amount of water should be determined using soil type, crop growth stage, field size, and water availability.
```

---

## 4.2 Drone Navigation

### Prompt

```text
Analyze this drone navigation problem systematically.

A drone has 60% battery remaining. The direct route to the destination contains three obstacles. An alternative route is 20% longer but has significantly fewer obstacles.

Consider:
- Battery level
- Travel distance
- Obstacle risk
- Safety
- Energy consumption

Determine the recommended route and justify the decision.
```

### Output

```text
Analysis:

1. Battery:
The drone has 60% battery, so energy availability must be considered.

2. Direct Route:
The direct route is shorter but contains three obstacles, increasing collision and replanning risk.

3. Alternative Route:
The alternative route is 20% longer but significantly safer.

4. Energy:
The drone should estimate whether the additional distance can be completed within the available battery.

5. Safety:
Safety should take priority over a small reduction in travel distance.

Final Recommendation:
Select the alternative route if its estimated energy requirement remains within the available battery reserve. The drone should continuously monitor battery status and obstacle conditions.
```

---

## 4.3 Robot Path Planning

### Prompt

```text
Analyze this robot path-planning scenario systematically:

A warehouse robot must travel from A to B. The shortest route contains a static obstacle, and a dynamic obstacle may appear during operation.

Discuss:
- Environment representation
- Initial path planning
- Dynamic obstacle detection
- Replanning
- Safety

Provide the final recommended approach.
```

### Output

```text
Environment Representation:
The warehouse can be represented using an occupancy grid or graph. Free areas are traversable while obstacles are represented as occupied regions.

Initial Planning:
A* can generate an efficient path from A to B while avoiding known static obstacles.

Dynamic Obstacle Detection:
LiDAR or cameras can detect moving objects during operation.

Replanning:
When a dynamic obstacle enters the planned route, the robot should update its local map and calculate a new collision-free path.

Safety:
The robot should maintain a safety margin, reduce speed near obstacles, and stop if a safe path cannot be determined.

Final Recommendation:
Use A* for global planning combined with real-time local obstacle detection and dynamic replanning.
```

---

# 5. Persona Pattern

## Description

The Persona Pattern assigns a specific professional role to the AI model.

This can encourage domain-specific terminology, constraints, and solution approaches.

---

## 5.1 Smart Irrigation

### Prompt

```text
You are an agricultural automation engineer specializing in IoT, precision agriculture, embedded systems, and machine learning.

Design an intelligent irrigation system using:
- Soil moisture
- Temperature
- Humidity
- Weather forecast
- Crop type
- Water availability

Explain the sensors, system architecture, decision-making algorithm, control mechanism, and safety considerations.
```

### Output

```text
As an agricultural automation engineer, I would design the system as an IoT-based closed-loop irrigation controller.

Architecture:

Sensors
   ↓
Microcontroller
   ↓
Data Processing
   ↓
Irrigation Decision Algorithm
   ↓
Pump Controller
   ↓
Water Pump
   ↓
Crop Field

Sensors:
- Capacitive soil moisture sensors
- Temperature sensor
- Humidity sensor
- Water-level sensor
- Weather API for rainfall prediction

Decision Algorithm:
The controller compares measured soil moisture with the crop-specific threshold. It also considers temperature, humidity, predicted rainfall, and available water.

If:
Soil moisture < crop threshold
AND rainfall probability is low
AND sufficient water is available

then irrigation is activated.

Safety Considerations:
- Prevent pump operation when the water tank is empty.
- Prevent excessive irrigation.
- Set a maximum pump operating time.
- Detect sensor failures.
- Provide manual override capability.

This architecture provides automated, data-driven irrigation while reducing water wastage.
```

---

## 5.2 Drone Navigation

### Prompt

```text
Act as an autonomous robotics engineer specializing in UAV navigation, computer vision, SLAM, path planning, and real-time control.

Design a robust drone navigation architecture for obstacle avoidance and energy-efficient path planning.
```

### Output

```text
A robust UAV navigation system should use multiple layers:

1. Perception Layer
   - Camera
   - LiDAR
   - IMU
   - GPS

2. Localization Layer
   - GPS-based localization outdoors
   - Visual or LiDAR-based localization when GPS is unreliable
   - Sensor fusion using an Extended Kalman Filter

3. Planning Layer
   - Global planner for long-distance route generation
   - Local planner for real-time obstacle avoidance
   - A* or similar algorithms for global planning

4. Control Layer
   - Flight controller
   - Position controller
   - Velocity controller

5. Safety Layer
   - Battery monitoring
   - Geofencing
   - Collision margins
   - Emergency landing
   - Return-to-home

This layered architecture improves reliability because perception, planning, control, and safety can operate as separate but interconnected modules.
```

---

## 5.3 Robot Path Planning

### Prompt

```text
Act as an autonomous robotics engineer specializing in mobile robotics, SLAM, path planning, computer vision, and real-time navigation.

Design a robust warehouse robot path-planning system that handles both static and dynamic obstacles.
```

### Output

```text
A robust warehouse robot should use a hierarchical navigation architecture.

1. Mapping
Use SLAM or a pre-built warehouse map to represent the environment.

2. Localization
Use LiDAR, odometry, IMU, or sensor fusion to estimate robot position.

3. Global Planning
Use A* or Dijkstra to calculate a collision-free global route.

4. Local Planning
Use real-time sensor data to avoid dynamic obstacles.

5. Replanning
If the global route becomes blocked, update the local map and generate an alternative route.

6. Safety
Maintain obstacle clearance, limit velocity near humans and vehicles, and stop when safe navigation cannot be guaranteed.

This architecture provides both efficient route planning and real-time obstacle avoidance.
```

---

# 6. Reverse Prompting

## Description

Reverse prompting asks the model to determine what information is required before generating the final solution.

It is particularly useful for engineering requirements analysis.

---

## 6.1 Smart Irrigation

### Prompt

```text
You need to design an intelligent irrigation system for a farm.

Before proposing the solution, identify the important questions and information that must be known about:
- Farm
- Crop
- Soil
- Climate
- Water availability
- Sensors
- Operational constraints

After identifying the requirements, propose a suitable intelligent irrigation system.
```

### Output

```text
Important information required:

1. Farm
- What is the farm area?
- How many irrigation zones are required?
- What is the existing irrigation infrastructure?

2. Crop
- What crop is being grown?
- What is the crop growth stage?
- What is the required soil moisture range?

3. Soil
- What is the soil type?
- What is its water retention capacity?
- What is the current moisture level?

4. Climate
- What are the average temperature and humidity?
- What is the expected rainfall?
- What is the evaporation rate?

5. Water Availability
- What is the water source?
- How much water is available?
- What is the pump capacity?

6. Sensors
- Are soil moisture sensors available?
- Is weather data available?
- Is water-level monitoring required?

Proposed System:

The system should use soil moisture sensors and environmental sensors connected to a microcontroller. Weather forecast information should be incorporated into the decision process. A crop-specific irrigation algorithm should determine irrigation duration, and a relay-controlled pump should deliver the required water.

The system should also include water-level monitoring, maximum irrigation limits, and manual override functionality.
```

---

## 6.2 Drone Navigation

### Prompt

```text
Before designing a drone navigation system, identify the requirements and questions that must be answered regarding the drone, environment, sensors, destination, obstacles, battery, and safety constraints.

Then propose an appropriate navigation architecture.
```

### Output

```text
Important requirements:

- What type of drone is being used?
- What is its maximum flight time?
- Is GPS available?
- What types of obstacles are expected?
- Are obstacles static or dynamic?
- What sensors are available?
- What is the operating altitude?
- How accurate must navigation be?
- What is the maximum acceptable collision risk?
- Is return-to-home required?
- What are the communication constraints?

Proposed architecture:

Sensors → Perception → Localization → Global Planner → Local Planner → Flight Controller

The global planner generates a route toward the destination, while the local planner reacts to obstacles detected during flight. Battery and safety constraints should be considered throughout the navigation process.
```

---

## 6.3 Robot Path Planning

### Prompt

```text
Before designing the warehouse robot path-planning system, identify the questions and requirements needed to select the correct planning algorithm, sensors, map representation, and obstacle avoidance strategy.

Then provide the proposed architecture.
```

### Output

```text
Important requirements:

1. Is the warehouse map known in advance?
2. Are obstacles static, dynamic, or both?
3. What is the robot's maximum speed?
4. What sensors are available?
5. Is human movement expected?
6. What level of localization accuracy is required?
7. What is the warehouse size?
8. Are multiple robots operating simultaneously?
9. How quickly must the robot react to obstacles?
10. What safety standards apply?

Proposed Architecture:

Sensors → Localization → Environment Model → Global Planner → Local Planner → Motion Controller

A* can be used for global planning, while a local planner continuously reacts to dynamic obstacles.
```

---

# 7. Graph Prompting

## Description

Graph prompting represents a problem using nodes and relationships.

It is useful for engineering systems where multiple components exchange information.

---

## 7.1 Smart Irrigation

### Prompt

```text
Model the smart irrigation system as a directed graph.

Use the following nodes:

- Soil Moisture
- Temperature
- Humidity
- Weather Forecast
- Crop Type
- Water Availability
- Decision Engine
- Irrigation Controller
- Water Pump
- Crop Field

Define the relationships between the nodes and explain how information flows through the graph to determine whether irrigation should occur.
```

### Output

```text
Graph representation:

Soil Moisture ────────┐
                      │
Temperature ──────────┤
                      │
Humidity ─────────────┤
                      ├──> Decision Engine
Weather Forecast ─────┤
                      │
Crop Type ────────────┤
                      │
Water Availability ───┘
                              │
                              ↓
                    Irrigation Controller
                              │
                              ↓
                         Water Pump
                              │
                              ↓
                         Crop Field
                              │
                              ↓
                       Soil Moisture

Explanation:

The sensors provide environmental information to the Decision Engine. Crop Type determines the required moisture threshold. Weather Forecast helps determine whether irrigation can be postponed.

Water Availability determines whether sufficient water exists for irrigation.

The Decision Engine generates an irrigation command. The Irrigation Controller activates the Water Pump, which supplies water to the Crop Field.

The resulting soil moisture is measured again, creating a feedback loop.
```

---

## 7.2 Drone Navigation

### Prompt

```text
Represent autonomous drone navigation as a graph.

Nodes:
GPS, IMU, Camera, LiDAR, Localization, Obstacle Detection, Global Planner, Local Planner, Battery Monitor, Flight Controller, Destination.

Show the information flow and explain the graph.
```

### Output

```text
GPS ───────────────┐
                   │
IMU ───────────────┤
                   ↓
              Localization
                   ↑
Camera ──> Obstacle Detection <── LiDAR
                   │
                   ↓
             Global Planner
                   │
                   ↓
              Local Planner
                   ↑
                   │
             Battery Monitor
                   │
                   ↓
            Flight Controller
                   │
                   ↓
               Destination

The sensors provide position and environmental information. Localization determines the drone's current position. The global planner generates a route toward the destination.

The obstacle detection module provides information to the local planner. The local planner modifies the route when obstacles are detected.

The battery monitor ensures that the selected route remains feasible given the available energy.
```

---

## 7.3 Robot Path Planning

### Prompt

```text
Represent an autonomous warehouse robot as a directed graph.

Nodes:
Robot Position, Warehouse Map, LiDAR, Camera, Obstacle Detection, Global Planner, Local Planner, Safety Controller, Motor Controller, Destination.

Explain the relationships and information flow.
```

### Output

```text
Warehouse Map ────────┐
                      ↓
Robot Position ──> Global Planner
                      │
                      ↓
                  Local Planner
                      ↑
                      │
LiDAR ──> Obstacle Detection <── Camera
                      │
                      ↓
                Safety Controller
                      │
                      ↓
                Motor Controller
                      │
                      ↓
                 Destination

The warehouse map and robot position are used by the global planner to generate a route.

LiDAR and camera sensors detect obstacles. The local planner modifies the route based on detected obstacles.

The safety controller verifies that the planned movement satisfies obstacle-clearance and velocity constraints before commands are sent to the motors.
```

---

# 8. Active Prompting

## Description

Active prompting allows the model to identify missing information and ask targeted questions before producing a solution.

This is useful when engineering requirements are incomplete.

---

## 8.1 Smart Irrigation

### Prompt

```text
You are designing an intelligent irrigation system.

Before giving the final design, identify the minimum number of high-impact questions whose answers could significantly change the architecture or irrigation strategy.

Ask those questions first. Do not make unnecessary assumptions.
```

### Output

```text
Before designing the system, I need the following information:

1. What type of crop is being cultivated?
2. What is the approximate farm area?
3. What type of soil is present?
4. What is the available water source and daily water capacity?
5. Is real-time weather forecast data available?
6. What level of automation is required?
7. What sensors and communication infrastructure are already available?

These answers will determine sensor requirements, irrigation thresholds, pump capacity, communication architecture, and the decision-making algorithm.
```

---

## 8.2 Drone Navigation

### Prompt

```text
You are designing an autonomous drone navigation system.

Ask only the most important questions that must be answered before selecting a navigation algorithm and sensor configuration.

Wait for the answers before proposing the final architecture.
```

### Output

```text
The most important questions are:

1. Will the drone operate indoors, outdoors, or both?
2. Is GPS reliably available?
3. Are obstacles static, dynamic, or both?
4. What is the required navigation accuracy?
5. What sensors are currently available?
6. What is the drone's maximum flight time?
7. What is the maximum operating speed?
8. What safety requirements must be satisfied?
9. Is real-time obstacle avoidance required?
10. What computing hardware is available onboard?

These answers are necessary to select appropriate localization, perception, planning, and control techniques.
```

---

## 8.3 Robot Path Planning

### Prompt

```text
You are designing a path-planning system for an autonomous warehouse robot.

Before selecting an algorithm, ask the minimum number of high-impact questions required to determine:
- Map representation
- Planning algorithm
- Sensor requirements
- Dynamic obstacle handling
- Safety requirements

Do not make assumptions when the missing information could change the design.
```

### Output

```text
High-impact questions:

1. Is a complete warehouse map available?
2. Are obstacles static, dynamic, or both?
3. Will humans share the workspace with the robot?
4. What sensors are available?
5. What is the robot's maximum speed?
6. How quickly must the robot react to obstacles?
7. Are multiple robots operating simultaneously?
8. What localization accuracy is required?
9. Is shortest path or minimum travel time the primary objective?
10. What safety constraints must be satisfied?

These answers will determine whether a simple graph-search algorithm is sufficient or whether a more advanced dynamic navigation system is required.
```

---

# 9. Evaluation Methodology

Each prompting technique is evaluated using three metrics.

## 9.1 Reasoning

Reasoning measures how logically and systematically the model analyzes the engineering problem.

### Scoring

| Score | Description                                                  |
| ----: | ------------------------------------------------------------ |
|     5 | Excellent logical analysis with relevant engineering factors |
|     4 | Good reasoning with minor omissions                          |
|     3 | Adequate reasoning                                           |
|     2 | Weak or incomplete reasoning                                 |
|     1 | Poor reasoning or unsupported conclusion                     |

---

## 9.2 Correctness

Correctness measures whether the generated solution is technically valid and appropriate for the given engineering problem.

### Scoring

| Score | Description                           |
| ----: | ------------------------------------- |
|     5 | Technically accurate and complete     |
|     4 | Mostly correct with minor issues      |
|     3 | Partially correct                     |
|     2 | Contains significant technical issues |
|     1 | Incorrect or impractical              |

---

## 9.3 Token Usage

Token usage measures the amount of text processed and generated by the model.

Token efficiency can be calculated as:

```text
Token Efficiency = Quality Score / Total Tokens Used
```

where:

```text
Quality Score = Reasoning Score + Correctness Score
```

Lower token consumption with high-quality output indicates better efficiency.

For actual experiments, token counts should be collected from the API or model interface being used.

---

# 10. Evaluation Table

The following table can be used to record experimental results.

---

# 11. Illustrative Results

The following values demonstrate how the final evaluation can be presented. These are example scores, not measured API results.

| Technique         | Reasoning /5 | Correctness /5 | Token Efficiency /5 |
| ----------------- | -----------: | -------------: | ------------------: |
| Zero-shot         |            3 |              4 |                   5 |
| Few-shot          |            4 |              4 |                   4 |
| Chain-of-Thought  |            5 |              5 |                   2 |
| Persona           |            4 |              5 |                   3 |
| Reverse Prompting |            5 |              5 |                   3 |
| Graph Prompting   |            5 |              5 |                   3 |
| Active Prompting  |            5 |              5 |                   3 |

---

# 12. Comparative Analysis

## Zero-shot Prompting

Zero-shot prompting is the simplest technique. It requires no examples and generally produces short responses. It is useful for establishing a baseline and has good token efficiency.

However, responses may be generic because the model receives limited guidance.

---

## Few-shot Prompting

Few-shot prompting provides examples that demonstrate the expected response pattern.

Advantages:

* Improves consistency
* Provides contextual guidance
* Can improve classification and decision-making
* Useful when the desired output format is specific

Disadvantage:

* Examples increase prompt length and token consumption.

---

## Chain-of-Thought Prompting

Chain-of-thought-style prompting encourages systematic consideration of multiple factors.

Advantages:

* Better structured analysis
* Useful for complex engineering decisions
* Can expose assumptions and intermediate considerations

Disadvantage:

* Usually produces longer responses and therefore increases token usage.

---

## Persona Pattern

Persona prompting assigns an expert identity to the model.

Advantages:

* Produces domain-oriented responses
* Encourages relevant terminology
* Helps focus on engineering constraints
* Can improve the practical quality of recommendations

For example, assigning the model the role of an agricultural automation engineer makes the smart irrigation response more focused on sensors, control systems, IoT, and safety.

---

## Reverse Prompting

Reverse prompting asks what information is required before solving the problem.

Advantages:

* Helps identify missing requirements
* Reduces unsupported assumptions
* Useful during requirements engineering
* Improves system-design completeness

This technique is especially valuable when the problem statement is incomplete.

---

## Graph Prompting

Graph prompting represents system components as nodes and their interactions as edges.

Advantages:

* Makes dependencies explicit
* Shows information flow
* Useful for complex engineering systems
* Helps identify feedback loops
* Improves system architecture understanding

Smart irrigation naturally forms a feedback graph because sensor measurements affect irrigation decisions, which affect the field, which subsequently changes soil moisture.

---

## Active Prompting

Active prompting allows the model to request important missing information.

Advantages:

* Reduces uncertainty
* Identifies high-impact requirements
* Prevents unnecessary assumptions
* Useful for interactive engineering design

It is especially useful when the user has not provided enough information to select an appropriate algorithm or architecture.

---

# 13. Overall Comparison

| Technique        | Main Strength              | Main Limitation                 | Best Use                    |
| ---------------- | -------------------------- | ------------------------------- | --------------------------- |
| Zero-shot        | Simple and token-efficient | Can be generic                  | Baseline solutions          |
| Few-shot         | Consistency                | Higher token usage              | Pattern-based tasks         |
| Chain-of-Thought | Structured reasoning       | Higher token usage              | Complex analysis            |
| Persona          | Domain expertise           | Can add unnecessary context     | Engineering recommendations |
| Reverse          | Requirement discovery      | Requires additional interaction | System requirements         |
| Graph            | Relationship modeling      | More complex prompt             | System architecture         |
| Active           | Handles uncertainty        | Requires interaction            | Incomplete requirements     |

---

# 14. Findings

The experiment demonstrates that prompt design significantly affects the quality and characteristics of AI-generated engineering solutions.

### Finding 1 — Reasoning

Structured techniques such as Chain-of-Thought, Reverse Prompting, Graph Prompting, and Active Prompting can produce more systematic analysis than a basic zero-shot prompt.

### Finding 2 — Correctness

Persona, Reverse, Graph, and Active prompting can improve technical relevance by providing additional context or forcing the model to consider engineering constraints.

### Finding 3 — Token Usage

Zero-shot prompting generally requires fewer tokens because it contains minimal instructions and no examples.

Few-shot and Chain-of-Thought prompting can consume more tokens because they include examples or request detailed reasoning.

### Finding 4 — Requirements

Reverse and Active prompting are particularly useful when requirements are incomplete.

### Finding 5 — System Relationships

Graph prompting is particularly useful for engineering systems containing multiple interconnected components.

---

# 15. Conclusion

This experiment implemented seven prompt engineering techniques across three engineering case studies: Smart Irrigation, Drone Navigation, and Robot Path Planning.

The results demonstrate that no single prompting technique is optimal for every problem.

**Zero-shot prompting** is suitable when simplicity and token efficiency are important.

**Few-shot prompting** is useful when examples can guide the model toward a desired response pattern.

**Chain-of-Thought prompting** is useful for structured engineering analysis.

**Persona prompting** helps produce domain-specific technical solutions.

**Reverse prompting** is effective for identifying missing requirements.

**Graph prompting** is effective for representing relationships and information flow between engineering components.

**Active prompting** is useful when the problem contains uncertainty or incomplete requirements.

Therefore, the best prompting technique should be selected according to the nature of the engineering problem, required reasoning depth, correctness requirements, and token budget.

---

# 16. Key Takeaway

```text
Prompt Engineering
        │
        ├── Zero-shot
        ├── Few-shot
        ├── Chain-of-Thought
        ├── Persona
        ├── Reverse
        ├── Graph
        └── Active
                │
                ↓
       Engineering Problem
                │
       ┌────────┼─────────┐
       ↓        ↓         ↓
   Reasoning Correctness Tokens
       │        │         │
       └────────┼─────────┘
                ↓
        Overall Evaluation
```

> **A well-designed prompt can guide an AI model toward more relevant, structured, and reliable engineering solutions while balancing reasoning quality, correctness, and token consumption.**

---

# 17. Technologies / Tools

The experiment can be performed using any LLM that provides access to generated responses and token statistics.

Possible tools include:

* OpenAI API

The same model should preferably be used for all prompting techniques to ensure a fair comparison.

# Result: The various types of Prompts are executed successfully with generated the report.
