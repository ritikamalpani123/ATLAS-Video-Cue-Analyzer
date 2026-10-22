# ATLAS — Video Cue Analyzer

A drowning-prevention research prototype prepared for the **2026 Congressional App Challenge**.

## Why I built ATLAS

As a high school student, lifeguard, and drowning-prevention researcher, I want to explore how technology can help organize observations of swimmer behavior for human review. Subtle physical cues can be difficult to describe consistently. ATLAS turns video-model responses into a readable list of observations that can support research and discussion.

ATLAS is **not a validated drowning-detection or emergency-response system**. It must never replace active supervision, trained lifeguards, rescue procedures, or emergency services. No accuracy, sensitivity, response-time, or validation claims are made.

## What it does

- Accepts multiple video uploads, with a removable queue and sequential analysis.
- Preserves native video input and local contact-sheet frame extraction (1–36 labeled frames).
- Offers model selection, custom model slugs, editable prompts, and request spacing.
- Defaults to `nvidia/nemotron-nano-12b-v2-vl:free`.
- Shows structured cue lists and per-video errors, with individual deletion and clearing.
- Exports results to CSV and Word-compatible HTML `.doc` files (not `.docx`).
- Includes an account-free, prewritten sample workflow with persistent illustrative labels in the interface and exports.

## Try the sample demo

Open the website and click **Try Sample Demo**. No API key or OpenRouter account is required. Review the fictional clip information and example physical cues, then export Word or CSV results. All sample outputs are **illustrative demonstrations, not actual AI-generated results**. No real video is provided or analyzed by this button.

## Use live analysis

1. Enter your own OpenRouter API key in the password field. It is optional for the demo and is not saved by the application.
2. Choose a model compatible with your selected input mode. The default model is retained from the original project; availability and capabilities can change.
3. Select native video to send the clip, or contact-sheet mode to extract frames locally and send one labeled JPEG image.
4. Add one or more video files, review the prompt, and click **Run analysis**.
5. Review every output critically before exporting it. Failures are reported on the relevant result card.

Only use footage you are authorized to share. Live requests send the prompt and video or contact sheet directly from your browser to OpenRouter and its selected provider. Their data policies apply. API keys are transmitted only in the Authorization header to OpenRouter; there is no project backend, analytics, key storage, or shared key. Never add keys to source code, commits, URLs, or GitHub Pages settings.

Model/provider pricing, account-balance rules, input support, and rate limits can change. A `:free` slug does not guarantee service availability. See [OpenRouter video input documentation](https://openrouter.ai/docs/guides/overview/multimodal/videos) and the [default model listing](https://openrouter.ai/nvidia/nemotron-nano-12b-v2-vl:free).

## Technologies and local use

The original application is preserved as a single static `index.html`, using HTML, CSS, vanilla JavaScript, browser FileReader, video/canvas APIs, Fetch, and Blob downloads. There are no build steps or third-party scripts.

Open `index.html` directly, or serve this folder locally, for example with `python3 -m http.server 8000`. GitHub Pages serves the same static file over HTTPS.

## Limitations and future improvements

- Models can hallucinate, miss distress, misinterpret normal swimming, or provide inconsistent observations. Visible cues alone cannot confirm drowning or medical status.
- Sparse contact sheets lose motion between frames. Codec support and memory limits vary across browsers, especially on mobile. H.264 MP4 is a practical compatibility option.
- Remote requests depend on network connectivity, provider support, quotas, and browser cross-origin access. Requests time out after two minutes.
- The sample demonstrates interface behavior; it provides no validation evidence.
- Future work could include consented, appropriately labeled evaluation data, independent expert review, systematic error analysis, accessible video annotation, and stronger privacy controls. These are proposed improvements, not completed research findings.

## Congressional App Challenge 2026

This version is prepared for a 2026 submission. Judges can start with **Try Sample Demo** immediately and inspect the source here. The creator should verify district-specific eligibility and deadlines, supply their name and district in the submission form, and include the required demonstration video. Publishing this site does not submit an entry to the competition.

## GitHub Pages deployment

Publish this repository as `ATLAS-Video-Cue-Analyzer`. In **Settings → Pages**, choose **Deploy from a branch**, **main**, and **/(root)**, then save. No secrets or environment variables are required.
