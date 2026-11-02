# VideoExpress Long-Form Multi-Character Story Agent

A rewritten **GitHub-ready playbook and prompt kit** for producing narrative videos in VideoExpress.ai through an **authorized, visible browser/computer-use agent**. It expands the [original two-character 10/30-second playbook](https://github.com/ai-playbooks/videoexpress-two-character-agent) into a storyboarded, multi-character **5–20-minute** storytelling workflow.

> **Important:** This is a production specification, prompt library, and offline planning/validation toolkit—not an unofficial VideoExpress API client or a claim that the editor has been automated. A capable, authorized browser/computer-use agent and a signed-in VideoExpress account are needed for on-site execution. Individual app controls and limits must be verified in the live UI. This package has not been tested end-to-end against the signed-in VideoExpress editor.

## Get VideoExpress (affiliate link)

**New to VideoExpress?** [Access VideoExpress using the repository maintainer's referral link](https://videoexpress.alphatoolkits.com/) before using this workflow. Already have a VideoExpress account? You can use your existing account.

> **Affiliate disclosure:** This is the repository maintainer's affiliate link. If you make an eligible purchase or subscription through it, the maintainer may receive a commission. Tracking, eligibility and payment are controlled by the VideoExpress affiliate program; a commission is not guaranteed. This repository is an independent community workflow, not an official VideoExpress product. You are not required to use the referral link to use these prompts.

## NEW: Viral-pattern scriptwriting workflow (script first)

This edition integrates **two narrative mechanisms** extracted from the user's two sample-video analyses, while keeping every generated story original:

1. **Injustice → transformation** (`INJUSTICE_TO_TRANSFORMATION`): opening loss/rejection, physical consequences, discovery of an undervalued asset, a vow, stepwise *visible* progress, first finished micro-win, a functional midpoint that proves a system works, then comfort/use, dignity reversal and proof that the result lasts.
2. **Sacrifice → justice** (`SACRIFICE_TO_JUSTICE`): personal bond, concrete sacrifice, escalating believable consequences, a help/hope beat and setback, a seeded deadline or irreversible choice, earned revelation/intervention, proportionate accountability and protagonist-centered healing.
3. **Hybrid redemption** (`HYBRID_REDEMPTION`): only when a real transformation and a sacrifice arc support a single protagonist objective.

The agent first writes an **original full timed script**, not merely a high-level prompt: 0–10 second hook, first-minute story promise, open-loop/payoff tracking, fully staged scenes with named speakers and exact dialogue/narration, sensory sound cues, a purposeful midpoint, scene transitions and a meaningful final image. **No asset generation occurs until the script passes a retention/story QA gate.** The original video examples are not copied, and these structures are **not a guarantee of views, revenue, recommendations or virality**.

For pacing, aim for distinct **micro-wins every ~45–90 seconds** in a transformation story, and new consequences/revelations/decisions every **~60–120 seconds** in a family drama, adapting to actual story needs. The main title/thumbnail promise must be paid off **on screen**, with adequate final minutes/seconds for durable human aftermath. The 27-minute source example is **compressed and reimagined** within the project's 20-minute cap, never reproduced beat by beat.

Key documents: `VIRAL_STORY_ENGINE.md` (full screenplay rules), `templates/SCRIPT_BEAT_SHEET.md` (production-script format), `templates/VIRAL_SCRIPT_QA.md` (human creative-quality acceptance check), `examples/viral-pattern-story-maps.md` (two original illustrative maps). Offline tooling creates timed **outline skeletons**, not magically completed scripts.

## Defaults and requirements

| Setting | Behavior |
| --- | --- |
| Final video runtime | **5–20 minutes** inclusive; default **5:00** |
| Aspect ratio | **16:9 landscape** by default; use other ratios only if requested and visibly supported |
| Image/animation style | **3D adult-proportioned cinematic animation (Pixar-like)** default, or **ultra-hyperrealistic fictional AI humans** |
| Characters | A **recurring multi-character cast**, typically 3–5 named people, created by AI or derived from authorized user references |
| Consistency | Character bible, fixed reference images/tags, set bible and shot-by-shot continuity |
| Clip generation | First write a full timed original screenplay; then convert into short UI-supported animated clips (e.g., 10 seconds) and edit into 5–20 minutes |
| Mandatory user input | Story/premise/script **and exact media folder name**; engine optional, chosen to fit the plot |
| Mandatory assembly path | **Media Library → My Media → [user's exact folder]**; verify the path before assembling in a separate clean editor project |
| Export | Saved project and verified MP4, preferably **1080p High** when available |

### How many clips?

When VideoExpress supports 10-second source clips, a 5-minute story needs roughly **30 clips**, a 10-minute story **60**, and a 20-minute story **120**, **before adjusting for trims or overlaps**. These counts are planning estimates—not a guarantee of finished length or available account credits.

### Critical limitation: two reference photos vs multiple story characters

The source playbook documents **two consistent-character reference slots per generated clip**. This rewrite achieves a **larger recurring cast across the video** by creating separate reference assets and selecting the appropriate character pair for each solo/two-character shot. Three or more recognizable characters *simultaneously in one shot* are **not guaranteed** by two reference slots; the system uses editing, reverse shots and reaction shots, or a verified group-reference feature if genuinely available.

### Folder requirement explained

The user specifies a folder **name**, for example `MIDNIGHT TRAIN - EP01`. The agent must open and verify `Media Library → My Media → MIDNIGHT TRAIN - EP01`. If the UI supports organizing/moving newly generated images and video clips into this folder, the agent must do so and verify the result. **The actual video is assembled on a clean timeline project in the editor**. The prompt prevents an agent from confusing an asset folder with the editing timeline or falsely claiming a folder save that wasn't possible.

## Included files

```text
videoexpress-longform-story-agent/
├── README.md
├── CHANGELOG.md
├── PUBLISHING.md                 # GitHub upload instructions
├── SYSTEM_PROMPT.md               # Complete production instruction
├── SYSTEM_PROMPT_COMPACT.md       # Short instructions + link to full file
├── SYSTEM_PROMPT_ALL_IN_ONE.md    # NEW: combined core + script engine in one file
├── VIRAL_STORY_ENGINE.md          # NEW: mandatory script-first viral-pattern architecture
├── templates/
│   ├── INTAKE.md                  # One-message production intake
│   ├── SCRIPT_BEAT_SHEET.md       # NEW: timed screenplay and dialogue template
│   ├── VIRAL_SCRIPT_QA.md         # NEW: story-quality acceptance gate
│   ├── STORY_BIBLE.md             # Identity, set and continuity registry
│   ├── QA_CHECKLIST.md            # Pre-export verification
│   └── project_spec.example.json  # Sample machine-readable project
├── examples/
│   ├── viral-pattern-story-maps.md # NEW: original 5/10-minute engine examples
│   ├── first-minute-screenplay-sample.md # NEW: formatted 60s script excerpt
│   ├── five_minute_transformation_script_blueprint.json
│   ├── ten_minute_justice_script_blueprint.json
│   ├── eight-minute-story.md      # Example 8-minute beat plan
│   └── eight_minute_plan.json     # 48-scene blank manifest for 8 minutes
├── tools/
│   ├── plan_script.py             # NEW: timed emotional beat outline planner
│   ├── validate_script.py         # NEW: beat-sheet structural validation
│   ├── plan_project.py            # Offline scene-manifest skeleton generator
│   └── validate_plan.py           # Offline duration/cast/folder verifier
├── tests/
│   ├── test_workflow.py           # Existing manifest sanity tests
│   └── test_script_blueprints.py  # NEW: script-architecture sanity tests
└── .github/workflows/
    └── validate.yml               # Offline CI checks
```

## Install the prompts

If you don't yet have VideoExpress access, use the [optional affiliate signup link](https://videoexpress.alphatoolkits.com/) (the maintainer may receive a commission on eligible purchases/subscriptions). If you already have an account, proceed with it.

**Custom GPT / agent:** paste `SYSTEM_PROMPT_COMPACT.md` into your custom instructions and attach **both** `SYSTEM_PROMPT.md` **and** `VIRAL_STORY_ENGINE.md` (plus templates if supported) as knowledge references. Enable a browser/computer-use capability if your environment actually offers one. **ChatGPT Work** may be an alternative if you have access to its browser/computer workflow; this package does not itself provide browser tools.

**Prefer one copy-paste file?** Use `SYSTEM_PROMPT_ALL_IN_ONE.md`, which embeds both the full production prompt and complete viral story-engine specification.

**Other browser-capable agents:** use the full `SYSTEM_PROMPT.md` together with `VIRAL_STORY_ENGINE.md` as agent/project system instructions, and give it access only to the signed-in VideoExpress UI you intend to use. Avoid granting account-management or payment powers unnecessarily.

At the start of an individual video request, provide the story and folder name. Style/length/ratio can be omitted to accept defaults.

## Example script-first story invocation

> Make a 10-minute **sacrifice-to-justice** story for a fictional family about a daughter returning to her mother's small shop and finding the sacrifice that saved her college fees. Produce an **original timed scene-by-scene script** with a 10-second emotional hook, a clearly planted question, meaningful escalations, hope and setback, an earned final revelation, accountable aftermath, and a filmable lasting proof. Use original 3D adult-style characters in 16:9, keep continuity, and assemble all clips into a new VideoExpress project using **Media Library → My Media → FAMILY REDISCOVERY EP01**. Do not generate any imagery until the complete screenplay and script QA are done; do not buy credits or publish.

## Example invocation

> Create an 8-minute narrative called **The Last Letter** about three adults who discover a hidden message in an old railway station. Make the cast as original 3D adult animated characters, 16:9. Use the VideoExpress My Media folder **THE LAST LETTER - EP01**. Generate consistent character references, storyboard the film, animate the scenes, assemble them in a clean project, Auto Align where available, save and export MP4 1080p. Keep the dialogue natural, and do not buy upgrades or publish anything.

Or ask for photorealism:

> Create a 12-minute hyperrealistic human AI story from my script. Folder: `FAMILY STORIES 02`. Use original fictional adult faces, 16:9, recurring cast, natural voice continuity, and verified final export.

## Local planner (optional; standard Python only)

The utilities generate/validate **metadata**, not images, videos or VideoExpress UI actions. Python 3.10+ recommended:

```bash
python tools/plan_script.py --title "The Last Letter" --minutes 8 --engine SACRIFICE_TO_JUSTICE --output script_blueprint.json
python tools/validate_script.py script_blueprint.json
python tools/plan_project.py --title "The Last Letter" --folder "THE LAST LETTER - EP01" --minutes 8 --style 3D_ADULT_ANIMATION --engine SACRIFICE_TO_JUSTICE --output scene_plan.json
python tools/validate_plan.py scene_plan.json
python -m unittest discover -s tests -v
```

The planners fill timed **beat-outline skeletons** and *skeletal 10-second shot slots*; you must write the full screenplay with real dialogue and visual actions before generating videos. The creative agent must still write each beat, choose a registered cast/set for it, generate content and update actual durations and asset IDs before final QA. The linter checks structural metadata only, **not** artistic quality or a finished exported file.

## Differences from the original

- Replaces two supplied images with a **created/referenced recurring cast**.
- Replaces 10/30-second outputs with **5–20-minute** narrative video duration planning.
- Replaces 9:16 by default with **16:9**.
- Fixes a deliberate two-style workflow: **adult 3D animation or hyperrealistic humans**.
- Adds **mandatory user-named `My Media` folder** and verifies path vs timeline project.
- Adds story bible, acts/chapters, 30–120-shot production manifest, stable character/voice profiles, asset ID tracking, queue/credit safeguards and export runtime verification.
- Adds **two viral-inspired screenplay engines and a hybrid**, a mandatory full timed-script stage, retention/continuity and title-promise audit, a compact prompt, reusable templates, original story maps, and offline planning QA scripts.

## Original provenance and publishing

Inspired by and substantially rewritten from the original [ai-playbooks/videoexpress-two-character-agent](https://github.com/ai-playbooks/videoexpress-two-character-agent) and an original system prompt supplied by the user. The source repository did not expose a license file in the inspected root; **verify reuse and licensing terms before republishing inherited material**. This package does not grant rights in VideoExpress, Pixar, or third-party assets. Animation visuals should be original; licensed/authorized voices, music and likenesses only.

To publish this package as your repository: create an empty GitHub repo and upload these files, or commit/push via your own authorized Git workflow. **No changes have been made to the original GitHub repository by generating this download.**