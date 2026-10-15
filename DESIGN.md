# Design direction

## The central question

Can choosing a route through a zombie horde be as engaging as fighting it?

The first development target is a compact encounter that answers this question. Movement, readable obstacles, and enemy pressure take priority over map size or equipment variety.

## Intended loop

1. Read the street and choose a crossing.
2. Build speed, vault low obstacles, and commit to jumps.
3. Reach open space before the horde cuts off the exit.
4. Return through a different route as pressure increases.

## Movement targets

| Action | Design requirement |
| --- | --- |
| Sprint | Enough control to line up a jump without making turns feel weightless. |
| Jump | A consistent arc with clear takeoff and landing feedback. |
| Vault | Low obstacles become a route choice instead of a collision stop. |
| Ledge crossing | Height and distance must be readable before committing. |

## First encounter to build

A street with a wrecked vehicle, two elevated crossings, and a ground-level escape route. One crossing is short and exposed; the other takes longer but creates distance from the horde. The layout should loop back without requiring a loading screen.

## Next steps

These are planned tasks, not completed features.

- [ ] Establish the movement controller in a greybox test scene.
- [ ] Build and measure the two crossing routes.
- [ ] Add pursuing enemies and verify that both exits remain usable.
- [ ] Add wave escalation and a restart loop.
- [ ] Record a repeatable traversal test and document what needs adjusting.

## Outside the first pass

Multiplayer, progression systems, a large open world, and a release date are outside the initial scope. The movement encounter needs to work first.
