---
name: reviewing-selenium-java
description: Reviews Selenium Java automation code for best practices, architecture (POM), locator strategy, and production readiness. Use when the user asks to review, audit, or improve Selenium Java test scripts.
---
# Reviewing Selenium Java

This skill evaluates Selenium Java code against enterprise automation standards (Clean Code, POM, robust locators, and efficient waits).

## When to use this skill
- User provides a `.java` file or code snippet using Selenium and TestNG/JUnit.
- User asks: "How can I improve this Selenium script?"
- Code review requests for automation frameworks.

## Workflow
1. [ ] **Code Analysis**: Check for common pitfalls:
    - Hardcoded locators in test methods (Violation of POM).
    - Use of `Thread.sleep()` or excessive `implicitlyWait`.
    - Hardcoded credentials and URLs.
    - Lack of WebDriver management (e.g., missing WebDriverManager).
2. [ ] **Locator Strategy**: Verify if locators are unique and robust (IDs/Names are preferred; avoid absolute XPaths).
3. [ ] **Assertion Check**: Ensure assertions are meaningful and specific to the test case (e.g., checking for an actual error message instead of just a page title).
4. [ ] **Categorization**: Report issues as Critical (Must Fix), Important (Should Fix), or Minor (Nitpicks).
5. [ ] **Recommendation**: Provide a refactored version using Page Object Model (POM).

## Instructions

### 1. Essential Checkpoints
- **Wait Strategy**: Prefer `WebDriverWait` (Explicit) over `implicitlyWait`.
- **Framework Architecture**: Tests should not contain locators. They should be in Page Classes.
- **Resource Management**: Ensure `driver.quit()` is called in `@AfterMethod` or `@AfterClass`.

### 2. Common Fixes
- **Hardcoding**: Move URLs and credentials to a `.properties` file or environment variables.
- **Locators**: Move `By.id(...)` to private fields in Page Objects.

## Resources
- [Java POM Example](examples/pom-example.java)
- [Best Practices Checklist](resources/checklist.md)
