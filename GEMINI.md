# FIRE Calculator Project Context

## Overview
This project is an interactive Financial Independence, Retire Early (FIRE) calculator. It is a Single Page Application (SPA) designed to help users visualize their path to financial independence based on current assets, income, spending, and future assumptions.

## Premise & Core Logic
The application's primary function is to calculate the **FI Target** (Financial Independence Number) and **Time to Independence** based on the following user inputs:

### Inputs
- **Current Status:**
    - **Age:** Current age of the user.
    - **Net Worth:** Current value of invested assets.
    - **After-tax Income:** Annual take-home pay.
    - **Annual Spending:** Annual living expenses.
- **Assumptions:**
    - **Withdrawal Rate (SWR):** Percentage of the portfolio withdrawn annually in retirement (e.g., 3.5%, 4.0%).
    - **Expected Growth:** Annualized real return rate on investments (inflation-adjusted).
    - **Additional Retirement Income:** Income streams available post-retirement (e.g., Social Security, Pension).
- **Targets (Bi-directional):**
    - **FI Spend:** Desired annual spending in retirement.
    - **Retirement Age:** Desired age to retire.

### Calculation Modes
The calculator must support two solving modes:
1.  **Solve for Age:** User provides a desired *FI Spend*. The app calculates the required *FI Target* (`(Spend - Add. Income) / SWR`) and projects how many years/growth are needed to reach that number.
2.  **Solve for Spend:** User provides a desired *Retirement Age*. The app projects the portfolio value at that specific age and calculates the sustainable annual spend available (`(Portfolio * SWR) + Add. Income`).

### Outputs
- **FI Target ($):** The total portfolio value required to sustain the desired spending.
- **Time to Independence:** Number of years remaining until the FI Target is reached (or the calculated date/age of financial freedom).
- **Visualizations:**
    - Timeline graph showing Net Worth projection (Accumulation vs. Decumulation).
    - Progress bar indicating % towards the FI number.
    - Run Rate (years of spending covered by current net worth).

## Tech Stack & Architecture
- **Structure:** Currently a single-file solution (`index.html`) containing structure, logic, and styles.
- **Frontend Framework:** Vanilla JavaScript (ES6+). No build step required.
- **Styling:** Tailwind CSS (via CDN) with custom CSS variables for theming.
- **Persistence:** Uses `localStorage` to save user scenarios ("Plans").
- **UI Patterns:**
    - Draggable inputs (desktop) and custom web-component sliders (mobile).
    - Reactive updates (graph and numbers update immediately on input change).
    - Dark mode aesthetic with specific color coding (Green for success/retirement, Yellow for accumulation).

## Development Guidelines
- **Zero-Build:** Maintain the ability to run the file directly in a browser without a build process/bundler unless explicitly refactored.
- **Responsive:** Ensure seamless experience on both desktop (mouse/drag) and mobile (touch/sliders).
- **Performance:** Calculations should be efficient enough to run `oninput` for smooth visual feedback.
