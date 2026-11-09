<h1 align="center">Artifact Sweep</h1>

[English](README.md) · [简体中文](README.zh-CN.md) · [日本語](README.ja.md)

> **Early preview** · Audio repair for AI-generated and digitally processed music.

## What it does

Artifact Sweep is designed to reduce gritty textures, fizz, and brittle highs that can linger after music generation, stem separation, or digital processing. It gives you control over the amount of repair while helping retain drum attacks, vocal detail, and instrument decay.

## How it works

The plug-in analyzes short slices of audio in the frequency domain. It estimates where attenuation is needed, smooths the changes over time, and reconstructs the audio. Strength, frequency focus, attack, and release let you adjust where and how quickly the processing takes effect.

The development build offers three views. The reduction graph shows how much is being attenuated. The line spectrum compares the original, processed, and removed signals. The spectrogram shows where changes occur over time and across frequencies.

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

The development target is **Apple Silicon macOS**, with **VST3** and **AU** plug-in formats. Source code, build instructions, and release notes will follow after audio-quality and host validation are complete.
