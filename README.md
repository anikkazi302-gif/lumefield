# Free AI Video Studio

> **Try it live: https://anikkazi302-gif.github.io/free-ai-video-studio/**

Turn reference photos into a 30-second, high-quality video — free.

## What it is

A single-page web tool that plans your video and writes the exact prompts, then sends you
to a genuinely free engine where the video is rendered for free. Open `index.html` in any
browser — no install, no account, no payment.

## Honest note — read first

This page does **not** render video itself. No web page can render a 30-second AI video
for free in your browser. What this tool does:

1. You upload 1–2 reference photos (they stay in your browser — nothing is uploaded).
2. You describe the scene: subject, action, camera move, style.
3. You pick a duration (5 / 10 / 20 / 30 seconds) and a verified free engine.
4. The tool builds a complete video plan: one prompt per segment, locked camera and
   face rules, recommended settings, and a direct link to the engine.

Most free engines make **5–10 seconds per clip**. A 30-second video is made by
**chaining segments**: generate segment 1, use its last frame as the start image for
segment 2, and so on. This tool builds that chain for you.

## How to make the full 30 seconds

1. Open the engine (free, no payment). Upload your reference photo as the start frame.
2. Paste the **Segment 1** prompt and generate. Download the clip.
3. For Segment 2, use the **last frame of Segment 1** as the start image and paste the
   Segment 2 prompt. Repeat for Segment 3.
4. Join the clips in any free editor (CapCut, DaVinci Resolve, or ffmpeg).
5. If a segment comes out wrong, regenerate only that segment — never the whole video.

Tip: keep every segment prompt's subject, face, clothes and setting identical.
Changing one word of the subject between segments is the most common cause of a face
or scene changing mid-video.

## Verified free engines (10 November 2026)

Every engine below was verified free on 10 November 2026. Free tiers change — always
re-check the engine's own page before planning a production around a limit.

| Engine | Image-to-video | Max per clip | Resolution | Audio | Free terms | Link |
|---|---|---|---|---|---|---|
| Wan 2.2 I2V (Alibaba) | Yes | 8s | 720p | No | Free Hugging Face Space, shared GPU queue | https://huggingface.co/spaces/Saravutw/WAN2.2_I2V_LIGHTNING_4-8step_custom |
| LTX-2.3 (Lightricks) | Yes | 10s | up to 1080p | Yes | Free official Hugging Face Space | https://huggingface.co/spaces/Lightricks/LTX-2-3 |
| HunyuanVideo 1.5 (Tencent) | Yes | 10s | 480p / 720p | No | Free Hugging Face Space | https://huggingface.co/spaces/multimodalart/Hunyuan-Video-1-5 |
| CogVideoX 1.5 (Zhipu AI) | Yes | 10s | up to 1360×768 | No | Free official Hugging Face Space | https://huggingface.co/spaces/zai-org/CogVideoX-5B-Space |
| Kling AI | Yes | 10s | 720p / 1080p | No | 66 free credits every day | https://klingai.com |
| Google Flow (Veo 3.1) | Yes | 8s | 720p / 1080p | Yes | 50 free credits every day | https://labs.google/fx/tools/flow |
| Runway Gen-4 Turbo | Yes | 5s | 720p | No | 125 credits once, never refills; watermarked | https://runwayml.com |
| Mochi 1 (Genmo) | **No — text only** | 5s | 480p | No | Free playground, 250 lifetime credits | https://genmo.ai/play |

Notes on the limits:

- **Wan 2.2 I2V** — the open-source model supports up to 8 seconds per clip on hosted
  Spaces (2 / 3.5 / 5 / 8 second settings). Self-hosted it can run longer with a strong GPU.
- **LTX-2.3** — the model itself supports up to 20 seconds per clip, but the free
  Hugging Face Space caps the duration slider at 10 seconds. It is the only free engine
  in this list with synced audio.
- **HunyuanVideo 1.5** — durations are 5, 8 or 10 seconds. Clips are silent. The 1.0
  version's standard output was ~5 seconds; 1.5 raised it to 10 seconds.
- **CogVideoX 1.5** — 5–10 second clips. The image-to-video variant (5B-I2V) accepts
  any aspect ratio.
- **Kling** — free credits expire in 24 hours; about 6 standard 10-second clips a day.
- **Google Flow / Veo 3.1** — Veo 3.1 makes 4, 6 or 8-second clips. Free tier is about
  2 Fast or 5 Lite clips a day.
- **Runway** — the 125 free credits never refill, and free-tier clips are 5 seconds
  and watermarked. Good for one test, not for daily work.
- **Mochi 1** — text-to-video only. It takes no reference photo, so it is listed here
  only to explain why it is not for reference-photo work.

## What each segment prompt contains

- The subject and the action beat for that segment (beginning / middle / peak / end).
- The camera move and the visual style.
- The setting, when given.
- A continuity line: segment 2+ continues from the last frame of the previous segment
  with the same character, face, clothes and setting.
- The locked rules block (pasted with every prompt):
  - **Camera rule** — the camera does whatever it needs to show the characters well;
    the characters never look at the camera or act for it.
  - **Face lock** — faces must match the reference photos exactly, no face changes,
    no character changes, no clothing changes between segments. 16:9 widescreen.
    No blood ever.

## Files

- `index.html` — the whole tool (HTML + CSS + JavaScript, no build step, no external
  dependencies except the engine links).
- `README.md` — this file.
- `LICENSE` — MIT License.

## How to run it

Open `index.html` in a browser. That is all. It works offline except for the links
out to the engines.

## How to contribute

Fork the repo, change one thing, open a pull request. Good first contributions:

- A new verified free engine (with its official link, its honest per-clip limit, and
  the date you verified it).
- A better segment planner (for example, per-segment action fields).
- Translations of the interface.

Do not add an engine you have not verified as free, and never add a fake limit.
Every engine in the list must link to its real official page or Space.

## License

MIT — see `LICENSE`. Free to use, share and remix.
