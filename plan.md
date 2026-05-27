# Implementation Plan: BrikGestion ERP Mobile App

A universal ERP application for micro-industries (starting with brick factories) to manage raw materials, finished products, production formulas, and replenishment with weighted average price (PMP) tracking.

## Scope & Non-Goals
- **Scope**: Onboarding, Configuration (Module 5), Replenishment (Module 2), and Production Sessions (Module 3).
- **Data Layer**: Client-side only (localStorage) as per session constraints.
- **UI/UX**: Mobile-first responsive web design (PWA style) using React, Tailwind CSS, and Shadcn UI.
- **Non-Goals**: No backend database, no real-time multi-user sync, no external authentication (local only).

## Assumptions & Open Questions
- Currency is fixed to FCFA (Franc CFA).
- The "Mobile Application" requirement will be fulfilled via a high-fidelity responsive web application optimized for mobile viewports.
- Weighted Average Price (PMP) will be calculated locally based on the history of purchases stored in localStorage.

## Affected Areas
- **Frontend**: All UI components, navigation, and state management.
- **State Management**: Custom hooks or a simple store to manage localStorage persistence for:
    - Raw Materials
    - Finished Products
    - Formulas
    - Inventory (Stock levels)
    - Purchase History
    - Production History

## Implementation Phases

### Phase 1: Foundation & Onboarding
- Set up routing (React Router).
- Implement the "Step 0: First Launch" flow.
- Deliverables: Structure name setup, Currency initialization, and Redirection to Configuration.
- **Owner**: `frontend_engineer`

### Phase 2: Module 5 - Configuration (The Brain)
- Implement Raw Material Management (CRUD).
- Implement Finished Product Catalog (CRUD).
- Implement Formula Manager (The "Recipe" system).
- Implement Logistic Conversions (e.g., Truck to KG).
- **Owner**: `frontend_engineer`

### Phase 3: Module 2 - Replenishment (Purchases & Stocks)
- Implement Universal Purchase Input Form.
- Implement PMP (Weighted Average Price) calculation engine.
- Implement Purchase History and Stock Alerting.
- **Owner**: `frontend_engineer`

### Phase 4: Module 3 - Production Sessions
- Implement Production Session Workflow:
    - Pre-requisites check (Stock availability).
    - Session Launch.
    - Session Management (Real-time consumption/output tracking).
    - Session Closing & Stock updates.
- **Owner**: `frontend_engineer`

### Phase 5: Polishing & Validation
- UI/UX refinements for mobile (touch targets, spacing).
- Final bug fixes and data persistence validation.
- **Owner**: `quick_fix_engineer`
