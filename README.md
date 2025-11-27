# khial — Agentic Flow (Gemini + nanobanana)

Overview
- This repository contains a text-first, git-like agentic workflow for producing 10 scenes (image prompts + TTS dialogs) with model-specific optimization and QA. The system supports Gemini models for thinking and TTS and "nanobanana" as the image model.

Quick start
1. Planner: run the Planner Agent (run locally or via UI). The Planner will ask interactive questions to gather project inputs and which models to use at each step.
2. Creator: Story Writer + Creator agents produce scenes/scene01..scene10.md.
3. For each scene, choose per-step models when prompted (images: nanobanana; thinking/flow decisions: Gemini-3; fast tasks: Gemini-3-Lite/Flash; TTS: Gemini-TTS-Pro-2.5 or Gemini-TTS-Flash).
4. Artifacts are streamed in real-time to the Flow-Refiner for suggestions before finalizing each step.
5. QA approves artifacts; Release Agent compiles reports and asks the human to approve any system changes.

File layout
- agent.md — agent roles & instructions
- README.md — this file
- config/models.md — canonical model names & options
- plans/planner_questions.md — interactive questions template the Planner uses to collect user inputs
- system_prompts/ — system prompts used by optimizer agents
- tts-models/ — model docs for TTS models
- image-models/ — model docs for image model(s)
- scenes/scene01..scene10.md — canonical scene files
- reports/ — optimization, QA, and final reports

How to choose models during the run
- The Planner will ask which model to use for each step (thinking, image optimization, TTS optimization, quick tasks).
- Defaults are provided but the user can change selections per step.

Privacy & safety
- The flow enforces content safety checks; any flagged item requires human review.

License
- MIT by default. See LICENSE file.