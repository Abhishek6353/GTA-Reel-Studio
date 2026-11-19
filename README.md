# GTA Reel Studio 🎮

An AI-powered GTA V gameplay editor for Google Antigravity. Turn long gameplay recordings into engaging, ready-to-review Instagram Reels, YouTube Shorts and TikTok videos using a reusable agent skill and local video-processing tools.

## Features

- Analyze the full recording for funny moments, rage, excitement, close calls, stunts and mission highlights.
- Combine commentary, speech timestamps, audio energy and visual evidence to rank highlights.
- Automatically select and edit the best 30–60 second clips.
- Reframe gameplay intelligently into 9:16, including facecam layouts when available.
- Add short hooks, synchronized subtitles, covers, captions and hashtags.
- Render and verify 1080 × 1920 MP4 videos using FFmpeg.
- Set up missing free dependencies, reuse previous analysis and preserve original recordings.

## Getting started

### 1. Clone the repository

```bash
git clone https://github.com/Abhishek6353/GTA-Reel-Studio.git
cd GTA-Reel-Studio
mkdir input
```

The repository is private, so authenticate with a GitHub account that has access.

### 2. Add your gameplay

Place your own gameplay recordings inside `input/`. Common supported formats include MP4, MOV, MKV and WEBM.

### 3. Open in Antigravity

Open the `GTA-Reel-Studio` folder as a workspace in Google Antigravity. The skill is located at `.agents/skills/gta-reel-editor/SKILL.md`.

Paste the following prompt into the agent:

> Use the gta-reel-editor skill. Automatically set up missing dependencies, analyze the gameplay videos in input/, and generate up to 5 high-quality, distinct 30–60 second vertical reels. Use quality mode, preserve my original commentary, add accurate subtitles and verify the final exports. Execute the complete workflow, not just a plan.

Approve any required installation or terminal permissions when prompted. External API uploads and paid services are not required by default.

### 4. Review the results

Find the generated videos and supporting files inside `output/`. Review each reel before publishing.

## Example prompts

| Mode | Prompt |
| --- | --- |
| Standard | Use gta-reel-editor. Process the new gameplay video in input/. |
| Quality | Use gta-reel-editor in quality mode. Create the best 5 reels with polished captions and intelligent cropping. |
| Fast | Use gta-reel-editor in fast mode. Generate up to 3 reels. |
| Analysis only | Use gta-reel-editor. Identify and rank highlights without rendering videos. |
| Hindi/Hinglish | Generate the best 3 reels, preserving my Hindi/Hinglish commentary and using Roman Hindi captions. |

## Project structure

```text
GTA-Reel-Studio/
├── .agents/skills/gta-reel-editor/
│   └── SKILL.md            # Reusable agent instructions (tracked)
├── .gitignore              # Repository exclusions (tracked)
├── README.md               # Documentation (tracked)
├── input/                  # Source gameplay (local only)
├── output/                 # Finished reels and metadata (local only)
├── work/                   # Analysis and temporary files (local only)
├── scripts/                # Generated processing scripts (local only)
└── .venv/                  # Python environment, if needed (local only)
```

Antigravity creates the processing folders and scripts as needed. The repository intentionally tracks only the skill and documentation, not videos, models, environments, generated scripts or credentials.

## Processing tools

| Tool | Purpose |
| --- | --- |
| Google Antigravity | Workflow execution and AI analysis |
| FFmpeg / FFprobe | Video editing, rendering and verification |
| Faster Whisper or compatible local ASR | Timestamped speech transcription |
| Python / OpenCV | Automation and visual frame analysis as needed |

The skill detects missing dependencies and attempts to configure free local tools. Availability, installation steps and processing speed depend on your operating system, hardware and permissions. Visual analysis capability depends on the selected model and tools.

## Output

Each source recording gets its own output directory with ranked MP4 reels, JPEG covers, subtitles when speech is present, posting captions and hashtags, and an analysis report with timestamps, scores and quality checks.

Default reel format: **1080 × 1920 · 9:16 · 30–60 seconds · H.264 MP4 · AAC audio**.

## Tips for better reels

- Use original high-resolution gameplay recordings.
- Record microphone and game audio on separate tracks whenever possible.
- Disable in-game radio to reduce music copyright concerns.
- Prefer a few genuinely strong highlights over many average clips.
- Review the final reels, captions, rights flags and suggested hashtags before posting.

## Updates on another PC

If the repository is already cloned, open its directory and run:

```bash
git pull
```

Then add new gameplay to `input/` and run the skill again. To verify what Git tracks, use `git ls-files`.

## Notes

This project is a local-first, agent-driven editing workflow, not a guaranteed viral-video predictor or an automatic Instagram publisher. Use footage you own or are authorized to edit and publish. Always review generated content before uploading.
