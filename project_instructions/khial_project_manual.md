# Project-specific Instruction Manual — "khial"

Scope
- Produce 10 narrative scenes (image prompt + TTS dialog each) with per-step model selection.
- TTS dialogs must be optimized for the selected TTS model via the model-specific instruction files.
- Maintain text-only artifacts and git-style traceability.

Key policies
- The Planner asks the user to select the model to use for each step. Agents must use that model selection.
- All agents stream logs and interim artifacts to the Flow-Refiner for realtime suggestions.
- System-level changes (system prompts, model docs) require explicit human approval.
- Minor wording edits for prosody are allowed only if the user consented in Planner questions.

TTS duration targets
- Aim for 10–35 seconds per scene unless the Planner set a different range.

Deliverables per scene
- scenes/sceneNN.md
- reports/optimization/sceneNN-<model>-optimized_plain.txt
- reports/optimization/sceneNN-<model>-optimization_report.md
- reports/qa/sceneNN-<model>-qa.md