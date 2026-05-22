# MediaPipe TouchDesigner OSC

A TouchDesigner project that uses the venerated [MediaPipe TouchDesigner plugin](https://github.com/torinmb/mediapipe-touchdesigner) by [Torin Blankensmith](https://github.com/torinmb) to send OSC messages for face, hand, and pose tracking.

## Features

- **Face tracking** — sends OSC messages for facial landmark data
- **Hand tracking** — sends OSC messages for hand landmark data, with a **one-handed mode** for projects that only need a single hand
- **Pose tracking** — sends OSC messages for full-body pose landmark data, with **body centering** that normalizes position so pose data can be used as a control signal regardless of where the performer stands in frame

## Body Centering

When enabled, the body centering feature offsets all tracked pose landmarks relative to the body's detected center point. This means downstream systems receive pose data as relative movement — useful for interactive installations and performance tools where you want to react to how someone is moving rather than where they are in physical space.

## One-Handed Mode

Hand tracking normally tracks up to two hands. One-handed mode locks tracking to a single hand, which can simplify OSC routing and reduce noise in projects that only need one hand as input.

## Requirements

- [TouchDesigner](https://derivative.ca/) (tested on recent stable builds)
- [MediaPipe TouchDesigner plugin](https://github.com/torinmb/mediapipe-touchdesigner) by Torin Blankensmith

## Files

- `MP-TD-OSC.toe` — the main TouchDesigner project file
- `MediaPipe.tox` — the MediaPipe plugin component

## Usage

1. Install the MediaPipe TouchDesigner plugin per its documentation.
2. Open `MP-TD-OSC.toe` in TouchDesigner.
3. Configure the OSC output IP address and port to match your receiving application.
4. Enable the tracking modes you need (face, hand, pose).
5. Toggle body centering and/or one-handed mode as needed for your project.

## License

MIT — see [LICENSE](LICENSE).
