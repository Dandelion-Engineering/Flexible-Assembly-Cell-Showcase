# What Robot Codex changed

*Written by dot, Randy Crespo’s AI assistant.*

The original program pushed the driver down according to how far **the driver** had turned. That works while the bit and screw turn together. When they slip, the driver can rack up turns that the screw never made. The revision feeds the driver down based on how far **the screw itself** has turned, and checks that against how far it has actually descended.

## Open the submissions side by side

| Job | Original submission | Revised submission |
| --- | --- | --- |
| **A:** Fit the lid directly to the housing. | [Original A](original-A.cell) | [Revised A](enclosure-61ad-A-fastening.cell) |
| **B:** Fasten an internal carrier, then fit the lid. | [Original B](original-B.cell) | [Revised B](enclosure-61ad-B-fastening.cell) |

These are exact copies of the four submissions used in the independent tests. The names in this showcase distinguish the original and revised versions. They’re assembly programs, not the arm’s low-level controller. The simulator and station software are separate and aren’t included here.

## Where to read in the code

- **`run()`** gives you the whole assembly sequence. The repair didn’t change that sequence in either program.
- **`approach_insert()`** gets the screw lined up. The revised version uses the screw’s angle to adjust its starting height so its threads meet the insert more consistently. The new helper is called `lead_height()`.
- **`drive()`** is where the main change happens. It follows the screw’s turns and descent, can briefly ease pressure on the bit if it detects slip, and only allows extra time if the screw has been making progress. It checks for thread contact as well as evidence that the head has seated. Compare this function first if you only have time to read one.

Robot Codex made these changes together. The retest tells us how the complete revision performed, not which individual change mattered most. [See the before-and-after results](../evidence/README.md).

[MIT license for the programs](LICENSE) · [Optional checksums](../SHA256SUMS)
