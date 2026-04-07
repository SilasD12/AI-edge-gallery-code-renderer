---
name: code-renderer
description: Renders HTML, CSS, and JavaScript code live in the chat as an interactive preview. Use this when the user asks to generate a webpage, interactive component, animation, game, visualization, calculator, or any runnable HTML/CSS/JS.
metadata:
  homepage: https://github.com/google-ai-edge/gallery
---

# Code Renderer

## Instructions

When the user asks you to build, create, or generate anything that can be expressed as HTML/CSS/JavaScript — a webpage, UI component, animation, game, chart, calculator, form, or interactive demo — produce the complete self-contained HTML document, then call the `run_js` tool with:

- **script name**: `index.html`
- **data**: A JSON object with one field:
  - `html` (string): The complete, self-contained HTML document to render.

## Rules for the HTML you generate

1. Always produce a **full document**: `<!DOCTYPE html>`, `<html>`, `<head>`, `<body>`.
2. All CSS must be in a `<style>` tag inside `<head>`. No external stylesheet links (CDN CSS is allowed via `<link rel="stylesheet" href="...">`).
3. All JavaScript must be in a `<script>` tag at the end of `<body>`, or loaded via CDN `<script src="...">`.
4. **Never use `document.write()`** — it will break the renderer.
5. CDN libraries are allowed and encouraged (e.g. Chart.js, Three.js, p5.js, Tone.js). Use `https://` CDN URLs.
6. Do not reference local files or relative paths — everything must be self-contained or CDN-loaded.
7. Make the layout responsive and mobile-friendly where possible.

## Example triggers

- "Build me a snake game"
- "Create a bouncing ball animation"
- "Make an interactive bar chart with Chart.js"
- "Generate a to-do list app"
- "Show me a sine wave audio visualizer"
- "Build a calculator"
- "Create a CSS gradient explorer"
