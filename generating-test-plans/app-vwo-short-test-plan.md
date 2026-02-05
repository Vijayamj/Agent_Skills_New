# 🧪 Short Test Plan: app.vwo.com
**Project Name:** VWO Platform Core Validation  
**Version:** 1.0  
**Prepared By:** Antigravity AI  
**Date:** February 6, 2026  

### 1. Objective
To validate the core functionalities of the VWO platform (Login, Campaign Creation, Heatmaps, and Session Recordings) to ensure a seamless experience for marketers and product teams.

### 2. Scope
**In Scope:**
*   User Authentication (Login/Signup/SSO)
*   A/B Testing & Split URL Campaign Creation (Visual Editor)
*   Heatmap generation and data visualization
*   Session Recording playback and filtering
*   Dashboard reporting and analytics accuracy

**Out of Scope:**
*   Third-party integrations (HubSpot, Salesforce, etc.)
*   Mobile SDK testing
*   Performance load testing (>10k concurrent users)

### 3. Test Approach
*   **Manual Testing:** Visual validation of the VWO SmartCode implementation and Visual Editor interactions.
*   **Automation:** Playwright (TypeScript) for regression testing of the login flow and campaign lifecycle.
*   **AI-Assisted:** Using AI for self-healing scripts when the Visual Editor UI updates and for generating edge-case test scenarios.

### 4. Test Environment
*   **OS:** Windows 11, macOS Sonoma
*   **Browser(s):** Chrome, Firefox, Safari, Edge
*   **Test URL:** [https://app.vwo.com](https://app.vwo.com)
*   **Test Data:** Dedicated QA accounts, mock e-commerce site for tracking validation.

### 5. Entry & Exit Criteria
*   **Entry:**
    *   Functional requirements for the sprint are finalized.
    *   Test Environment (Staging/Sandbox) is accessible.
*   **Exit:**
    *   100% of P0 & P1 test cases executed.
    *   Zero open Critical or High severity defects.

### 6. Deliverables
*   Test Scenarios & Cases
*   Playwright Automation Suite
*   Daily Execution & Defect Reports
*   Final Test Summary Report (TSR)

### 7. Risks
*   **Dynamic UI:** Frequent updates to the Visual Editor may require high maintenance for automation.
*   **Latency:** Data processing delays in Heatmaps might affect real-time validation.

### 8. Approval
**QA Lead / Product Owner**
