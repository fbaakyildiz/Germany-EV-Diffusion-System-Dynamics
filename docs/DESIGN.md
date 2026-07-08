# Design Document

## Project Objective

This project models electric vehicle diffusion in Germany using a system dynamics approach. The goal is to understand how infrastructure, technology, consumer behavior, and policy feedback loops interact over time and influence EV market share.

The model horizon extends toward 2045, matching Germany's long-term transportation decarbonization context.

## Modeling Approach

The project uses system dynamics because EV diffusion is not a one-directional forecasting problem. Adoption changes infrastructure needs, infrastructure changes charging convenience, charging convenience changes consumer utility, and consumer utility changes future adoption.

The model therefore represents multiple reinforcing and balancing loops instead of treating EV adoption as a static trend line.

## System Boundary

### Included

- electric vehicle stock
- conventional vehicle stock
- vehicle retirement
- consumer choice between EV and conventional vehicles
- EV charging infrastructure
- fast charger share
- expected charging and waiting time
- EV price learning
- EV range improvement
- operating cost comparison
- word-of-mouth effects
- policy and scenario experiments

### Excluded

- detailed manufacturer competition
- regional differences inside Germany
- second-hand vehicle market detail
- explicit grid capacity constraints
- household-level heterogeneity
- vehicle production supply-chain constraints

## Dynamic Hypothesis

EV adoption accelerates when improvements in technology and infrastructure increase the perceived utility of EVs relative to conventional vehicles. Charging convenience and word-of-mouth effects create reinforcing loops, while vehicle retirement and market saturation create balancing behavior.

## Core Feedback Loops

### Charging Infrastructure Loop

More EVs increase the desired number of charging stations. This creates a gap between desired and available infrastructure, triggering planning and construction. After a delay, additional charging stations reduce expected waiting time and improve EV convenience, increasing EV attractiveness.

### Word-of-Mouth Loop

As EV share grows, more consumers are exposed to EV ownership experiences. This increases the fraction of potential EV customers and reinforces adoption.

### Technology Learning Loop

Accumulated EV production and adoption improve price, range, and efficiency assumptions through learning effects. Better technology increases EV utility and can accelerate diffusion.

### Retirement Balancing Loop

Vehicle stocks decline through retirement. Retired vehicles create replacement decisions, where consumers choose between EVs and conventional vehicles based on relative utility.

## Model Files

- `base_model.mdl` - baseline system dynamics model.
- `fast_charger_policy.mdl` - policy experiment for increasing the desired share of fast chargers.
- `fuel_price_scenario.mdl` - scenario experiment for increased conventional fuel prices.
- `technology_advancement_scenario.mdl` - scenario experiment for stronger EV technology progress.

## Consumer Decision Structure

The consumer decision structure compares EV and conventional vehicle attractiveness through utility factors:

- purchase price
- operating cost
- range
- charging or refueling convenience
- word-of-mouth and social exposure

The model combines these utility signals into an adoption mechanism that shifts the market share of EVs over time.

## Charging Infrastructure Submodel

The charging infrastructure submodel includes:

- total charging stations
- fast charging stations
- desired charger-to-vehicle relationship
- planning and construction delay
- average charging time
- expected waiting time
- perceived charging convenience

This allows infrastructure to respond to EV adoption with realistic delays.

## Policy and Scenario Analysis

The model supports intervention testing by modifying assumptions and comparing output behavior.

### Fast Charger Policy

Tests the effect of increasing the desired percentage of fast chargers. This targets the charging convenience bottleneck rather than vehicle technology directly.

### Fuel Price Scenario

Tests how higher conventional fuel prices improve the relative operating-cost position of EVs.

### Technology Advancement Scenario

Tests how faster improvements in EV range, price, or efficiency can influence adoption.

## Expected Outputs

Typical model outputs include:

- EV share of total vehicles
- conventional vehicle share
- total EV stock
- charging station stock
- fast charger percentage
- average EV range
- consumer utility components
- adoption rate over time

## Verification and Validation

The model was designed with structural and behavioral checks:

- dimensional consistency of major relationships
- plausibility of feedback loops
- extreme-condition behavior
- historical behavior comparison for EV share
- sensitivity to policy and scenario assumptions

## Limitations

The model is a decision-support and learning tool, not a production-grade forecast engine. Results depend on assumptions about consumer behavior, policy response, charging infrastructure delays, and technology improvement rates.

Future extensions could add regional heterogeneity, explicit grid constraints, cost-benefit analysis, uncertainty sampling, and interactive scenario controls.
