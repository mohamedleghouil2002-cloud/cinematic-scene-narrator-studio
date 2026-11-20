---
name: cinematic-scene-narrator-studio
description: Build and refine an interactive web studio that turns stories, real-life incidents, or ideas into keyword-matched scenes with expressive narrator voices, mood atmospheres, and video or script export. Use when building or debugging a story-to-scene studio, cartoon 3D or realistic scene generator, multilingual narrator voice pipeline, or 1080p/2K/4K scene and video exporter.
---

# Cinematic Scene Narrator Studio

## Summary

Guide the generation and refinement of an interactive web studio that converts stories, incidents, or ideas into sequenced visual scenes with a visual style switcher (cartoon 3D inspired by Pixar/Disney or realistic film style), target video export resolutions up to 2K and 4K, smooth human-like AI narration without abrupt stops or robotic cadence, and script export. Keep browser prototypes transparent about browser 3D, high-resolution export, and speech engine limits while supporting external AI media or voice integrations.

## When to Use

Use this skill in these situations:

* Building or iterating on a story-to-scene or moment-to-scene web studio.
* Adding a visual style switcher between cartoon 3D (Pixar/Disney inspired) and realistic film scenes, plus mood and weather staging (dark clouds and rain for sad or tense scenes, bright warm light for happy scenes).
* Configuring smooth, continuous human-like narration via uploaded audio (`MP3` or `WAV`), realistic TTS API keys, or fallback browser speech without random mid-sentence stops.
* Adding `1080p`, `2K`, or `4K` video export options, script export, or debugging WebGL, `AudioContext`, and `MediaRecorder` behavior.

## Steps

1. **Support Cartoon 3D and Realistic Style Modes**: Provide a clear style switcher between cartoon 3D (warm, expressive stylized animation inspired by Pixar and Disney films) and realistic film style (lifelike people, vehicles, lighting, and weather). Because lightweight browser scripts cannot render feature-film animation or photorealism on their own, render an interactive scene prototype in the browser while generating ready-to-use style-matched prompts or external AI generation hooks for full visual fidelity.
2. **Stage Mood, Weather, and Camera Motion**: Parse story text into scenes and extract visual cues and emotions (`sad`, `tense`, `scary`, `dramatic`, `happy`). Shift skies, clouds, rain, lighting, color tone, and camera movement to fit the emotion and maturity of a short film.
3. **Deliver Smooth, Human-Like Narration**: Prioritize natural, continuous human-like speech without robotic tone or unexpected mid-sentence pauses. Support uploading pre-generated audio files (`MP3` or `WAV`) synced to playback, entering an optional realistic AI voice API key, and pairing with built-in `Web Audio` ambient soundscapes, keeping browser speech as a clearly labeled fallback with smooth sentence flow.
4. **Provide 1080p, 2K, and 4K Export Options**: Include export resolution selection (`1080p`, `2K`, `4K`) alongside video recording (`canvas.captureStream` with `preserveDrawingBuffer: true`, `MediaRecorder` with automatic `mimeType` detection, and `AudioContext` mixing when available) and script export, while clearly explaining browser memory/resolution limits and wrapping export logic in `try/catch` with status feedback.
5. **Test and Iterate One Component at a Time**: Validate using concrete multi-scene stories (such as a rainy night drive, an emotional moment, or a bright happy shift) and fix the exact broken component first before adding new features.

## Gotchas

* Lightweight browser 3D and `4K` canvas recording can strain memory or frame rates depending on the device and browser. Clearly surface export resolution notes, keep a responsive fallback, and generate ready-to-copy visual prompts when external AI video tools produce the final `2K`/`4K` render.
* Browser built-in speech (`Web Speech API`) can sound robotic, choppy, or drop/pause unexpectedly, and system speech may not always record into `MediaRecorder`. Always support uploaded `MP3`/`WAV` tracks, external realistic voice APIs, and `Web Audio` ambience with clear status indicators.
* Audio and recording APIs can fail without user interaction or error guards. Unlock audio on user action, use `try/catch`, and keep local fallbacks working on first load.
