# Artifact Sweep

[English](README.md) · [简体中文](README.zh-CN.md) · [日本語](README.ja.md)

> **Early preview** · Audio repair for AI-generated and digitally processed music.

## What it does

Artifact Sweep is designed to reduce gritty textures, fizz, and brittle highs that can linger after music generation, stem separation, or digital processing. It gives you control over the amount of repair while helping retain drum attacks, vocal detail, and instrument decay.

## How it works

The plug-in analyzes short slices of audio in the frequency domain. It estimates where attenuation is needed, smooths the changes over time, and reconstructs the audio. Strength, frequency focus, attack, and release let you adjust where and how quickly the processing takes effect.

The development build offers three views. The reduction graph shows how much is being attenuated. The line spectrum compares the original, processed, and removed signals. The spectrogram shows where changes occur over time and across frequencies.

## How to use it

1. Insert the plug-in on the track you want to repair and loop a passage where the artifacts are easy to hear.
2. Raise **Strength** gradually and toggle **Bypass** to compare.
3. Use **Noise only** to hear what is being removed. If you hear too much voice, percussion, or instrument detail, lower the strength or adjust the protection controls.

## Platform and release status

The development target is **Apple Silicon macOS**, with **VST3** and **AU** plug-in formats. The first public build is planned with an independently developed model. Source code, build instructions, and release notes will follow after the model and host validation are ready.
