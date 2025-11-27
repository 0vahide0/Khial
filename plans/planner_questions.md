# Planner interactive questions template

Use this template to collect required inputs from the user before running each step. The Planner agent should ask these in sequence and confirm answers.

1. Project overview
- Project name (default: khial)
- Target number of scenes (default: 10)

2. Scene-level questions (repeat for each scene)
- Scene title / short description
- Story notes / micro-arc details
- Image model choice for this scene (choices: nanobanana)
- Image style preferences (photorealistic, painterly, cinematic, other)
- Do you want multiple image variants? (yes/no)
- TTS model choice for this scene (choices: gemini-tts-pro-2.5, gemini-tts-flash)
- Voice hint (e.g., VOICE: female, warm, calm)

3. Run-level choices
- Default thinking/decision model for Planner and Flow-Refiner (choices: gemini-3, gemini-3-flash, gemini-3-lite)
- Should the Flow-Refiner receive streaming logs in realtime? (yes/no)
- Do you want automatic image rendering if API keys are available? (yes/no)

4. Approval preferences
- Who is the human approver for system-level changes? (username or email)
- Do you allow minor semantic edits for TTS to improve prosody? (yes/no)

Confirm collected answers before proceeding: [Y/n]