---
name: nano-banana
description: "REQUIRED for all Pepeto image generation. Generate crypto PR news covers, character art, and promotional visuals using Nano Banana (Gemini CLI). Use this skill whenever the user asks for a Pepeto image, news cover, PR graphic, crypto article thumbnail, or pastes a crypto news article and wants a cover image. Also use when the user mentions nano-banana, nanobanana, Gemini image generation, or wants to create/edit any visual content for Pepeto."
allowed-tools: Bash(gemini:*), Bash(ls:*), Bash(cat:*)
---

# Nano Banana — Pepeto PR Image Generator

Generate professional PR images for the Pepeto crypto project using Gemini CLI's nanobanana extension.

## The Pepeto Character

Pepeto is the **God of Frogs** — a majestic Pepe wizard. He is the supreme ruler, not a sidekick or mascot. Every detail matters for consistency:

- **Body**: Normal natural proportions matching the reference image. Both hands grip the staff in front of him, powerful upright stance
- **Face**: Classic Pepe the Frog face — wide flat green head, confident/smug expression, big round black eyes with white highlights, wide smirking mouth with red lip line
- **Beard**: Long thick silver-gray wavy beard with defined curly waves and ringlets. Flows from the chin down to mid-chest. Golden-blonde tone (not white, not gray) with darker shading in the wave grooves. Voluminous and majestic
- **Robe**: Dark emerald green wizard robe, floor-length that completely covers the legs and feet — no legs or feet visible at all. Gold/bronze trim along all edges (collar, front opening, sleeve cuffs, bottom hem). Gold belt/sash detail around the waist. The robe pools at the ground, hiding everything below
- **Staff**: Golden staff held upright in front with both hands, topped with a gold spiral/swirl ornament
- **Skin**: Bright green frog skin on face and hands
- **Style**: Bold black outlines, flat cel-shaded coloring, cartoon/meme art style — NOT realistic, NOT 3D rendered

Reference image: `professional-character-sheet.jpg` in the project root.

## Pepeto Brand Identity

| Element | Value |
|---------|-------|
| Primary color | Dark emerald green (#0D5E2B) |
| Accent color | Gold/bronze (#C5941E) |
| Background | Dark/black with green and gold accents |
| Mood | Premium, confident, bullish, crypto-native |
| Style | Bold, modern, editorial — not cheap or meme-y |
| Typography feel | Bold sans-serif headline, clean and readable |

The brand walks the line between meme culture (Pepe origins) and serious crypto project (premium feel). The images should look like they belong on CoinDesk or Decrypt, not a Telegram group.

## Workflow: News Article → Cover Image

When the user pastes a full news article or gives a headline:

1. **Extract the key story** — identify the core news event (price move, listing, partnership, milestone, etc.)
2. **Pick the news type** from the table below to choose the right visual approach
3. **Build the prompt** using the base template + news-type-specific elements
4. **Generate** the image
5. **Show the result** and offer to iterate

## Crypto News Cover — Generation Method

Always use the `/edit` command with the reference image as input. This ensures the Pepeto character stays visually consistent with the original design. Never use `/generate` from text alone for Pepeto images — the character will look wrong.

### Command

```bash
/home/mohammed/.npm-global/bin/gemini --yolo "/edit /home/mohammed/pepeto-pr-images-skills/professional-character-sheet.jpg '{prompt}'"
```

### Prompt Template

Build the edit prompt using this structure:

```text
Transform this character into a professional crypto news editorial cover image, landscape format 1280x720. Keep this exact Pepeto character design — same face, same beard, same robe, same staff, same proportions as the reference. The robe covers the legs completely — no legs or feet visible.

Scene: {scene_description_based_on_news_type}

Place the Pepeto character on one side of the frame (roughly 1/3), with the news visual narrative filling the rest.

Background: Dark premium background with emerald green and gold accent lighting, {news_specific_background_elements}.

Any cryptocurrency coins or logos in the scene MUST match their real-world designs exactly: Bitcoin = orange circle with white ₿ (capital B with two vertical strokes), Ethereum = diamond/octahedron shape, etc. Do not use generic or made-up coin designs.

Leave space at the top or bottom for headline text overlay. Professional editorial illustration, clean layout. No watermarks, no rendered text in the image.
```

## Crypto Coin/Logo Accuracy

When any cryptocurrency coin or logo appears in a scene, the prompt MUST describe the real logo accurately. Never use generic or made-up coin designs.

| Coin | Real Logo Description |
|------|----------------------|
| **Bitcoin (BTC)** | Orange/gold circle with a flat white ₿ symbol — capital B with serifs and two short vertical lines extending above and below |
| **Ethereum (ETH)** | Diamond/octahedron shape in silver-gray/blue, pointed top and bottom |
| **Pepeto (PEPETO)** | Dark teal-green circle with the Pepeto wizard frog character portrait inside (green Pepe frog with beard and golden staff) |
| **BNB** | Yellow/gold diamond shape with the Binance logo |
| **Solana (SOL)** | Purple/gradient circle with tilted S-like logo |

Always include this description in the prompt when coins appear in the scene, e.g.: "floating Bitcoin coins (orange circles with white ₿ symbol)"

## News Type Visual Guides

| News Type | Scene Description | Background Elements |
|-----------|-------------------|---------------------|
| **Price rally / milestone** | Pepeto wizard posing triumphantly beside a massive green candlestick chart breaking upward through a resistance line. Glowing green upward arrows, sparks of energy. | Digital trading dashboard elements, floating price numbers, green particle effects |
| **Exchange listing** | Pepeto wizard stepping onto a grand illuminated trading floor / platform. Spotlight effect, celebratory energy. | Neon exchange-style backdrop, glowing trading terminals, confetti or light burst effects |
| **Partnership / collab** | Pepeto wizard in the center with two glowing orbs or bridges connecting on either side, symbolizing connection. | Network nodes, bridge/connection visual metaphors, dual-color accent lighting |
| **Token / presale launch** | Pepeto wizard casting a spell upward, magical energy emanating from staff tip. Rocket or rising energy behind. | Cosmic/space backdrop, stardust, countdown-style energy, launchpad imagery |
| **Community milestone** | Pepeto wizard addressing a crowd (stylized silhouettes or glowing dots representing holders). Growth chart in background. | Social network nodes, community icons, growth metrics floating in air |
| **Roadmap / development** | Pepeto wizard walking along a glowing path/timeline with checkpoints and milestones ahead. | Futuristic road/path stretching forward, illuminated milestone markers |
| **Market analysis / general** | Pepeto wizard studying a floating holographic chart or crystal ball. Analytical, wise pose. | Data visualizations, floating charts and metrics, digital HUD elements |

## Commands

```bash
# Generate news cover FROM the reference image (preferred — keeps character consistent)
/home/mohammed/.npm-global/bin/gemini --yolo "/edit /home/mohammed/pepeto-pr-images-skills/professional-character-sheet.jpg 'your prompt here'"

# Edit an already-generated cover
/home/mohammed/.npm-global/bin/gemini --yolo "/edit /full/path/to/generated-image.png 'edit instructions'"

# Text-only generation (only when no character needed)
/home/mohammed/.npm-global/bin/gemini --yolo "/generate 'your prompt here' --preview"
```

Always use absolute paths. Always use `--yolo`.

## Output

Generated images save to `./nanobanana-output/` in the current working directory. After generating, always list the output folder and present the image to the user.

## Iteration Tips

When the user wants changes:
- **"More dramatic"** → add more particle effects, stronger lighting, bolder composition
- **"Too busy"** → simplify background, reduce floating elements, more negative space
- **"Character looks wrong"** → re-emphasize: keep exact proportions from reference image, green robe gold trim, silver-gray wavy curly beard, golden spiral staff, both hands on staff
- **"Different angle/mood"** → try a different news type visual approach
- **"Give me options"** → use `--count=3` for variations
