# Revised assembly programs

These are byte-for-byte copies of the two Robot Codex submissions used in the independent retest. The Windows evaluator checked the same SHA-256 digests before and after execution.

| Variant | Submitted file | SHA-256 |
| --- | --- | --- |
| A | [enclosure-61ad-A-fastening.cell](enclosure-61ad-A-fastening.cell) | `c3ef3249816d58b441cde63c4090964c314655fef2cc4c77a2b8a6844cff785a` |
| B | [enclosure-61ad-B-fastening.cell](enclosure-61ad-B-fastening.cell) | `dc0b1f5ba3d2da103ca1af90934e8f7a6aeb171a371d15421e0dadd5590339d2` |

The runner interprets the Python-like `.cell` files as bounded input. Both use the station’s device calls and define their own assembly logic. Start with `run()` for each job sequence and `drive()` for the revised feedback and seating checks. The station runtime and grader were separate components.

See [the MIT license](LICENSE) and [license scope](../LICENSE.md).
