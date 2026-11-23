# How we checked the fix

*Written by dot, Randy Crespo’s AI assistant.*

The strongest test wasn’t another successful demo. It was going back to the two setups that had already failed and changing just one thing: **which version of the program ran**.

## The two matched setups

Dev Codex started the old and new A programs from the same saved setup for each failure. The old program missed the same screw both times. The revised program seated both screws and finished both assemblies.

| Setup | Original program | Revised program |
| --- | --- | --- |
| First lid screw | Time ran out with the head still 0.321 mm above the lid. | The head made contact after 2.584 s of driving. The assembly passed. |
| Last lid screw | Time ran out with the head still 0.069 mm above the lid. | The head made contact after 2.576 s of driving. The assembly passed. |

Those gaps are tiny. A screw can look seated in the video without making contact. The readings show what the close-up can’t: at the same point in both drives, the driver spun at about **4 revolutions per second** while the screw turned at about **0.015**. The screw started moving again, but neither head reached the lid before the original 3.92-second time limit. That explains why the job stopped, not why the screw slowed down in the first place.

## What happened across the fresh jobs?

Dev Codex ran the submitted programs with the same MuJoCo simulator and grading rules. Each job started with a fresh staging of the cell. The saved program ran by itself; no agent steered the arm or intervened. To pass, it had to finish the assembly, confirm the screws were seated, complete the camera inspection, and deliver the product.

| Programs tested | Variant A | Variant B |
| --- | ---: | ---: |
| Original | 8 of 10 | 10 of 10 |
| Revised | 20 of 20 | 20 of 20 |

The original test ran 5 A jobs, 10 B jobs, then 5 more A jobs. The revised test doubled those blocks. Both original failures happened in the last A block, but that alone doesn’t show that switching variants caused them. One fresh B run in the revised test was interrupted before it could be graded. It passed when restarted from the same setup and counts once. The four matched replays above aren’t included in the fresh-job totals.

All tests were in simulation. They show what happened in these setups, not how often a physical robot would succeed.

## Where the videos came from

| Video | What you’re watching |
| --- | --- |
| [Revised A pass](../media/revised-a-pass.mp4) | A complete fresh run that passed, job `T04R-01-A`. |
| [Revised B pass](../media/revised-b-pass.mp4) | A complete fresh run that passed, job `T04R-11-B`. |
| [First screw failure](../media/original-a-first-screw-fail.mp4) | A 3.8-second cut from the original failure, job `T04-18-A`. |
| [Last screw failure](../media/original-a-last-screw-fail.mp4) | A 3.8-second cut from the original failure, job `T04-20-A`. |

The failure clips are continuous cuts through the moment each job stopped, not footage from the later replays. Watch the close-up on the right to see the screw pause and then move again. The rotation rates and gaps above come from simulation measurements, not estimates from the video. Each preview image is a still from its video.

[Original and revised programs](../programs/README.md) · [Optional checksums](../SHA256SUMS)
