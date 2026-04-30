# OpenClaw Pilot

OpenClaw Pilot is a browser-side Agent pilot for capturing web context and turning active pages into actionable input for intelligent agents.

It started as a Chrome extension side panel for OpenClaw, with hooks for reading page content, injecting browser context, and routing actions through a reverse gateway. The direction is to evolve it into a lightweight browser control layer where agents can observe pages, understand user context, and delegate tasks to model backends such as Gemini, Claude-compatible services, or other OpenClaw-connected agents.

## What It Does

- Runs as a Manifest V3 Chrome extension.
- Opens an OpenClaw side panel directly inside the browser.
- Captures and injects webpage context for downstream agent workflows.
- Provides reverse gateway modules for routing browser-side actions.
- Includes content scripts, side panel UI assets, extension icons, and declarative network rules.

## Intended Direction

OpenClaw Pilot is intended to become a browser Agent bridge:

- Webpage capture: extract the current page, selected content, and browser state as agent context.
- Agent delegation: route user tasks from the browser to OpenClaw agents.
- Multi-model support: prepare the extension layer for Gemini, Claude-compatible models, and other model providers.
- Browser automation: expose controlled browser actions through the extension runtime.
- Side-panel workflow: keep the agent close to the active browsing session without switching apps.

## Repository Layout

- `manifest.json`: Chrome extension manifest.
- `background.js`: extension service worker.
- `src/content-script.js`: page content bridge.
- `src/read-inject.js`: injected page reader.
- `src/reverse/`: reverse gateway and RPC modules.
- `src/sidepanel.html`: side panel entry point.
- `assets/`: bundled side panel assets and locale files.
- `icons/`: extension icons and source artwork.

## Status

This repository currently contains the reverse-engineered extension package and supporting source fragments. The next development step is to clean up the extension architecture, document the gateway contract, and formalize the agent-facing API.
