# PharmaGuard Frontend Documentation

## Overview
PharmaGuard's frontend is a high-performance, clinical-grade dashboard built with **React** and **Vite**. It features a modern "Midnight" dark theme, real-time animations, and a responsive grid layout for pharmacogenomic risk analysis.

## Technology Stack
- **Framework:** React 18 + Vite
- **Styling:** Tailwind CSS v4
- **Animations:** Framer Motion (page transitions, modal springs, staggered lists)
- **Icons:** Lucide React
- **State Management:** React Context / Local State (Lifted to App.jsx)

## Project Structure
```
frontend/
├── src/
│   ├── components/
│   │   ├── Header.jsx          # Top navigation & global "Run" button
│   │   ├── InputPanel.jsx      # VCF upload & Drug selection (Drag-n-drop)
│   │   ├── RiskMatrix.jsx      # Interactive Grid (Active vs Null states)
│   │   ├── ReportModal.jsx     # Detailed JSON report & explainable AI
│   │   ├── SkeletonResults.jsx # Scanning animation state
│   │   └── WarningModal.jsx    # Validation alerts (Amber theme)
│   ├── App.jsx                 # Main layout & State Controller
│   ├── index.css               # Global styles & Tailwind theme config
│   └── main.jsx                # Entry point
└── ...
```

## Key Components

### 1. App.jsx (Controller)
Acts as the central source of truth.
- **State:** Manages `file`, `selectedDrugs`, `status` (idle/scanning/done), and `modalData`.
- **Validation:** Implements `handleRun()` to check for missing files or empty drug selections before triggering analysis.
- **Layout:** Orchestrates the grid layout (Sidebar + Main Content).

### 2. RiskMatrix.jsx (Visualization)
A dynamic grid comparing selected Drugs vs. Key Genes (CYP2D6, CYP2C19, etc.).
- **Smart Filtering:** Only renders rows for drugs selected by the user.
- **Interactive Cells:**
    - *Active:* Clickable, hover effects, color-coded (Red/Amber/Teal).
    - *Null:* Muted, dashed border, non-interactive "N/A".
- **Props:** Accepts `selectedDrugs` array and `onOpenModal` callback.

### 3. ReportModal.jsx (Detailed View)
Fullscreen glassmorphism overlay displaying the AI report.
- **Visuals:** Uses a "Midnight" frosted glass effect (`backdrop-blur-md`).
- **Features:**
    - "Gemini Clinical Summary" box with glowing teal accents.
    - JSON Export & Copy-to-Clipboard functionality.
    - Accessibility: Close on `Esc` key.

### 4. InputPanel.jsx (Data Entry)
- **File Upload:** Drag-and-drop zone for `.vcf` files with success/error states.
- **Drug Selection:** Multi-select dropdown with "pill" tags for easy removal.
- **Validation:** Visual cues when file is missing.

### 5. WarningModal.jsx (Feedback)
- **Trigger:** Appears if user attempts to run analysis without valid inputs.
- **Design:** Spring-animated "Alert" in Amber/Gold theme to demand attention without being aggressive.

## Design System (Midnight Theme)
The application uses a custom color palette defined in `index.css`:

| Variable | Color | Hex Code | Usage |
| :--- | :--- | :--- | :--- |
| `--color-midnight` | **Midnight Black** | `#050505` | Global Background |
| `--color-midnight-card` | **Obsidian** | `#0F1218` | Card Backgrounds |
| `--color-teal` | **Electric Teal** | `#00F2AD` | Primary Actions, Success, Low Risk |
| `--color-crimson` | **Crimson Red** | `#FF4B4B` | High Risk, Critical Alerts |
| `--color-amber` | **Safety Orange** | `#FFB02E` | Moderate Risk, Warnings |

## Development Workflows
- **Start Dev Server:** `npm run dev` (Runs on port 5173/5174)
- **Build for Production:** `npm run build`
- **Linting:** `npm run lint`
