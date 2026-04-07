# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Expense Tracker starter project built with React 19 and Vite 7. Single-page app for managing financial transactions (income/expenses) with filtering by type and category. This is a course project with intentional bugs and messy code meant to be improved.

## Commands

- `npm run dev` — Start dev server (http://localhost:5173)
- `npm run build` — Production build to `dist/`
- `npm run lint` — ESLint check
- `npm run preview` — Preview production build

**Requires Node.js >= 20** (use `nvm use 20` if needed).

## Architecture

Single-component React app — all logic lives in `src/App.jsx`:
- **Entry:** `index.html` → `src/main.jsx` → `src/App.jsx`
- **State:** Local `useState` hooks only (no Context, no Redux, no router)
- **Styling:** Plain CSS in `src/App.css` (component styles) and `src/index.css` (global reset/fonts)

### App.jsx State & Logic

- `transactions` array — objects with `{id, description, amount, type, category, date}`
- Separate `useState` for each form field (description, amount, type, category)
- Filter states for type and category
- Computed: `totalIncome`, `totalExpenses`, `balance`, `filteredTransactions`
- Categories: food, housing, utilities, transport, entertainment, salary, other
- Types: income, expense
