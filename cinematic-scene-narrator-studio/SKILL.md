---
name: cinematic-scene-narrator-studio
description: Build and refine an interactive web studio that turns stories, real-life incidents, or ideas into keyword-matched scenes with expressive narrator voices, mood atmospheres, and video or script export. Use when building or debugging a story-to-scene studio, 3D or stylized animation scene generator, multilingual narrator voice pipeline, or scene/video exporter.
---

# Cinematic Scene Narrator Studio

## Summary

Guide the generation and refinement of an interactive web studio that converts stories, incidents, or ideas into sequenced visual scenes paired with a mood-aware narrator voice, background atmosphere, and video or script export. Keep browser prototypes resilient and realistic about browser 3D and speech engine limits while supporting external AI media or voice APIs for production quality.

## When to Use

Use this skill in these situations:

* Building or iterating on a story-to-scene or moment-to-scene web application.
* Mapping story keywords and moods (such as car, driving, rain, night, house, door, sad, tense, scary, or dramatic) to matching visual elements and lighting.
* Configuring multilingual narration (English, French, and other languages), pacing, mood adjustments, external realistic TTS APIs, or uploaded audio tracks.
* Debugging WebGL/Three.js rendering, `MediaRecorder` scene/video export, or browser speech/audio errors.

## Steps

1. **Scope Visual Style and Realism Honestly**: Set clear expectations between browser-rendered 3D or stylized scenes (Three.js or Canvas) and high-detail animation styles (such as warm Pixar or Disney inspired character and environment design). Use browser 3D for fast interactive prototypes, and output structured prompts or external media hooks when full cinematic character or environment detail is needed.
2. **Map Story Elements and Mood to the Scene**: Parse story text into clear scenes and extract visual cues (vehicles, weather, time of day, locations, characters) along with emotional mood (`tense`, `scary`, `sad`, `dramatic`). Adjust lighting, color tone, camera motion, and subtle ambient audio to match each scene.
3. **Configure Multilingual Voice and Pacing**: Support target narration languages (especially English and French, plus other available voices) with safe voice loading (`onvoiceschanged`), short sentence pauses, and moderate pitch/rate tuning so speech avoids robotic distortion. Include an optional realistic voice API key field (such as ElevenLabs) and an audio file upload option (`MP3` or `WAV`) for human-like delivery.
4. **Build Reliable Video and Script Export**: Configure WebGL canvases with `preserveDrawingBuffer: true` when recording via `canvas.captureStream` and `MediaRecorder`, auto-detect a supported `mimeType`, mix `AudioContext` output when available, and provide script (`txt`) export plus clear status indicators and `try/catch` error handling.
5. **Test and Iterate with Concrete Stories**: Validate changes using multi-scene stories (such as driving in rain, night tension, or a quiet emotional return) and fix the exact broken component first before adding extra features.

## Gotchas

* Browser built-in speech engines (`Web Speech API`) often sound robotic or choppy in Arabic and other languages, and `MediaRecorder` may not capture system speech audio directly in every browser. Clearly separate prototype browser speech from external realistic TTS or uploaded voice tracks.
* Complex Pixar-like characters, hair, and lighting cannot be fully rendered from scratch in a lightweight browser script. Keep browser 3D clean and stable, and generate rich visual prompts or external AI assets when high visual fidelity is the goal.
* Missing external API keys or blocked third-party asset URLs easily break prototypes. Keep local fallback logic and `try/catch` guards active so the studio stays usable on first load.
