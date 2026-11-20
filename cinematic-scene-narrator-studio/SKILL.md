---
name: cinematic-scene-narrator-studio
description: Build and refine an interactive web studio that turns stories, real-life incidents, or ideas into sequenced visual scenes and videos using either text descriptions alone or user-uploaded reference photos for characters, vehicles, or locations, in cartoon 3D (Pixar/Disney-inspired) or realistic styles, with smooth human-like AI narration and 1080p/2K/4K or script export. Use when building or debugging an OpenArt-style story-to-scene and video studio with reference photo inputs, style switching, voice pipelines, or video/script export.
---

# Cinematic Scene Narrator Studio

## Summary

Guide the generation and refinement of an interactive web studio inspired by OpenArt AI workflows that turns stories, real-life incidents, or ideas into sequenced visual scenes and videos. Support two clear generation paths: text-description-only generation and reference-photo-guided generation (uploading photos of characters, specific vehicle models/types, or real incident locations so scenes stay consistent with those references), with cartoon 3D (Pixar/Disney-inspired) and realistic styles, smooth human-like narration without abrupt stops or robotic cadence, `1080p`/`2K`/`4K` video export options, and script export.

## When to Use

Use this skill in these situations:

* Building or iterating on an OpenArt-style story-to-scene and video web studio.
* Supporting both text-only scene/video generation and uploaded reference images (characters, car type/model, or incident location) paired with visual style switching (`Cartoon 3D` vs. `Realistic`) and mood/weather staging (dark clouds and rain for sad or tense moments, bright warm light for happy moments).
* Configuring continuous, natural human-like narration via uploaded audio (`MP3`/`WAV`), realistic AI voice API keys, or fallback browser speech without random mid-sentence stops.
* Adding `1080p`, `2K`, or `4K` export options, script export, or handling browser 3D, `AudioContext`, `FileReader`/image preview, and `MediaRecorder` limits cleanly.

## Steps

1. **Offer Text-Only and Reference-Photo Workflows**: Support generating scenes and videos from story text descriptions alone, AND provide clean reference-photo upload slots (for characters, specific car type/model, or the actual location where an incident happened) with instant image previews, reference tags, and style-matched prompts (`Cartoon 3D` inspired by Pixar/Disney or `Realistic` film style) or external image-to-video / AI generation hooks.
2. **Stage Mood, Weather, and Scene Continuity**: Parse story text into sequenced scenes, preserve character/vehicle/location consistency across scenes using either text cues or uploaded reference photos, and shift clouds, rain, lighting, color tone, and camera motion to match emotions (`sad`, `tense`, `scary`, `dramatic`, `happy`) in a mature short-film tone.
3. **Deliver Smooth, Human-Like Narration**: Prioritize natural, continuous human-like speech without robotic tone or unexpected mid-sentence pauses. Support uploading `MP3`/`WAV` voice tracks synced to playback, entering an optional realistic AI voice API key, and mixing built-in `Web Audio` ambient soundscapes, keeping browser speech as a clearly labeled fallback with smooth sentence flow.
4. **Provide 1080p, 2K, and 4K Export Options**: Include resolution selection (`1080p`, `2K`, `4K`) for video recording (`canvas.captureStream` with `preserveDrawingBuffer: true`, `MediaRecorder` with automatic `mimeType` detection, and `AudioContext` mixing when available) alongside script export, while clearly explaining browser resolution/memory limits or external AI render hooks and wrapping operations in `try/catch` with clear status feedback.
5. **Test and Iterate One Component at a Time**: Validate using concrete multi-scene stories (such as a rainy night drive, an incident at a specific place, or a shift to a bright happy mood) with both text-only and reference-photo inputs, fixing one broken piece at a time.

## Gotchas

* Pure browser scripts cannot run full OpenArt-grade diffusion/video models locally or render true `4K` cinema on every device without heavy memory use or external AI APIs/workflows. Keep the UI and prototype responsive, generate detailed prompts combining text + reference context, and support external media/video APIs or downloadable assets cleanly.
* Large uploaded reference photos (`PNG`/`JPG`/`WEBP`) can slow down state or hit storage/payload limits if not resized or handled carefully. Validate file types, show clear previews, and handle large images safely with `try/catch`.
* Browser speech (`Web Speech API`) can sound robotic or stop mid-sentence, and system speech may not record reliably in `MediaRecorder`. Always provide uploaded `MP3`/`WAV` tracks, external realistic voice APIs, and `Web Audio` ambience with clear status states.
