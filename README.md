# Germany EV Diffusion System Dynamics

System dynamics simulation project for electric vehicle diffusion in Germany.

The model studies how electric vehicles may diffuse into the German vehicle market through 2045 under interacting behavioral, infrastructure, technology, and policy feedback loops.

## Project Focus

Germany has ambitious transportation decarbonization targets, but electric vehicle adoption depends on more than vehicle availability. Adoption is shaped by charging infrastructure, range improvements, vehicle price learning, operating costs, consumer perception, word-of-mouth effects, and policy incentives.

This project models those interactions with a system dynamics approach.

## Model Variants

```text
models/
├── base_model.mdl
├── fast_charger_policy.mdl
├── fuel_price_scenario.mdl
└── technology_advancement_scenario.mdl
```

## Core Mechanisms

- EV and conventional vehicle stock dynamics
- consumer choice between EV and conventional vehicles
- operating cost utility
- initial purchase price utility
- EV range utility
- charging convenience utility
- word-of-mouth adoption loop
- charging station planning and construction delay
- EV price, range, and efficiency learning curves

## Experiments

### Base Simulation

Baseline EV adoption path without additional intervention beyond the model assumptions.

### Fast Charger Policy

Policy experiment increasing the desired share of fast chargers to test whether charging convenience accelerates EV adoption.

### Fuel Price Scenario

Scenario experiment where higher conventional fuel prices improve the relative operating cost utility of EVs.

### Technology Advancement Scenario

Scenario experiment where stronger EV range and performance improvements affect consumer adoption.

## GitHub Pages

Project page:

<https://fbaakyildiz.github.io/Germany-EV-Diffusion-System-Dynamics/>

## Documentation

- [Design document](docs/DESIGN.md)
- [Model files](models/)

## Tooling

The model files use the `.mdl` system dynamics model format. They are intended to be opened with compatible system dynamics tools such as Vensim.
