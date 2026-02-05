---
name: generating-test-plans
description: Generates comprehensive, industry-standard test plans for web applications using a professional template. Specialized for social media platforms like Facebook. Use when the user requests a 'Test Plan' for a website or feature.
---
# Generating Test Plans

This skill provides a structured way to create professional test plans, ensuring all critical testing phases (SMOKE, SANITY, REGRESSION) are covered with clear entry/exit criteria.

## When to use this skill
- User says "Write a test plan for [Website/Feature]".
- User needs a "Testing Strategy" document.
- Requests for "Quality Assurance Planning" on Facebook or similar apps.

## Workflow
1. [ ] **Requirement Gathering**: Identify the website (e.g., facebook.com) and the specific module (e.g., Login, Feed, Messaging).
2. [ ] **Context Injection**: Use the [Test Plan Template](resources/test-plan-template.md) as the base.
3. [ ] **Customization**:
    - **Scope**: Define what's in/out of scope for the current sprint.
    - **Test Strategy**: Select appropriate tools (Playwright/Selenium) and frameworks (POM).
    - **Environment**: Detail the OS/Browsers for testing.
4. [ ] **Risk Assessment**: Identify risks like "API Rate Limiting" or "Dynamic Locators" for Facebook.
5. [ ] **Delivery**: Export the populated markdown document to the user.

## Instructions

### 1. The Template Pattern
Always follow the 11-section hierarchy provided in the template. Do not skip sections unless the user explicitly asks.

### 2. Facebook Specific Insights
When creating plans for Facebook:
- **Scope**: Always include multi-device responsiveness (Mobile vs Desktop Feed).
- **Strategy**: Recommend Playwright for its speed with high-dynamic content.
- **Risks**: Highlight "Account Locking/Bot Detection" as a risk for automation.

## Resources
- [Test Plan Template](resources/test-plan-template.md)
