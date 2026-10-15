# Gameplay notes

This is the design I'm aiming for. The priorities below describe what to build and test.

## What to borrow

From Mirror's Edge: momentum, contextual vaulting, wall runs, ledge catches and recovery rolls. Routes need to read at speed. Red paint, railings, light and the shape of a landing can suggest a crossing without drawing a line through the whole level. The full movement kit should be available from the start.

From Black Ops II Zombies: escalating rounds, crowd management, revives, spending points to open the map and secrets that give a familiar location another purpose. The useful tension is deciding whether to spend, explore or return for a teammate while the next round gets closer.

The combination needs its own enemy routes. If the player reaches a roof and every zombie waits in the street, the central idea stops working.

## Dead Block

Start with one connected arena: a bus intersection below a shop, an apartment stairwell and a maintenance roof. Build a fast crossing over the bus, a safer interior route and a rooftop loop with two ways down.

Opening the shop shutters should connect two existing routes. Restoring power should open a service gate and start a noisy event. Each objective needs to change how players move through the block.

A missed rooftop jump should sometimes leave the player on a lower balcony or back in the street. A clearly fatal fall can still kill. The level needs both recovery opportunities and consequences the player can read before jumping.

## The crew

Proposed characters, with names and designs still open:

| Runner | Character direction |
| --- | --- |
| Kite | A former courier who remembers the city before the streets closed. Worn running shoes, a light jacket and a red glove. |
| Fuse | A maintenance worker with a tool harness and soot on everything. Knows which doors were never meant to open. |
| Patch | A street medic with a battered field bag. Keeps talking to people even when they stop answering. |
| Rook | A scavenger in repaired clothes, carrying more keys than supplies. Always asks who is coming back for the bag. |

Begin with one shared character rig and movement controller. Different silhouettes, clothing, first-person hands and a small set of contextual voice lines would establish the crew before unique abilities become necessary.

If gadgets earn their place, test a thrown noise lure, smoke to break sight and a temporary barricade. Keep them swappable between runners until there is a good reason to create fixed roles.

## Co-op that serves the movement

Target solo play and private sessions for two to four players. Start network testing with two.

A player can draw the crowd away from a revive or lead it through a longer route while someone opens a shortcut. Those interactions should come from the map and enemy behaviour before adding special co-op animations.

Use a host-authoritative session for the first networking pass: the host owns enemy decisions, damage, round state and purchases. Responsive local movement still needs prediction, correction and interpolation. Hosting, joining across the internet, disconnects and lobby behaviour need explicit work; an engine's networking API does not solve the whole experience.

## The horde

Begin with ordinary pursuers following authored street and climbing connections. Add a limited number of climbers that can reach marked rooftop entries. Test fast interceptors only after both are readable.

Enemy pressure should force a route decision. Spawning enemies directly onto the player's landing or making every zombie match the player's parkour would make learning the map less useful.

## Build order

1. Make one traversal loop feel good, including a failed jump and recovery.
2. Run that loop with two networked players.
3. Add a small pursuing group and one rooftop entry.
4. Add rounds, a downed state, revives and one purchasable shortcut.
5. Test four players and tune the active enemy count to measured performance.
6. Expand the crew, secrets and challenge routes once the encounter holds up.

An open world, competitive PvP and a large hero ability roster would each multiply the work. Keep them outside the first map.

## What the replies suggest

The [original post's replies](https://x.com/bonnyxen/status/2110747071498051892) are a small, self-selected sample. They offer ideas to test, not a settled feature wishlist.

| Observed response | Design implication to test |
| --- | --- |
| Five different accounts compare the clip to Dying Light. | Make the round-based, compact-map loop distinct enough that players can describe the difference after playing. The comparisons alone do not show approval or rejection. |
| [Himookim asks for Mirror's Edge mixed with Outlast](https://x.com/himookim/status/2110787344018329766), specifically escaping a pursuer through parkour. This had 16 likes when checked. | Test whether a dangerous individual pursuer adds fear and makes traversal more satisfying. This is the clearest specific new mechanic suggestion in the visible replies. |
| [One reply asks for Left 4 Dead](https://x.com/koikrip/status/2110828720063942817). | Co-op survival is worth testing, but that short comment does not establish demand for a particular party size, rescue system or character roster. |
| [Vista Larga Games asks how it actually plays](https://x.com/VistaLargaGames/status/2110801734658556019). | A future demonstration should show a complete encounter: choosing a route, making a mistake, recovering and ending the round. |

My reading is that fast movement becomes more interesting when there is a threat close enough to make the escape matter. The Outlast suggestion supports testing that idea. It does not establish that the whole audience wants a horror mode.

### A blackout chase to test

Use the existing Dead Block layout. After a clear power-failure cue, emergency lights reveal familiar crossings while one original pursuer enters through a visible route. Give it a recognisable footstep rhythm and a limited set of climbing connections.

Let players break line of sight through the shop or create distance across rooftops. The pursuer should keep travelling through the level, never teleport onto a landing. An unreachable hiding spot or a chase that never releases pressure would both defeat the point.

Test this as a short optional event first. Measure whether players choose to trigger it again, whether they can explain how they escaped and whether they describe the encounter as tense or unfair. A positive response could justify a separate pursuit challenge later.

Character abilities and progression remain my design proposals rather than requests established by these replies.

## Questions for players

- Is the main draw rescuing friends, surviving high rounds or mastering routes?
- Does a missed jump create a good scramble, or feel like a cheap loss?
- Are the runners interesting as characters before they have unique abilities?
- Does the rooftop loop stay tense once the whole group knows it?

Use feedback to choose the next test. Requests and enthusiasm can suggest a direction; repeat play is better evidence that the loop works.

## References

- [DICE on contextual movement and chaining moves](https://www.ea.com/amp/news/movement-in-mirrors-edge-catalyst-the-basics)
- [DICE on Runner's Vision and maintaining momentum](https://www.ea.com/amp/news/runners-vision-in-mirrors-edge-catalyst)
- [Black Ops II manual: Survival, Grief and TranZit](https://support.activision.com/servlet/servlet.FileDownload?file=00PU0000004ZQcPMAW&retURL=%2Fapex%2Fmanuals)
- [Godot multiplayer documentation, as an implementation reference](https://docs.godotengine.org/en/stable/tutorials/networking/high_level_multiplayer.html)

These are design and technical references, not a statement of affiliation or an engine choice.
