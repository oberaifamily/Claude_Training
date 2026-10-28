<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>IT PMO – Project Board (Demo)</title>
<style>
/* ===== Design tokens: corporate blue palette + spacing scale ===== */
:root {
  --blue-900: #0b2a55;
  --blue-700: #134a94;
  --blue-600: #1b5fb8;
  --blue-100: #e3edf9;
  --blue-50: #f2f6fc;
  --ink: #1b2430;
  --ink-soft: #566274;
  --line: #d3dce8;
  --surface: #ffffff;
  --bg: #eef2f7;
  --red: #c62828;
  --red-bg: #fdecea;
  --amber: #e69100;
  --amber-bg: #fff4de;
  --grey: #8a94a3;
  --green: #1e7a4a;
  --radius: 8px;
  --s1: 4px;
  --s2: 8px;
  --s3: 12px;
  --s4: 16px;
  --s5: 24px;
  --s6: 32px;
  --font: system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
}

* { box-sizing: border-box; }
body { margin: 0; font-family: var(--font); color: var(--ink); background: var(--bg); font-size: 14px; line-height: 1.4; }
button, input, select, textarea { font: inherit; color: inherit; }
:focus-visible { outline: 3px solid var(--blue-600); outline-offset: 2px; }

/* ===== Header ===== */
.app-header { background: var(--blue-900); color: #fff; padding: var(--s3) var(--s5); display: flex; flex-wrap: wrap; align-items: center; gap: var(--s4); }
.wordmark { font-size: 20px; font-weight: 700; letter-spacing: 0.04em; margin: 0; }
.wordmark span { font-weight: 400; opacity: 0.8; margin-left: var(--s2); font-size: 14px; letter-spacing: 0; }
.summary { display: flex; flex-wrap: wrap; gap: var(--s2); margin: 0; padding: 0; list-style: none; flex: 1; }
.summary li { background: rgba(255,255,255,0.12); border-radius: var(--radius); padding: var(--s1) var(--s3); white-space: nowrap; }
.summary strong { font-size: 16px; margin-right: var(--s1); }
.summary .overdue-stat { background: var(--red); }
.btn { border: 1px solid transparent; border-radius: var(--radius); padding: var(--s2) var(--s4); cursor: pointer; font-weight: 600; }
.btn-primary { background: var(--blue-600); color: #fff; }
.btn-primary:hover { background: var(--blue-700); }
.btn-primary:disabled { opacity: 0.7; cursor: progress; }
.btn-header { background: #fff; color: var(--blue-900); }
.btn-header:hover { background: var(--blue-100); }
.btn-secondary { background: var(--surface); border-color: var(--line); }
.btn-secondary:hover { background: var(--blue-50); }

/* ===== Notice + filter bar ===== */
.demo-note { margin: 0; padding: var(--s2) var(--s5); background: var(--blue-100); color: var(--blue-900); font-size: 12px; }
.filters { display: flex; flex-wrap: wrap; align-items: flex-end; gap: var(--s3); padding: var(--s3) var(--s5); background: var(--surface); border-bottom: 1px solid var(--line); }
.filters .field { display: flex; flex-direction: column; gap: var(--s1); }
.filters label { font-size: 12px; font-weight: 600; color: var(--ink-soft); }
.filters input, .filters select { padding: 6px var(--s2); border: 1px solid var(--line); border-radius: 6px; background: #fff; min-width: 170px; }

/* ===== Board ===== */
.board { display: flex; gap: var(--s4); padding: var(--s5); align-items: flex-start; }
.column { flex: 1 1 0; min-width: 0; background: #e4eaf3; border: 2px solid transparent; border-radius: var(--radius); padding: var(--s3); min-height: 200px; }
.column.drop-target { border-color: var(--blue-600); background: var(--blue-100); }
.column-header { display: flex; justify-content: space-between; align-items: center; margin-bottom: var(--s3); }
.column-header h2 { margin: 0; font-size: 15px; color: var(--blue-900); }
.count-badge { background: var(--blue-700); color: #fff; border-radius: 999px; padding: 1px 10px; font-size: 12px; font-weight: 700; }
.column-body { display: flex; flex-direction: column; gap: var(--s3); min-height: 80px; }
.empty { color: var(--ink-soft); font-size: 12px; text-align: center; padding: var(--s4); border: 1px dashed var(--line); border-radius: var(--radius); }

/* ===== Cards ===== */
.card { background: var(--surface); border-radius: var(--radius); border-left: 6px solid var(--grey); padding: var(--s3); box-shadow: 0 1px 2px rgba(11,42,85,0.15); cursor: grab; }
.card.dragging { opacity: 0.45; }
.card.prio-critical { border-left-color: var(--red); }
.card.prio-high { border-left-color: var(--amber); }
.card.prio-medium { border-left-color: var(--blue-600); }
.card.prio-low { border-left-color: var(--grey); }
.card-top { display: flex; justify-content: space-between; align-items: center; gap: var(--s2); font-size: 12px; color: var(--ink-soft); }
.card-id { font-weight: 700; font-family: ui-monospace, Menlo, Consolas, monospace; }
.card-title { margin: var(--s2) 0; font-size: 14px; font-weight: 600; overflow-wrap: anywhere; }
.card-meta { display: grid; gap: 2px; font-size: 12px; color: var(--ink-soft); overflow-wrap: anywhere; }
.card-tags { display: flex; flex-wrap: wrap; gap: var(--s1); margin: var(--s2) 0; }
.pill, .tag, .overdue-badge { display: inline-block; border-radius: 999px; padding: 1px var(--s2); font-size: 11px; font-weight: 700; }
.pill-critical { background: var(--red-bg); color: var(--red); }
.pill-high { background: var(--amber-bg); color: #8a5600; }
.pill-medium { background: var(--blue-100); color: var(--blue-700); }
.pill-low { background: #eceff3; color: #4a5563; }
.tag { background: var(--blue-50); color: var(--blue-900); border: 1px solid var(--line); font-weight: 600; }
.overdue-badge { background: var(--red-bg); color: var(--red); border: 1px solid var(--red); }
.card-actions { display: flex; justify-content: space-between; align-items: center; gap: var(--s2); margin-top: var(--s2); }
.move-select { padding: 3px var(--s1); border: 1px solid var(--line); border-radius: 6px; background: var(--blue-50); font-size: 12px; max-width: 120px; }
.icon-btn { border: 1px solid transparent; background: transparent; border-radius: 6px; width: 28px; height: 28px; cursor: pointer; font-size: 18px; line-height: 1; color: var(--ink-soft); }
.icon-btn:hover { background: var(--red-bg); color: var(--red); }
.confirm { display: flex; align-items: center; gap: var(--s2); font-size: 12px; font-weight: 600; color: var(--red); }
.confirm button { border: 1px solid var(--line); border-radius: 6px; background: #fff; padding: 2px var(--s2); cursor: pointer; font-size: 12px; }
.confirm button.yes { background: var(--red); color: #fff; border-color: var(--red); }

/* ===== Modal form ===== */
dialog { border: none; border-radius: var(--radius); padding: 0; width: min(560px, calc(100vw - 32px)); box-shadow: 0 10px 40px rgba(0,0,0,0.35); }
dialog::backdrop { background: rgba(11,42,85,0.5); }
.dialog-head { background: var(--blue-900); color: #fff; padding: var(--s3) var(--s4); display: flex; justify-content: space-between; align-items: center; }
.dialog-head h2 { margin: 0; font-size: 16px; }
.dialog-head .icon-btn { color: #fff; }
.dialog-head .icon-btn:hover { background: rgba(255,255,255,0.2); color: #fff; }
form { padding: var(--s4); display: grid; grid-template-columns: 1fr 1fr; gap: var(--s3); max-height: 80vh; overflow-y: auto; }
.form-field { display: flex; flex-direction: column; gap: var(--s1); }
.form-field.full { grid-column: 1 / -1; }
.form-field label { font-weight: 600; font-size: 12px; }
.req { color: var(--red); }
.form-field input, .form-field select, .form-field textarea { padding: var(--s2); border: 1px solid var(--line); border-radius: 6px; background: #fff; width: 100%; }
.form-field textarea { resize: vertical; min-height: 70px; }
.form-field [aria-invalid="true"] { border-color: var(--red); background: var(--red-bg); }
.error { color: var(--red); font-size: 12px; min-height: 0; }
.form-actions { grid-column: 1 / -1; display: flex; justify-content: flex-end; gap: var(--s2); }

/* ===== Toasts ===== */
.toast-region { position: fixed; bottom: var(--s4); right: var(--s4); display: flex; flex-direction: column; gap: var(--s2); z-index: 1000; max-width: calc(100vw - 32px); }
.toast { background: var(--blue-900); color: #fff; padding: var(--s3) var(--s4); border-radius: var(--radius); box-shadow: 0 4px 14px rgba(0,0,0,0.3); border-left: 6px solid var(--green); }
.toast.warn { border-left-color: var(--amber); }
.toast::before { content: "\2713  "; font-weight: 700; }
.toast.warn::before { content: "\26A0  "; }

/* ===== Responsive ===== */
@media (max-width: 767px) {
  .board { flex-direction: column; padding: var(--s3); }
  .column { width: 100%; flex: none; }
  .app-header, .filters { padding-left: var(--s3); padding-right: var(--s3); }
  form { grid-template-columns: 1fr; }
}
</style>
</head>
<body>

<!-- ===== Header: wordmark, live summary strip, Add Task button ===== -->
<header class="app-header">
  <h1 class="wordmark">IT PMO<span>Project Board</span></h1>
  <ul class="summary" id="summary" aria-label="Board summary"></ul>
  <button type="button" class="btn btn-header" id="openForm">+ Add Task</button>
</header>
<p class="demo-note">Demo / training tool. Board data lives in memory only — refreshing the page resets it to the seeded demo tasks.</p>

<!-- ===== Filter bar ===== -->
<section class="filters" aria-label="Board filters">
  <div class="field">
    <label for="fProject">Project</label>
    <select id="fProject"></select>
  </div>
  <div class="field">
    <label for="fAssignee">Assignee contains</label>
    <input type="text" id="fAssignee" placeholder="e.g. Tan">
  </div>
  <div class="field">
    <label for="fPriority">Priority</label>
    <select id="fPriority"></select>
  </div>
  <button type="button" class="btn btn-secondary" id="clearFilters">Clear filters</button>
</section>

<!-- ===== Kanban board (columns rendered by renderBoard) ===== -->
<main class="board" id="board" aria-label="Kanban board"></main>

<!-- ===== Add Task modal ===== -->
<dialog id="taskDialog" aria-labelledby="dialogTitle">
  <div class="dialog-head">
    <h2 id="dialogTitle">Add Task</h2>
    <button type="button" class="icon-btn" id="closeForm" aria-label="Close form">&times;</button>
  </div>
  <form id="taskForm" novalidate>
    <div class="form-field full">
      <label for="title">Task Title <span class="req">*</span></label>
      <input type="text" id="title" name="title" maxlength="80" aria-describedby="err-title">
      <span class="error" id="err-title" role="alert"></span>
    </div>
    <div class="form-field full">
      <label for="description">Description</label>
      <textarea id="description" name="description" maxlength="500" aria-describedby="err-description"></textarea>
      <span class="error" id="err-description" role="alert"></span>
    </div>
    <div class="form-field">
      <label for="project">Project / Workstream</label>
      <select id="project" name="project"></select>
      <span class="error" id="err-project" role="alert"></span>
    </div>
    <div class="form-field">
      <label for="category">Category</label>
      <select id="category" name="category"></select>
      <span class="error" id="err-category" role="alert"></span>
    </div>
    <div class="form-field">
      <label for="assignee">Assignee <span class="req">*</span></label>
      <input type="text" id="assignee" name="assignee" maxlength="60" aria-describedby="err-assignee">
      <span class="error" id="err-assignee" role="alert"></span>
    </div>
    <div class="form-field">
      <label for="priority">Priority</label>
      <select id="priority" name="priority"></select>
      <span class="error" id="err-priority" role="alert"></span>
    </div>
    <div class="form-field">
      <label for="dueDate">Due Date <span class="req">*</span></label>
      <input type="date" id="dueDate" name="dueDate" aria-describedby="err-dueDate">
      <span class="error" id="err-dueDate" role="alert"></span>
    </div>
    <div class="form-field">
      <label for="status">Status</label>
      <select id="status" name="status"></select>
      <span class="error" id="err-status" role="alert"></span>
    </div>
    <div class="form-actions">
      <button type="button" class="btn btn-secondary" id="cancelForm">Cancel</button>
      <button type="submit" class="btn btn-primary" id="submitBtn">Add Task</button>
    </div>
  </form>
</dialog>

<!-- Toast region: announced politely by screen readers -->
<div class="toast-region" id="toasts" aria-live="polite"></div>

<script>
"use strict";

/* ===================================================================
   CONFIG
   -------------------------------------------------------------------
   FormSubmit requires a ONE-TIME ACTIVATION: the first submission sent
   to this address triggers a confirmation email to it. Submissions are
   only delivered after the link in that email is clicked.
   Swap the email address below (the only place it is used).
   =================================================================== */
const FORMSUBMIT_ENDPOINT = "https://formsubmit.co/ajax/YOUR_EMAIL@example.com";

/* ===================================================================
   CONSTANTS: fixed lists used for columns, selects and validation
   =================================================================== */
const STATUSES = ["Backlog", "In Progress", "Blocked", "Done"];
const PROJECTS = ["Core Banking Upgrade", "Digital Channels", "Cybersecurity Uplift", "Data & Analytics", "Infrastructure & Cloud", "Vendor Management"];
const CATEGORIES = ["Application Development", "Infrastructure", "Cybersecurity", "Data", "Compliance", "Vendor"];
const PRIORITIES = ["Critical", "High", "Medium", "Low"];

/* ===================================================================
   STATE: single source of truth (in memory only, no storage APIs)
   =================================================================== */
const state = { tasks: [], filters: { project: "", assignee: "", priority: "" } };
const ui = { pendingDeleteId: null, draggingId: null, nextId: 1, sending: false };

/* ===================================================================
   HELPERS
   =================================================================== */
// Escape user-supplied strings before they go into HTML
function escapeHtml(value) {
  return String(value).replace(/[&<>"']/g, (c) => ({ "&": "&amp;", "<": "&lt;", ">": "&gt;", '"': "&quot;", "'": "&#39;" }[c]));
}

// Local date as YYYY-MM-DD (string comparison works for ISO dates)
function dateString(d) {
  const p = (n) => String(n).padStart(2, "0");
  return d.getFullYear() + "-" + p(d.getMonth() + 1) + "-" + p(d.getDate());
}
function todayString() { return dateString(new Date()); }
function offsetDate(days) { const d = new Date(); d.setDate(d.getDate() + days); return dateString(d); }

function isOverdue(task) { return task.status !== "Done" && task.dueDate < todayString(); }
function formatId(n) { return "UOB-ITPM-" + String(n).padStart(4, "0"); }
function slug(s) { return s.toLowerCase(); }

/* ===================================================================
   SEED DATA: 8 demo tasks (due dates relative to today)
   =================================================================== */
function seedTasks() {
  const rows = [
    ["Migrate FX pricing service to AWS", "Lift and shift the FX pricing microservices to the new landing zone.", "Infrastructure & Cloud", "Infrastructure", "Priya Nair", "High", 21, "In Progress"],
    ["Patch CVE-2025-XXXX on branch teller VDI", "Roll out vendor patch to all branch teller virtual desktops.", "Cybersecurity Uplift", "Cybersecurity", "Marcus Tan", "Critical", -2, "In Progress"],
    ["UAT sign-off for mobile onboarding release 4.2", "Collect business sign-off for the eKYC onboarding flow.", "Digital Channels", "Application Development", "Aisha Rahman", "High", 5, "In Progress"],
    ["Renew core banking vendor support contract", "Awaiting legal review of revised SLA terms.", "Vendor Management", "Vendor", "Daniel Lim", "Medium", 12, "Blocked"],
    ["Build regulatory reporting data mart", "Design star schema for monthly liquidity reports.", "Data & Analytics", "Data", "Chen Wei", "Medium", 45, "Backlog"],
    ["Quarterly access recertification", "Complete user access review for core banking admins.", "Cybersecurity Uplift", "Compliance", "Sofia Hernandez", "Low", 30, "Backlog"],
    ["Core banking DB upgrade – rehearsal 2", "Awaiting DR environment from infrastructure team.", "Core Banking Upgrade", "Infrastructure", "Ravi Kumar", "Critical", -5, "Blocked"],
    ["Decommission legacy SMS gateway", "Gateway retired and monitoring removed.", "Digital Channels", "Infrastructure", "Grace Ong", "Low", -10, "Done"]
  ];
  state.tasks = rows.map((r) => ({
    id: formatId(ui.nextId++), title: r[0], description: r[1], project: r[2], category: r[3],
    assignee: r[4], priority: r[5], dueDate: offsetDate(r[6]), status: r[7]
  }));
}

/* ===================================================================
   FILTERING
   =================================================================== */
function applyFilters(tasks) {
  const f = state.filters;
  const needle = f.assignee.trim().toLowerCase();
  return tasks.filter((t) =>
    (!f.project || t.project === f.project) &&
    (!f.priority || t.priority === f.priority) &&
    (!needle || t.assignee.toLowerCase().includes(needle))
  );
}

/* ===================================================================
   RENDERING (the only place card/column DOM is built)
   =================================================================== */
function renderCard(task) {
  const overdue = isOverdue(task);
  const moveOptions = STATUSES.filter((s) => s !== task.status)
    .map((s) => `<option value="${escapeHtml(s)}">${escapeHtml(s)}</option>`).join("");
  const actions = ui.pendingDeleteId === task.id
    ? `<div class="confirm" role="group" aria-label="Confirm delete ${escapeHtml(task.id)}">
         <span>Delete?</span>
         <button type="button" class="yes" data-action="delete-yes" data-id="${escapeHtml(task.id)}">Yes</button>
         <button type="button" data-action="delete-no" data-id="${escapeHtml(task.id)}">No</button>
       </div>`
    : `<button type="button" class="icon-btn" data-action="delete" data-id="${escapeHtml(task.id)}" aria-label="Delete task ${escapeHtml(task.id)}">&times;</button>`;
  return `
    <article class="card prio-${slug(task.priority)}" draggable="true" data-id="${escapeHtml(task.id)}" aria-label="${escapeHtml(task.id)}: ${escapeHtml(task.title)}">
      <div class="card-top">
        <span class="card-id">${escapeHtml(task.id)}</span>
        <span class="pill pill-${slug(task.priority)}">${escapeHtml(task.priority)}</span>
      </div>
      <h3 class="card-title">${escapeHtml(task.title)}</h3>
      <div class="card-meta">
        <span>Project: ${escapeHtml(task.project)}</span>
        <span>Assignee: ${escapeHtml(task.assignee)}</span>
        <span>Due: ${escapeHtml(task.dueDate)}</span>
      </div>
      <div class="card-tags">
        <span class="tag">${escapeHtml(task.category)}</span>
        ${overdue ? '<span class="overdue-badge">Overdue</span>' : ""}
      </div>
      <div class="card-actions">
        <select class="move-select" data-action="move" data-id="${escapeHtml(task.id)}" aria-label="Move task ${escapeHtml(task.id)} to another column">
          <option value="">Move ▸</option>${moveOptions}
        </select>
        ${actions}
      </div>
    </article>`;
}

function renderSummary() {
  const total = state.tasks.length;
  const overdue = state.tasks.filter(isOverdue).length;
  const parts = [`<li><strong>${total}</strong>Total</li>`];
  STATUSES.forEach((s) => {
    parts.push(`<li><strong>${state.tasks.filter((t) => t.status === s).length}</strong>${escapeHtml(s)}</li>`);
  });
  parts.push(`<li class="overdue-stat"><strong>${overdue}</strong>Overdue</li>`);
  document.getElementById("summary").innerHTML = parts.join("");
}

function renderBoard() {
  const visible = applyFilters(state.tasks);
  const html = STATUSES.map((status) => {
    const cards = visible.filter((t) => t.status === status);
    return `
      <section class="column" data-status="${escapeHtml(status)}" aria-labelledby="col-${slug(status).replace(/\s/g, "-")}">
        <div class="column-header">
          <h2 id="col-${slug(status).replace(/\s/g, "-")}">${escapeHtml(status)}</h2>
          <span class="count-badge" aria-label="${cards.length} tasks">${cards.length}</span>
        </div>
        <div class="column-body">
          ${cards.length ? cards.map(renderCard).join("") : '<div class="empty">No tasks</div>'}
        </div>
      </section>`;
  }).join("");
  document.getElementById("board").innerHTML = html;
  renderSummary();
}

/* ===================================================================
   TASK ACTIONS: add / move / delete (state first, then re-render)
   =================================================================== */
function addTask(data) {
  const task = Object.assign({ id: formatId(ui.nextId++) }, data);
  state.tasks.push(task);
  renderBoard();
  return task;
}

function moveTask(id, newStatus) {
  const task = state.tasks.find((t) => t.id === id);
  if (!task || !STATUSES.includes(newStatus) || task.status === newStatus) return;
  task.status = newStatus;
  renderBoard();
}

function deleteTask(id) {
  state.tasks = state.tasks.filter((t) => t.id !== id);
  ui.pendingDeleteId = null;
  renderBoard();
}

/* ===================================================================
   TOASTS
   =================================================================== */
function showToast(message, type) {
  const el = document.createElement("div");
  el.className = "toast" + (type === "warn" ? " warn" : "");
  el.textContent = message;
  document.getElementById("toasts").appendChild(el);
  setTimeout(() => el.remove(), type === "warn" ? 6000 : 3500);
}

/* ===================================================================
   FORMSUBMIT NOTIFICATION (never allowed to break the board)
   =================================================================== */
async function notifyNewTask(task) {
  const res = await fetch(FORMSUBMIT_ENDPOINT, {
    method: "POST",
    headers: { "Content-Type": "application/json", Accept: "application/json" },
    body: JSON.stringify({
      _subject: `[UOB IT PMO] New task ${task.id}: ${task.title}`,
      _template: "table",
      _captcha: "false",
      "Task ID": task.id,
      Title: task.title,
      Description: task.description,
      Project: task.project,
      Category: task.category,
      Assignee: task.assignee,
      Priority: task.priority,
      "Due Date": task.dueDate,
      Status: task.status,
      "Submitted At": new Date().toISOString(),
    }),
  });
  if (!res.ok) throw new Error(`FormSubmit failed: ${res.status}`);
  return res.json();
}

/* ===================================================================
   FORM: validation + submit
   =================================================================== */
const form = document.getElementById("taskForm");
const dialog = document.getElementById("taskDialog");
const submitBtn = document.getElementById("submitBtn");
const FIELD_NAMES = ["title", "description", "project", "category", "assignee", "priority", "dueDate", "status"];

function readForm() {
  const data = {};
  FIELD_NAMES.forEach((n) => { data[n] = form.elements[n].value.trim(); });
  return data;
}

function validate(data) {
  const errors = {};
  if (!data.title) errors.title = "Task title is required.";
  else if (data.title.length > 80) errors.title = "Title must be 80 characters or fewer.";
  if (data.description.length > 500) errors.description = "Description must be 500 characters or fewer.";
  if (!PROJECTS.includes(data.project)) errors.project = "Choose a project.";
  if (!CATEGORIES.includes(data.category)) errors.category = "Choose a category.";
  if (!data.assignee) errors.assignee = "Assignee is required.";
  if (!PRIORITIES.includes(data.priority)) errors.priority = "Choose a priority.";
  if (!data.dueDate) errors.dueDate = "Due date is required.";
  else if (data.dueDate < todayString()) errors.dueDate = "Due date cannot be in the past.";
  if (!STATUSES.includes(data.status)) errors.status = "Choose a status.";
  return errors;
}

function showErrors(errors) {
  FIELD_NAMES.forEach((n) => {
    const input = form.elements[n];
    const msg = errors[n] || "";
    document.getElementById("err-" + n).textContent = msg;
    if (msg) input.setAttribute("aria-invalid", "true"); else input.removeAttribute("aria-invalid");
  });
}

function resetForm() {
  form.reset();
  form.elements.priority.value = "Medium";
  form.elements.status.value = "Backlog";
  showErrors({});
}

async function handleSubmit(event) {
  event.preventDefault();
  if (ui.sending) return;
  const data = readForm();
  const errors = validate(data);
  showErrors(errors);
  const firstBad = FIELD_NAMES.find((n) => errors[n]);
  if (firstBad) { form.elements[firstBad].focus(); return; }

  // Optimistic UI: card appears immediately, notification happens in parallel
  const task = addTask(data);
  resetForm();
  ui.sending = true;
  submitBtn.disabled = true;
  submitBtn.textContent = "Sending…";

  let emailOk = true;
  try {
    await notifyNewTask(task);
  } catch (err) {
    emailOk = false;
  }

  ui.sending = false;
  submitBtn.disabled = false;
  submitBtn.textContent = "Add Task";
  dialog.close();
  if (emailOk) showToast(`Task ${task.id} added and notification sent.`);
  else showToast("Card added locally — email notification failed", "warn");
}

/* ===================================================================
   SETUP: populate selects, wire events
   =================================================================== */
function fillSelect(select, values, placeholder) {
  const opts = (placeholder ? [`<option value="">${escapeHtml(placeholder)}</option>`] : [])
    .concat(values.map((v) => `<option value="${escapeHtml(v)}">${escapeHtml(v)}</option>`));
  select.innerHTML = opts.join("");
}

function setupControls() {
  fillSelect(document.getElementById("fProject"), PROJECTS, "All projects");
  fillSelect(document.getElementById("fPriority"), PRIORITIES, "All priorities");
  fillSelect(form.elements.project, PROJECTS);
  fillSelect(form.elements.category, CATEGORIES);
  fillSelect(form.elements.priority, PRIORITIES);
  fillSelect(form.elements.status, STATUSES);
  resetForm();

  // Filters re-render the board from state
  const onFilter = () => {
    state.filters.project = document.getElementById("fProject").value;
    state.filters.assignee = document.getElementById("fAssignee").value;
    state.filters.priority = document.getElementById("fPriority").value;
    renderBoard();
  };
  ["fProject", "fAssignee", "fPriority"].forEach((id) => {
    document.getElementById(id).addEventListener("input", onFilter);
  });
  document.getElementById("clearFilters").addEventListener("click", () => {
    document.getElementById("fProject").value = "";
    document.getElementById("fAssignee").value = "";
    document.getElementById("fPriority").value = "";
    onFilter();
  });

  // Modal open/close
  document.getElementById("openForm").addEventListener("click", () => {
    form.elements.dueDate.min = todayString();
    dialog.showModal();
    form.elements.title.focus();
  });
  const closeDialog = () => { if (!ui.sending) dialog.close(); };
  document.getElementById("closeForm").addEventListener("click", closeDialog);
  document.getElementById("cancelForm").addEventListener("click", closeDialog);
  dialog.addEventListener("cancel", (e) => { if (ui.sending) e.preventDefault(); });
  form.addEventListener("submit", handleSubmit);

  setupBoardEvents();
}

// Event delegation on the board: clicks, move select, drag and drop
function setupBoardEvents() {
  const board = document.getElementById("board");

  board.addEventListener("click", (e) => {
    const btn = e.target.closest("[data-action]");
    if (!btn) return;
    const id = btn.dataset.id;
    if (btn.dataset.action === "delete") { ui.pendingDeleteId = id; renderBoard(); focusCardControl(id, "delete-yes"); }
    else if (btn.dataset.action === "delete-no") { ui.pendingDeleteId = null; renderBoard(); focusCardControl(id, "delete"); }
    else if (btn.dataset.action === "delete-yes") { deleteTask(id); }
  });

  board.addEventListener("change", (e) => {
    const sel = e.target.closest('[data-action="move"]');
    if (sel && sel.value) moveTask(sel.dataset.id, sel.value);
  });

  board.addEventListener("dragstart", (e) => {
    const card = e.target.closest(".card");
    if (!card) return;
    ui.draggingId = card.dataset.id;
    e.dataTransfer.effectAllowed = "move";
    e.dataTransfer.setData("text/plain", card.dataset.id);
    card.classList.add("dragging");
  });
  board.addEventListener("dragend", () => {
    ui.draggingId = null;
    board.querySelectorAll(".dragging, .drop-target").forEach((el) => el.classList.remove("dragging", "drop-target"));
  });
  board.addEventListener("dragover", (e) => {
    const col = e.target.closest(".column");
    if (!col || !ui.draggingId) return;
    e.preventDefault();
    e.dataTransfer.dropEffect = "move";
    board.querySelectorAll(".drop-target").forEach((el) => { if (el !== col) el.classList.remove("drop-target"); });
    col.classList.add("drop-target");
  });
  board.addEventListener("dragleave", (e) => {
    const col = e.target.closest(".column");
    if (col && !col.contains(e.relatedTarget)) col.classList.remove("drop-target");
  });
  board.addEventListener("drop", (e) => {
    const col = e.target.closest(".column");
    if (!col || !ui.draggingId) return;
    e.preventDefault();
    const id = ui.draggingId;
    ui.draggingId = null;
    moveTask(id, col.dataset.status);
  });
}

// Restore keyboard focus to the relevant control after a delete-confirm re-render
function focusCardControl(id, action) {
  const el = document.querySelector(`[data-action="${action}"][data-id="${CSS.escape(id)}"]`);
  if (el) el.focus();
}

/* ===================================================================
   INIT
   =================================================================== */
seedTasks();
setupControls();
renderBoard();
</script>
</body>
</html>
