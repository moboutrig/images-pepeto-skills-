# Pepeto PR Images Skills

Image generation project for Pepeto crypto PR — news covers and character sheets using Nano Banana (Gemini CLI).

## Key Files

- `professional-character-sheet.jpg` — Pepeto wizard character reference (MUST be used as base for all image generation)
- `.claude/skills/nano-banana/SKILL.md` — Image generation skill

## Tools & Dependencies

- **Gemini CLI**: `/home/mohammed/.npm-global/bin/gemini`
- **Nanobanana extension**: Installed globally
- **API Key**: Set in extension config

## Image Generation Rules — CRITICAL

- **NEVER use `/generate`** — it cannot reference the character sheet and produces inconsistent characters
- **ALWAYS use `/edit`** with `professional-character-sheet.jpg` as the base image — this ensures the Pepeto wizard looks exactly like the reference
- Always use `gemini --yolo` flag
- Command pattern: `gemini --yolo "/edit /home/mohammed/pepeto-pr-images-skills/professional-character-sheet.jpg 'prompt here'"`
- Output goes to `./nanobanana-output/`
- Present generated images to user after creation
