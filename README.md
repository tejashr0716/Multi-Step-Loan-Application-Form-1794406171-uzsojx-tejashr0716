# ZeTheta FastTrack — Multi-Step Loan Application Portal
## Full Stack Engineer Assessment — Project 1 A (Course ID: 137617)

### Deliverables Compliance Matrix

| Deliverable Part | Status | Technical Implementation |
|---|---|---|
| **Part 1: 8+ Step Form Architecture** | **Completed** | Modular state machine with forward/backward history, progress tracker, and step validation. |
| **Part 2: Conditional Field Rendering** | **Completed** | Reactive field isolation for `PERSONAL`, `HOME`, and `BUSINESS` loan categories. |
| **Part 3: Real-Time PAN & Aadhaar KYC** | **Completed** | NSDL regular expression format validation + simulated asynchronous UIDAI verification with live badges. |
| **Part 4: Document Upload & Compression** | **Completed** | Client-side image/PDF drag-and-drop compression preview + HTML5 Canvas stroke e-signature capture pad. |
| **Part 5: Auto-Save with Resume** | **Completed** | `localStorage` persistence layer saving draft on every keystroke with automatic session restoration. |
| **Part 6: Pre-Approval & Loan Eligibility**| **Completed** | Financial Underwriting Engine computing FOIR (Fixed Obligation to Income Ratio), CIBIL telemetry, and precise EMI. |
| **Part 7: Comprehensive E2E Test Suite** | **Completed** | Playwright test suite (`e2e_test.py`) covering all steps, validations, canvas interaction, and underwriting math with 100% pass rate. |
| **Final Part: Production Submission** | **Completed** | Packaged production bundle with complete documentation. |

---

### Architecture Overview

```
[User Input] ──► [Input Normalization & Masking]
                      │
                      ▼
             [Step-Level Validator] ──(Valid)──► [LocalStorage Draft Persist]
                      │                                   │
                      ├─► [PAN / Aadhaar Gateway Sim]    │
                      ├─► [Smart PIN Autocomplete]       │
                      ├─► [Canvas Signature Capture]     │
                      ├─► [Client File Compression]      │
                      │                                   ▼
                      └──────────────────────────► [Underwriting Engine]
                                                          │
                                         ┌────────────────┴────────────────┐
                                         ▼                                 ▼
                                  [EMI Calculation]               [FOIR & Risk Tier]
                                         │                                 │
                                         └────────────────┬────────────────┘
                                                          ▼
                                            [Instant Pre-Approval Offer]
```

---

### How to Run Locally

1. Open `index.html` directly in any modern browser (Google Chrome, Brave, Safari, Edge).
2. To run the automated E2E test suite:
   ```bash
   python3 e2e_test.py
   ```
   All 10 test cases will execute headlessly and report verification status.
