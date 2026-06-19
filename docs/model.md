# Simulation Model Notes

FungalLight represents fungal growth as local updates over a 2D grid.

## State

- `GridFood`: remaining resources for each grid cell.
- `GridRestriction`: binary restriction mask derived from an input image.
- `FungiSpawnPositionList`: candidate cells scheduled for spawning.
- `FungiExistPositionList`: occupied positions used to prevent duplicate spawning.

## Growth Loop

Each living fungi entity:

1. consumes food at its current cell,
2. samples a local neighboring position,
3. spawns into free space,
4. emits a short-lived light marker when it hits a restricted boundary,
5. dies if food is exhausted or by random death probability.

The visual state reflects food availability and boundary interaction.

## Restriction Mask

`RESTRICTION_IMAGE` points to an image mask used to turn selected pixels into blocked cells. This allows shape constraints to be authored visually and then executed inside the simulation.

## Relationship to the Paper

The paper studies fungal morphology simulation and dynamic light containment from a graphic generation perspective. This repository is a compact Rust/Bevy prototype for the simulation component and is intended as a readable starting point for further experimentation.
