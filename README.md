# Introduction
This repository is my personal exploration of **Software Testing & Quality Assurance**.  
It contains definitions, notes, and small projects I built while learning QA fundamentals.

---

## What is QA?
Quality Assurance (QA) is the process of ensuring that software meets requirements, functions correctly, and provides a good user experience.  
QA is not only about finding bugs, but also about preventing defects and ensuring continuous quality throughout the software development lifecycle (SDLC).

---

## Types of Software Testing

### 1. Manual vs Automated Testing

**Manual Testing**  
The tester executes test cases step by step, without using automation tools.  

*Advantages*  
- Flexible, good for exploratory and usability testing.  
- Can be applied without additional tools or coding knowledge.  

*Disadvantages*  
- Time-consuming.  
- Error-prone.  
- Difficult to scale for large test suites.

**Popular Tools**  
- **JIRA, TestRail, HP ALM**: Used to document test cases, track execution, and manage defects.  
These tools are useful when multiple testers and developers need to collaborate, and when test evidence must be tracked formally. 

**Example (Manual Test Scenario)**  
1. Open a website in a browser  
2. Click **Login**  
3. Enter **username** and **password**  
4. Click **Submit**  
5. Verify that the **user dashboard** page is displayed  
6. Record the result in Excel or TestRail  

---

**Automated Testing**  
The tester writes scripts or uses tools to execute test cases automatically.  

**Advantages**  
- Faster execution.  
- Repeatable and consistent.  
- Very useful for regression testing.  

**Disadvantages**  
- Requires coding or scripting skills.  
- Test scripts need ongoing maintenance.  
- Initial setup can be time-intensive.  


**Popular Tools**  
- **Selenium**: Automates browsers, widely used and language-flexible.  
- **Cypress**: JavaScript-based, focused on modern web apps, fast and developer-friendly.  
- **Robot Framework**: Keyword-driven, easier for non-programmers to read and use.  

**Example (Automated Test Scenario in Python with Selenium)**  

```python
from selenium import webdriver
from selenium.webdriver.common.by import By

driver = webdriver.Chrome()
driver.get("https://example.com/login")

driver.find_element(By.ID, "username").send_keys("testuser")
driver.find_element(By.ID, "password").send_keys("password123")
driver.find_element(By.ID, "login").click()

assert "Dashboard" in driver.page_source
driver.quit()
```

## 2. Test Methodologies

### ISTQB
ISTQB provides a framework of best practices and principles for software testing.  
- Focus on finding defects early and prioritizing tests based on risk.  
- Emphasizes clear documentation of test cases and bug reports.  

**Core Principles of ISTQB:**  
1. **Testing shows the presence of defects** – Testing can show defects exist, but cannot prove their absence.  
2. **Exhaustive testing is impossible** – Testing all inputs and scenarios is impractical; risk-based testing is recommended.  
3. **Early testing saves time and cost** – Start testing as early as possible in the software lifecycle.  
4. **Defect clustering** – Most defects are often found in a few modules.  
5. **Pesticide paradox** – Repeating the same tests will eventually stop finding new defects; test cases should evolve.  
6. **Testing is context-dependent** – Testing approaches vary depending on the application and environment.  
7. **Absence-of-errors fallacy** – Fixing defects alone does not guarantee the software meets user needs.

*Example:* Before releasing a new feature, critical scenarios are identified and tested early, and tests are updated regularly to uncover new defects.

---

### Agile Testing
Agile Testing integrates testing into the development process.  
- Continuous testing within sprints, close collaboration with developers.  
- Automation is encouraged to speed up regression checks.  

*Example:* Each new feature is tested during the sprint, with feedback given immediately to the team to fix issues before the next iteration.

---

### Summary
ISTQB emphasizes structured best practices, while Agile Testing focuses on fast, iterative validation. Many teams combine both to ensure quality without slowing development.

## 3. Common Testing Types

## 3.1 Functional Testing Techniques

- **Unit Testing**: Tests individual software components (functions, modules, or methods) to ensure they work correctly. Typically automated and written during development.  
  *Example:* Testing a single function that calculates tax on an order.

- **Integration Testing**: Verifies that different modules or services work together as expected, focusing on data flow and communication between components.  
  *Example:* Checking that the shopping cart correctly communicates with the payment system.

- **System Testing**: Validates the complete application end-to-end against requirements to ensure all features work together.  
  *Example:* Placing an order from login to payment confirmation.

- **User Acceptance Testing (UAT)**: Performed by end users or clients in the final testing phase to confirm the software meets business requirements before production.  
  *Example:* A client tests a payroll system to verify all calculations are correct.

- **Exploratory Testing**: Informal testing where the tester learns and explores the application to find defects through experimentation and observation.  
  *Example:* Navigating an e-commerce site randomly to look for unexpected behavior.

- **Sanity Testing**: Quick testing of minor code or functionality changes to verify that specific issues have been fixed and no new problems are introduced.  
  *Example:* Verifying that a recently fixed login button now functions correctly.

- **Regression Testing**: Ensures that recent code changes do not break existing features by re-running previous test cases.  
  *Example:* Running tests on the checkout process after updating the discount logic.

- **Smoke Testing**: Basic tests run on a new build to confirm that the major functions work and the build is stable enough for further testing.  
  *Example:* Checking that login, search, and add-to-cart features work after a new deployment.


---

## 3.2 Non-Functional Testing Techniques

- **Load Testing**: Evaluates how a system behaves under expected user load to ensure it can handle multiple simultaneous users.  
  *Example:* Simulating 1,000 concurrent users on a website to check responsiveness.

- **Performance Testing**: Measures the speed, scalability, and stability of the system under various conditions to monitor key metrics like response time and resource usage.  
  *Example:* Measuring page load times and CPU usage during peak traffic.

- **Stress Testing**: Determines the system’s breaking point by applying extreme or beyond-normal load conditions.  
  *Example:* Sending a very high volume of API requests to see when the service fails or returns errors.

- **Security Testing**: Identifies vulnerabilities or threats in the software to prevent unauthorized access or malicious attacks.  
  *Example:* Testing that sensitive user data cannot be accessed without proper authentication.

- **Accessibility Testing**: Ensures the software can be used by people with disabilities, meeting standards such as WCAG.  
  *Example:* Checking that all buttons are operable via keyboard and readable by screen readers.


---

## 3.3 Regression and Non-Regression Testing

- **Regression Testing**: Ensures that recent changes or bug fixes do not break existing functionality.  
  *Example:* After updating the discount calculation, running tests on the checkout process to confirm everything still works.

- **Non-Regression Testing**: Confirms that areas of the system that haven’t changed remain unaffected by updates or fixes.  
  *Example:* After modifying the login feature, verifying that unrelated modules like user profiles or search functionality are still working as expected.
  
---

## 4. Environments

Environments are controlled spaces where software is deployed and tested at different stages of development.  

- **Development (dev):** Where developers write and test code locally. Frequently changing and may be unstable.  
- **Testing / QA:** Dedicated space for systematic testing by QA teams. More stable, focuses on functional and non-functional testing.  
- **Staging:** Production-like environment for final testing. Nearly identical to production setup, used for final validation.  
- **Production (prod):** Live environment with real users. Limited testing is performed, mostly monitoring and smoke tests.  

---

## Resources
The following resources guided the definitions and informations outlined in this repository:
- [QA Roadmap – roadmap.sh](https://roadmap.sh/qa)  
- [ISTQB Certified Tester Foundation Level Syllabus (Version 4.0.1)](https://istqb.org/wp-content/uploads/2024/11/ISTQB_CTFL_Syllabus_v4.0.1.pdf)
- [Todo app – GitHub](https://github.com/FeresMrad/todo-app) (application used for tests) 


*Next steps:* 
- Add automated tests.
- Further additions (TBD)
