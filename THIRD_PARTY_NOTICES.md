# Credits and third-party notices

*Written by dot, Randy Crespo’s AI assistant.*

This showcase includes four assembly programs, videos, and still images. It does not ship the simulator, a copy of the robot model, or any of the software used to record the videos.

## What you see in the videos

- **The arm** is a simulated Universal Robots UR5e. The cell uses the [UR5e model from MuJoCo Menagerie](https://github.com/google-deepmind/mujoco_menagerie/tree/32224735cf004df068cd29ba099459f71bcd7d21/universal_robots_ur5e), which credits ROS-Industrial for the original visuals. The project kept the upstream visual meshes but adapted the arm’s placement, hierarchy, servo settings, contact masks, and tool attachment for this cell. See the [Menagerie license](https://github.com/google-deepmind/mujoco_menagerie/blob/32224735cf004df068cd29ba099459f71bcd7d21/LICENSE) and the [full UR5e BSD 3-Clause notice](licenses/UR5e-BSD-3-Clause.txt).
- **The labels** use [Aileron Regular](https://dotcolon.net/fonts/aileron/) by Sora Sagano, under [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/). They’re drawn into the video, not distributed as a separate font file. Pillow 11.3.0 used its [bundled font subset](https://github.com/python-pillow/Pillow/blob/11.3.0/src/PIL/ImageFont.py), based on the designer’s 0.102 release (internal version 1.102; [subset details](https://github.com/python-pillow/Pillow/pull/7354)).
- **The rest of the cell** (the tooling, product, and generated scene textures) comes from Dandelion Engineering’s project. The clips are silent, and each preview image is a still from its video. [See where the videos came from](evidence/README.md#where-the-videos-came-from).

## Tools used, not bundled

| Tool | What it did | Upstream terms |
| --- | --- | --- |
| MuJoCo 3.3.7 | Ran the physics and rendered the cell. | [Apache-2.0](https://github.com/google-deepmind/mujoco/blob/3.3.7/LICENSE); [wheel notices](https://pypi.org/project/mujoco/3.3.7/#third-party-licenses). |
| CPython 3.12.10 | Ran the evaluator. | [Python Software Foundation License and historical notices](https://github.com/python/cpython/blob/v3.12.10/LICENSE). |
| Pillow 11.3.0 | Put the camera views and labels together. | [MIT-CMU (Pillow and PIL licenses)](https://github.com/python-pillow/Pillow/blob/11.3.0/LICENSE). |
| imageio-ffmpeg 0.6.0 | Connected the recording code to the video encoder. | [BSD 2-Clause](https://github.com/imageio/imageio-ffmpeg/blob/v0.6.0/LICENSE). |
| FFmpeg 7.1 with x264 core 164 r3192 | Encoded the videos and cut and checked the clips. | [FFmpeg terms](https://github.com/FFmpeg/FFmpeg/blob/n7.1/LICENSE.md) (GPL v3 or later for the [Windows essentials build](https://www.gyan.dev/ffmpeg/builds/)); [x264 source](https://code.videolan.org/videolan/x264/-/commit/c24e06c2e184345ceb33eb20a15d1024d9fd3497) (GPL-2.0-or-later). |

The four programs call the cell’s existing interfaces. They don’t bundle the simulator or import third-party code. [What you can reuse](LICENSE.md)
