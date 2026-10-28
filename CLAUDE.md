# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

A single-file IT PMO Kanban demo app for a fictitious bank: `index.html` contains all markup, CSS and JS. There is no build, lint, or test tooling and no package.json. To run it, open `index.html` in a browser (works via `file://`).

## Hard constraints (from the original brief)

- Vanilla HTML/CSS/JS only: no frameworks, bundler, npm, CDN scripts, web fonts or image files. Icons are Unicode glyphs or inline SVG.
- Everything stays in the one file `index.html`.
- No persistence of any kind (no localStorage, sessionStorage, IndexedDB or cookies). Board state is in memory and a refresh resets it to the seeded demo data; the UI says so.
- The only network call is the FormSubmit AJAX endpoint (`FORMSUBMIT_ENDPOINT`, config constant at the top of the script). Its failure must never break the board.
- Do not use real UOB branding or logos; the header uses a neutral "IT PMO" text wordmark. The `UOB-ITPM-####` ID format and the `[UOB IT PMO]` email subject are specified by the brief and are intentional.
- No `!important` in CSS, and no native `alert()` or `confirm()`; use inline errors, toasts and the inline "Delete? Yes / No" toggle.

## Architecture

- `state = { tasks, filters }` is the source of truth. A separate `ui` object holds transient UI state (pending-delete id, drag id, ID counter, sending flag).
- All card and column DOM is built in `renderBoard()` / `renderCard()` as an HTML string and replaced wholesale. Mutate `state`, then call `renderBoard()`; do not edit card DOM directly.
- Every user-supplied string must pass through `escapeHtml()` before it goes into `innerHTML`. Toasts use `textContent`.
- Board interactions use event delegation on `#board` (`setupBoardEvents()`): click for delete/confirm, change for the Move ▸ select, and the HTML5 drag events. Because the board is re-rendered on every change, re-query or restore focus after a render (see `focusCardControl()`).
- The Add Task form lives in a `<dialog>`. `handleSubmit()` validates, adds the card optimistically, then awaits `notifyNewTask()` in a try/catch, keeping the modal open with a disabled "Sending…" button until it settles.
- Overdue means `dueDate < today && status !== "Done"`. Dates are compared as local `YYYY-MM-DD` strings.
- Seed due dates are relative to today (`offsetDate`), so the overdue demo cards stay overdue on any date.
