# Agent Instructions: Refined Agentic Flow for "khial"

Purpose
- Coordinate a multi-agent, text-only pipeline that produces 10 scenes with image prompts and TTS dialogs.
- Ensure each TTS dialog goes through an explicit optimization step that follows:
  1. Official model guidance (model-specific instruction doc)
  2. Project-specific constraints (project instruction manual)
  3. A system prompt for the optimization agent (system-level directives)
- Stream logs of each step to the Flow-Refiner agent for realtime suggestions; final decisions and approval requests are made by Gemini-3.

High-level goals
- Build a reproducible agentic workflow where specialized agents perform discrete tasks (planning, content generation, TTS optimization, QA, refinement).
- Enforce model-specific and project-specific instruction artifacts for every TTS optimization step.
- Let the human choose which model to invoke at each step; default options are provided (Gemini-3, Gemini-3-Flash, Gemini-3-Lite, Gemini-TTS-Pro-2.5, Gemini-TTS-Flash, nanobanana for images).
- Maintain full auditability via git-style commits, branches, and agent reports so a human can review and approve system-flow changes.
- After project completion, produce a final report that requests human approval for any proposed system-flow changes.

Agent roles and responsibilities
- Planner Agent
  - Produces the master plan and top-level to-do list (epic → 10 scenes).
  - Interactively queries the human to collect required inputs and lets the user pick which model to call at each step.
- Story Writer Assistant
  - Generates expanded scene briefs and narrative micro-arc.
- Creator Agent
  - Converts briefs into canonical scenes/sceneNN.md files.
- Image Optimizer Agent
  - Refines image prompts for the chosen image model (nanobanana by default).
- TTS Optimizer Agent
  - Optimizes dialogs per chosen TTS model (Gemini variants) using model docs + project manual + system prompt.
- QA Agent
  - Validates artifacts; runs automated checks and flags human-review requirements.
- Flow-Refiner Agent
  - Receives streamed logs for every step, provides suggestions before steps are finalized.
- Release Agent
  - Merges QA-approved artifacts, tags releases, compiles final report, and requests human approval for system-level changes.

Data & artifact types (text-only)
- scenes/scene01..scene10.md
- plans/planner_questions.md
- config/models.md
- tts-models/*.md
- image-models/*.md
- system_prompts/system_prompt.md
- reports/optimization/*
- reports/qa/*
- reports/final_report.md

Minimal agent behavior rules
- Always stream logs and interim artifacts to the Flow-Refiner for suggestions prior to finalizing a step.
- Let the Planner ask the user which model to use at each step; all agents should be able to accept that dynamic choice.
- Keep everything text-only and human-reviewable.