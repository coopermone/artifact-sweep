<h1 align="center">Artifact Sweep</h1>

[English](README.md) · [简体中文](README.zh-CN.md) · [日本語](README.ja.md)

> **Version 1.0 — available now** · Audio repair for AI-generated and digitally processed music.

## What it does

Artifact Sweep is designed to reduce gritty textures, fizz, and brittle highs that can linger after music generation, stem separation, or digital processing. It gives you control over the amount of repair while helping retain drum attacks, vocal detail, and instrument decay.

## How it works

The plug-in includes an embedded AI audio model that runs locally on your computer. It analyzes short slices of audio in the frequency domain and estimates how much to attenuate each frequency band. Conventional signal processing smooths those changes over time and reconstructs the audio. Strength, frequency focus, attack, and release let you control where and how quickly processing takes effect. Audio does not need to be uploaded for processing.

The plug-in offers three views. The reduction graph shows how much is being attenuated. The line spectrum compares the original, processed, and removed signals. The spectrogram shows where changes occur over time and across frequencies.

### Cleaned spectrogram

Select **Cleaned** to see the signal after processing. Time runs left to right, frequency rises vertically, and brighter colors indicate higher levels.

![Cleaned spectrogram from the Artifact Sweep plug-in](docs/images/artifact-sweep-cleaned.png)

## How to use it

1. Insert the plug-in on the track you want to repair and loop a passage where the artifacts are easy to hear.
2. Raise **Strength** gradually and toggle **Bypass** to compare.
3. Use **Noise only** to hear what is being removed. If you hear too much voice, percussion, or instrument detail, lower the strength or adjust the protection controls.

### Inspect and listen to what was removed

Select **Removed** to see the removed component over time and across frequencies. This changes the display only. To hear that component on its own, switch on **Noise only** in the Monitor panel.

![Removed-component spectrogram from the Artifact Sweep plug-in](docs/images/artifact-sweep-removed.png)

## Platform and release status

**[Download Artifact Sweep 1.0](https://github.com/coopermone/artifact-sweep/releases/tag/v1.0.0-preview.1)** — English and Simplified Chinese **VST3 / AU** for **Apple Silicon macOS**.

The installer is not Developer ID signed or notarized. Quality matching against 0.3.5 is still in progress; some drum and full-mix passages differ, and CPU / real-time performance need further optimization. See the release notes for installation details and limitations. Future updates will continue improving the model and performance.

The complete plug-in source and build instructions are not yet public. GitHub's automatic source archives currently contain the public project materials only.
