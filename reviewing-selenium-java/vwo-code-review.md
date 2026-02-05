# 🔍 Selenium Java Code Review: VWO Login Test

This review evaluates the submitted script against enterprise automation standards (Clean Code, Page Object Model, and robust wait strategies).

---

## 🚩 Executive Summary
The code is a functional script but is **not production-ready**. It lacks architectural separation (Page Object Model) and relies on implicit waits, which can lead to flaky tests in CI/CD environments.

---

## 🛠 Detailed Findings

### 1. Architecture: Violation of POM (CRITICAL)
- **Issue**: Locators (`By.id`, `By.className`) and actions (`sendKeys`, `click`) are directly inside the `@Test` method.
- **Impact**: If the application's UI changes (e.g., `js-login-btn` ID changes), you must update every test method where it's used.
- **Recommendation**: Move all locators and element-related actions into a separate `LoginPage` class.

### 2. Wait Strategy: Implicit Wait vs. Explicit Wait (IMPORTANT)
- **Issue**: Relying on `driver.manage().timeouts().implicitlyWait(10)`.
- **Impact**: Implicit waits apply to all elements and can slow down execution or fail to handle elements that appear dynamically.
- **Recommendation**: Set implicit wait to 0 or a very low value and use **`WebDriverWait`** (Explicit Wait) for the error message after the login click.

### 3. Hardcoded Data (IMPORTANT)
- **Issue**: URL (`https://app.vwo.com`) and credentials (`test@test.com`) are hardcoded.
- **Impact**: Difficult to run tests against different environments (Stage, QA, Prod) without modifying code.
- **Recommendation**: Externalize configuration to a `config.properties` or `.env` file.

### 4. Code Readability (MINOR)
- **Issue**: No separation between "Arrange", "Act", and "Assert" phases.
- **Recommendation**: Use clear comments or break down actions into readable methods.

---

## 🚀 Refactored Code (Page Object Model)

### 📄 LoginPage.java
```java
public class LoginPage {
    private WebDriver driver;
    private WebDriverWait wait;

    // Locators
    private By emailField = By.id("login-username");
    private By passwordField = By.id("login-password");
    private By loginButton = By.id("js-login-btn");
    private By errorMessage = By.className("notification-box-description");

    public LoginPage(WebDriver driver) {
        this.driver = driver;
        this.wait = new WebDriverWait(driver, Duration.ofSeconds(10));
    }

    public void login(String email, String password) {
        driver.findElement(emailField).sendKeys(email);
        driver.findElement(passwordField).sendKeys(password);
        driver.findElement(loginButton).click();
    }

    public String getErrorMessage() {
        return wait.until(ExpectedConditions.visibilityOfElementLocated(errorMessage)).getText();
    }
}
```

### 📄 VwoLoginTest.java
```java
public class VwoLoginTest {
    WebDriver driver;
    LoginPage loginPage;

    @BeforeMethod
    public void setUp() {
        driver = new ChromeDriver();
        driver.manage().window().maximize();
        driver.get("https://app.vwo.com");
        loginPage = new LoginPage(driver);
    }

    @Test
    public void loginWithInvalidCredentials() {
        loginPage.login("test@test.com", "wrongpassword");
        String actualError = loginPage.getErrorMessage();
        Assert.assertTrue(actualError.contains("Your email, password, IP address or location did not match"), "Error message mismatch!");
    }

    @AfterMethod
    public void tearDown() {
        if (driver != null) {
            driver.quit();
        }
    }
}
```
