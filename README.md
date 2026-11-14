<h1 align="center">Artifact Sweep</h1>

[English](README.md) · [简体中文](README.zh-CN.md) · [日本語](README.ja.md)

## 🎉 Celebrating the release of 2.0

**A major step forward for Artifact Sweep’s restoration engine.** 🧠 Version 2.0 updates the embedded audio model and resolves the remaining drum, guitar and dense-mix discrepancies in our current comparison suite. 🎧 We checked both starting directly at a passage and playing into it continuously, so the improvement covers the playback-state problem found in 1.2.

🌈 Explore the results with the color spectrogram, compare original and cleaned audio, and use **Noise only** to hear what was removed. 🎛️ Your familiar controls and layout stay in place. All audio processing runs locally.

## Designed for digitally processed music

Artifact Sweep is an audio repair plug-in for the gritty textures, fizz, and brittle highs that can remain after AI music generation, stem separation, or digital processing. Adjustable repair strength and protection controls help you balance artifact reduction with drum attacks, vocal detail, and instrument decay.

It is designed for musical artifacts rather than a single fixed noise profile. Results depend on the source: stronger attenuation can also remove desirable musical content, so comparison and residual monitoring are part of the workflow.

## Local AI with controllable signal processing

An embedded AI audio model runs on your computer. It analyzes short slices of audio in the frequency domain and estimates attenuation across frequency bands. Signal processing smooths those estimates over time and reconstructs the audio. Processing does not require uploading audio.

Strength sets the overall amount of repair; frequency focus adjusts where processing is emphasized. Attack and release shape how quickly attenuation engages and recovers. Protection and resonance controls provide additional ways to preserve detail and manage narrow spectral peaks. The frequency-focus curve changes the processing emphasis; it is not a conventional output EQ.

## Main controls

| Control group | Purpose |
| --- | --- |
| Strength, attack and release | Adjust processing amount and response over time. |
| Frequency focus | Emphasize or relax repair in selected frequency regions. |
| Detail, transient and high-frequency tail protection | Balance cleanup with attacks, texture and decays. |
| Resonance controls | Adjust the depth, threshold and selectivity of resonance suppression. |
| Auto sheen and harmonic / percussive fill | Shape brightness and reconstructed texture; these do not guarantee recovery of missing original detail. |
| Low latency | Request the lower-latency processing mode; actual latency and CPU load depend on host settings and processing mode. |
| Bypass, Noise only, A/B and presets | Compare settings and hear what processing removes. |
| Wet mix and output | Blend the processed signal and adjust output level. |

## Three complementary analysis views

| View | What it shows |
| --- | --- |
| Focus / Reduction | Frequency emphasis and the amount of attenuation. |
| Line spectrum | Color-separated curves for the original, cleaned and removed signals. |
| Spectrogram | Sound energy across time and frequency, with original, cleaned and removed views. |

### Inspect the cleaned signal

Select **Cleaned** in the spectrogram to see the processed signal. Time runs left to right, frequency rises vertically, and brighter colors indicate higher levels. Switching the display does not change the audio output.

![Cleaned spectrogram from Artifact Sweep](docs/images/artifact-sweep-cleaned.png)

### Inspect and listen to what was removed

Select **Removed** to inspect the removed component. To hear it on its own, enable **Noise only** in the Monitor panel. Removed audio can contain musical content as well as unwanted artifacts: use it to judge whether processing is too strong.

![Removed-component spectrogram from Artifact Sweep](docs/images/artifact-sweep-removed.png)

The screenshots show the established interface; the downloaded 2.0 build uses the same control layout.

## A practical starting workflow

1. Insert Artifact Sweep on the track you want to repair and loop an affected passage.
2. Increase **Strength** gradually, using **Bypass** to compare with the source.
3. Enable **Noise only**. If too much voice, percussion or instrument detail is removed, lower Strength or increase the appropriate protection.
4. Adjust frequency focus and resonance controls only where needed. Check both a dense passage and a quieter decay.
5. Compare settings with **A/B**, then set wet mix and output for the track.

## Download and install

Version 2.0 includes English and Simplified Chinese **VST3 / Audio Unit** plug-ins for **Apple Silicon Mac**. Intel Mac and Windows builds are not included.

Download **Artifact-Sweep-2.0-macOS-arm64.pkg** from the [release Assets](https://github.com/coopermone/artifact-sweep/releases/tag/v2.0.0). Quit your DAW, run the installer, then reopen the host and rescan plug-ins. Select **Artifact Sweep** or **Artifact Sweep CN**.

The installer is **not Developer ID signed or notarized**; macOS may display a warning or block it. Do not disable system-wide security protections. Keep an existing working version if you need to compare releases.

## 🚀 What changed from 1.2 to 2.0

| Area | 1.2 | 2.0 |
| --- | --- | --- |
| 🥁 Drums and 🎸 guitars | Some passages still missed our fixed audio-comparison thresholds. | All current drum and guitar comparison checks pass. |
| 🎧 Dense mixes | Low-frequency removed-waveform alignment remained unresolved. | The difficult second mix excerpt passes, alongside the full-track check. |
| ▶️ Playback state | Direct starts and continuous playback exposed different errors. | Both conditions checked, with 0, 125, 500, 1,000 and 2,000 ms of preceding audio. |
| 🌈 Workflow | Three analysis views and detailed repair controls. | Same layout and controls with the updated model. |

On the same difficult mix excerpt, removed-waveform cosine similarity to our fixed validation target rose from **0.9272 in 1.2 to above 0.9999 in 2.0**. This measures agreement with a fixed target on the tested material. It is not a noise-removal percentage or a universal listening-quality score. Broader music and host testing will continue.

```mermaid
flowchart LR
    V12["1.2 · Low-frequency refinement"] --> V20["🎉 2.0 · Updated restoration core"]
    V20 --> Audio["🥁 🎸 🎧 Current audio checks pass"]
    V20 --> Playback["▶️ Direct and continuous playback verified"]
```

## Project and source status

The installer is publicly available. The complete plug-in source and build instructions are not yet public. GitHub's automatic source ZIP / TAR archives currently contain the public project materials, not the complete software source.

For feedback, use [GitHub Issues](https://github.com/coopermone/artifact-sweep/issues) and include your host, sample rate, buffer size and plug-in version.

**[Download for Apple Silicon Mac](https://github.com/coopermone/artifact-sweep/releases/tag/v2.0.0)** · English & Simplified Chinese · VST3 / AU
