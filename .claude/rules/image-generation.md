# Image Generation Rules

## CRITICAL: Use /edit ONLY — Never /generate

- **NEVER use `/generate`** — it does not accept a reference image and will produce an inconsistent Pepeto character
- **ALWAYS use `/edit`** with the character sheet as the base image so the character is correct from the first shot
- Always use nano-banana skill for any image generation request
- Use `--yolo` flag on all gemini commands

## Command Template

```bash
/home/mohammed/.npm-global/bin/gemini --yolo "/edit /home/mohammed/pepeto-pr-images-skills/professional-character-sheet.jpg 'Transform this character sheet into a [NEWS TYPE] crypto news cover. Landscape 1280x720, dark premium background. Keep the Pepeto wizard character exactly as shown — green frog, white beard, dark green hooded robe with gold trim, golden spiral staff, cel-shaded with bold outlines. [SCENE DESCRIPTION]. Headline: [HEADLINE]. Bottom banner: PEPETO NEWS. Brand colors: emerald green #0D5E2B and gold #C5941E.' --preview"
```

## Workflow

1. When user pastes a news article, extract the headline and determine the news type
2. Build the `/edit` command using the template above with the reference image path
3. Use absolute file path: `/home/mohammed/pepeto-pr-images-skills/professional-character-sheet.jpg`
4. After generating, present the image to the user

## News Cover Specs

- Dimensions: landscape 1280x720
- Background: dark premium with subtle geometric patterns
- Brand colors: emerald green (#0D5E2B) + gold (#C5941E)
- Character: must match reference exactly — normal proportions, dark green robe with gold trim, white beard, golden spiral staff, cartoon cel-shaded style with bold outlines
- Always include headline text and PEPETO NEWS banner
