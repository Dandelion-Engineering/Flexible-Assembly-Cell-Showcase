# Independent evaluation and media provenance

## The trial record

Dev Codex verified the submitted program bytes and ran each job on a pinned Windows evaluator with MuJoCo 3.3.7. The grader checked physical assembly and seating, camera observations, delivery and the final state of the cell. Each planned job started from a fresh simulated staging. The simulator ran unattended.

| Campaign | Order | Variant A | Variant B | Total |
| --- | --- | ---: | ---: | ---: |
| Original comparison, November 21, 2026 (UTC) | 5 A, 10 B, 5 A | 8/10 | 10/10 | 18/20 |
| Revised retest, November 23, 2026 (UTC) | 10 A, 20 B, 10 A | 20/20 | 20/20 | 40/40 |

The original comparison covered `T04-01-A` through `T04-20-A`. Two separately checked original first articles also passed, `A-61ad-009` and `B-61ad-006`. Those two are outside the table.

The revised campaign covered `T04R-01-A` through `T04R-40-A`. The first start of `T04R-19-B` was interrupted before a grader verdict. A new process restarted that job with the same preselected staging seed and passed. The table counts one scored result per planned job, along with the 39 other completed fresh jobs. Across the 40 scored runs the grader confirmed head contact for all 80 A and 120 B screw drives.

The normalized evaluator pin manifest was verified before and after execution. Its SHA-256 was `0dbd80ccf6d9aeb9b18b35f56609173ec32614d2835c8a794376aa504541dabb`. The [submitted programs and digests](../programs/README.md) identify the revised byte streams. The trials establish outcomes for the tested simulated setups. No physical hardware was tested.

## The two matched setups

The revised retest separately ran each saved A setup once with the exact original A and once with revised A. The original replays matched the historical initial and terminal state, command log, frame count, step count and verdict. The revised replays matched the same starting state and staging. These four replays are outside the fresh counts.

| Original job and screw | Original-program replay | Revised-program replay |
| --- | --- | --- |
| `T04-18-A`, first lid screw (southwest) | `T04-18-A-original` failed. The head never bore on the lid during the 3.920 s powered drive. | `T04-18-A-revised` passed. First head contact was logged 2.584 s after spindle start and the grader confirmed seating. |
| `T04-20-A`, last lid screw (northwest) | `T04-20-A-original` failed at a 3.920 s spindle stop without head bearing. | `T04-20-A-revised` passed. First head contact was logged 2.576 s after spindle start and the grader confirmed seating. |

The close-up in each historical clip shows slow screw travel and renewed descent. Diagnostic runs matched to those original failures measured about 3.99 spindle rev/s and 0.015 screw rev/s at 0.8 simulated seconds into each drive. The first screw nearly stalled from 55.352 to 56.720 simulated seconds (1.368 s). The last nearly stalled from 91.368 to 92.608 simulated seconds (1.240 s). That starts about 1.4 seconds into each clip. The screw picked up speed in both cases. The measured head gaps at the stop were 0.321 mm and 0.069 mm, respectively. Those small gaps and the two rotation rates come from the evidence traces.

## Media provenance

| File | Independently scored source | Playback | Source frame range and simulated time |
| --- | --- | ---: | --- |
| [Revised A full run](../media/revised-a-pass.mp4) | Fresh `T04R-01-A`, revised A, accept | 86.9 s | Frames 0–868. Staged at 0 s, terminal at 131.816 s. |
| [Revised B full run](../media/revised-b-pass.mp4) | Fresh `T04R-11-B`, revised B, accept | 132.2 s | Frames 0–1321. Staged at 0 s, terminal at 200.584 s. |
| [Original first-screw failure](../media/original-a-first-screw-fail.mp4) | Historical `T04-18-A`, original A, fail | 3.8 s | Frames 351–388. Approach at 53.240 s, spindle command from 54.848 to 58.768 s, last frame at 58.768 s. |
| [Original last-screw failure](../media/original-a-last-screw-fail.mp4) | Historical `T04-20-A`, original A, fail | 3.8 s | Frames 588–625. Approach at 89.264 s, spindle command from 90.864 to 94.784 s, last frame at 94.784 s. |

The passing movies are byte-for-byte copies, with both original camera views and their job labels. The A poster is frame 434 (65.856 simulated seconds). The B poster is frame 536 (81.360 simulated seconds), around the open-carrier inspection. The failure clips are re-encoded, contiguous cuts from the original campaign captures. They keep the original 10 frames/s and both original views. Each contains 38 decoded frames and includes the terminal frame. Playback time follows the recorder’s cadence. The on-screen counter gives simulated time.

The two original capture digests match the original campaign ledger. Every full run and clip was decoded, with frame counts and timestamps checked against the source and frame map. The original captures and the files in this showcase can be identified by these SHA-256 digests.

| Recording | Original capture SHA-256 | Showcase SHA-256 |
| --- | --- | --- |
| Revised A full run | `253cbd107a05545e911e23efaacc170e753d90901e1443fd5068048a4d830924` | Same as capture |
| Revised B full run | `ccafa5797814c9ffc0612631db1a7fc595e37909f79bbc2d41b71489e07c5698` | Same as capture |
| Original first-screw failure | `b6a47cdbbe3fcc73894d5d2be6e87817b67f0d4a15343ddc83df3dcb452106d1` | `93f7bfac17238b98ff6634799ee2368385e4a6d4af7e23a2ca554fad3d37352b` |
| Original last-screw failure | `34ef30193fe06e93215606138c9de72cdbbd9e2592b76436ad51f3b9ab073ebf` | `795b2330c64fc9a3d94e11f75b10c15f778d9dbfb8b75272bec14525e3c37bc1` |
