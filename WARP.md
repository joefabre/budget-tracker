# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

Repository purpose
- Personal Budget Tracker: a dependency-free, single-page web app for tracking income and expenses with charts, printing, and strong accessibility support (508/WCAG 2.1).

Common commands and workflows
- Build: Not applicable (no build toolchain configured)
- Lint: Not applicable (no linter configured)
- Tests: Not applicable (no test framework configured; running a single test is N/A)
- Run locally
  - Open directly: open budget-tracker.html
  - Optional static server (useful if you prefer a local URL):
    - python3 -m http.server 5500
    - Then open http://localhost:5500/budget-tracker.html
- Print: Use your browser’s print dialog; the app renders print-specific charts before printing

High-level architecture (big picture)
- Single-page application in budget-tracker.html
  - Markup defines summary cards, a revenue table, and multiple expense sections (home, daily-living, transportation, entertainment, financial). Each section has a <tbody> with an id pattern like {section}-tbody and a .total-row that the JS updates.
  - Inline JavaScript handles all app logic:
    - State and totals
      - calculateTotals() scans each section’s inputs, updates per-row year totals, per-section monthly totals, and overall summary cards; also manages progress bars and positive/negative balance styling.
      - Format helpers like formatCurrency() centralize currency display.
    - Dynamic editing
      - addIncomeRow() and addExpenseRow(section) insert new rows before the section’s .total-row; deleteRow() removes rows with confirmation.
      - toggleSection(id) collapses/expands sections with a simple class toggle.
    - Persistence and autosave
      - saveData() serializes table inputs per section and writes to localStorage under budgetData_<year>.
      - loadData() and loadFromLocalStorage() restore values; resetData()/resetDataSilent() clear inputs.
      - setInterval autosaves every 30 seconds (skips while an input is focused).
    - Import/export
      - exportToCSV()/exportToJSON() derive data from the live DOM and trigger downloads.
      - handleFileImport() dispatches to importJSONData()/importCSVData(); parseCSVLine() handles quoted CSV fields; loadImportedBudgetData() reconstructs rows before totals recompute.
    - Charts and print integration
      - showCharts() creates a modal via createChartModal() and calls generateCharts().
      - Charts are hand-drawn on HTML5 canvas: createMonthlyChart() (bar), createExpenseChart() (pie), createSavingsChart() (line).
      - Printing uses a separate hidden print area with createPrintMonthlyChart(), createPrintExpenseChart(), createPrintSavingsChart(); printBudget() renders those then invokes window.print().
    - Accessibility
      - Semantic roles/labels, skip link, ARIA live regions on totals, keyboard handling for modal and help.
  - Help integration: openHelp() opens help.html in a new window/tab.
- styles.css
  - Provides responsive layout, consistent column widths, focus outlines, high-contrast and reduced-motion support, and extensive @media print rules that hide editing UI and lay out summary and print charts for one-page output.
- help.html
  - Standalone documentation UI with tabbed content (Getting Started, Features, How-To, Accessibility, Changelog); includes a Close Help action and keyboard escape handling.

Notes from README.md
- Live demo and project overview are in README.md (features, browser support, and technical details: vanilla JS, HTML5 canvas, localStorage, 508 compliance). Opening budget-tracker.html in a modern browser is sufficient to use the app.

Repo layout (essentials only)
- budget-tracker.html — single-page application with inline JS handling all logic
- styles.css — application, accessibility, and print styling
- help.html — help/documentation page launched from the app
- README.md — overview, features, and demo link

Tooling status
- No Node/packager, no CI, and no linter/test suite are present. Development is direct HTML/CSS/JS editing and browser-based verification.
