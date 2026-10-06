# Anitha Swaminathan
## Senior QA Analyst | QA Automation Engineer
### Healthcare & Enterprise Applications
### Selenium | Playwright | API Testing | SQL Validation | CI/CD

📧 anithaswam95@gmail.com  
📞 805-559-0536

---

# Senior QA Automation Engineer | Selenium | Playwright | Rest Assured | ETL Testing | Jenkins | GitHub Actions

Welcome to my QA automation portfolio. I am a Senior QA Automation Engineer with 6+ years of hands-on experience in test automation, API testing, ETL validation, and CI/CD integration across healthcare and enterprise applications.

## About Me

Results-driven QA professional with proven expertise in building scalable automation frameworks, leading end-to-end testing strategies, and integrating quality assurance into CI/CD pipelines. My focus is on:

- **Test Automation**: Selenium WebDriver, Playwright, Java, TestNG, Page Object Model
- **API Testing**: REST APIs (Postman), SOAP Web Services, backend validation
- **ETL & Database Testing**: SQL validation, Oracle PL/SQL, data integrity checks
- **Shift-Left Testing**: Automated regression testing, early defect detection, quality metrics
- **CI/CD Integration**: Jenkins, GitHub Actions, automated test reporting
- **BDD Automation**: Cucumber, Gherkin-based test design
- **AI-Enhanced Testing**: ChatGPT, Gemini, Copilot, Claude for test scenario generation
- **Data Analytics**: Power BI dashboards, test metrics visualization, Pandas/NumPy

---

## Professional Experience

### QA Analyst | Kaiser Permanente (via Garni Software Inc.)
**Jan 2024 – Feb 2026** | Leading CA-based Healthcare Organization

**Key Achievements:**
- Built and maintained 200+ regression test cases for Patient Satisfaction Survey Portal and MTM Web Re-write, reducing regression cycle time by 30%
- Owned ETL testing across 5+ source-target combinations with zero production quality failures
- Completed System Integration Testing for Consumer Payment Portal across UI, REST API, and Oracle SQL layers — identified 23 defects pre-UAT including 3 critical payment processing bugs
- Delivered 2 full UAT cycles for BofA Consumer Payment Portal: 120+ test cases, 0% defect escape rate to production
- Maintained 95%+ defect closure rate across 80+ defects logged and tracked in JIRA
- Applied shift-left testing practices, reducing late-stage defect discovery by 40%
- Used AI tools (ChatGPT, Gemini, Claude, Copilot) to generate test scenarios, cutting test case authoring time by 35% while increasing coverage by 20%
- Designed Power BI dashboards for real-time test execution metrics and sprint defect trends
- Executed PL/SQL scripts in Oracle SQL Plus for test data setup and database validation

**Environment:** .NET, SQL Server, Oracle, JIRA, QTEST, Agile/Scrum, ETL, PL/SQL, Postman API, Pandas, NumPy, Power BI, Databricks

### QA Analyst | Healthcare Client — SPARTA EHR (via Garni Software Inc.)
**Mar 2021 – Dec 2023** | Electronic Health Records System

**Key Achievements:**
- Built test plans with 100% requirements traceability across 4 major releases over 3 years
- Executed smoke, system, integration, regression, and functional testing with 90%+ defect detection rate
- Automated Patient Details Capture module using Playwright and JavaScript with scheduled execution
- Validated EHR data integrity across 10+ database tables using SQL Server, catching 15+ data mismatches
- Tracked 60+ defects in JIRA with zero critical-defect production escapes in final 18 months
- Adapted test strategy across 30+ sprints in Agile environment

**Environment:** .NET, SQL Server, JIRA, C#, HTML, JavaScript, Playwright, ASP.NET, MS Azure, Agile

### QA Analyst | Technology Services Provider (via Garni Software Inc.)
**Jan 2020 – Feb 2021** | Cybersecurity & Cloud Computing Focus

**Key Achievements:**
- Coordinated end-to-end QA activities across 3 product releases with zero QA-caused delays
- Wrote 30+ SQL validation queries, catching 12+ data integrity violations
- Built Requirements Traceability Matrix covering 100% of functional requirements
- Executed 80+ UAT test cases with zero reopened defects post-launch
- Built hands-on experience in Selenium WebDriver test automation

**Environment:** Selenium WebDriver, QC, QTP, SQL, PL/SQL, Agile, Waterfall

---

## Core Skills

### Automation Frameworks & Languages
- Selenium WebDriver (web UI test automation)
- Playwright (JavaScript)
- TestNG
- Cucumber (BDD)
- JUnit
- Java
- Page Object Model (POM)

### API Testing
- Rest Assured
- Postman (REST API)
- SOAP UI (SOAP Web Services)
- Backend REST API validation

### Database & ETL Testing
- Oracle SQL / SQL Server
- PL/SQL scripting
- SQL Plus
- ETL pipeline validation
- Data integrity checks
- Test data management

### CI/CD & Execution
- Jenkins
- GitHub Actions
- JIRA (issue tracking & test management)
- QTEST
- HP ALM / Quality Center
- Confluence

### Data Analytics & Visualization
- Power BI (dashboards & visualization)
- Pandas
- NumPy
- Google Colab
- Databricks

### AI & Emerging Tools
- ChatGPT
- Gemini
- Copilot
- Claude
- Iterative prompting for test scenario generation

### Additional Technologies
- .NET, C#, ASP.NET
- MS Azure
- HTML, JavaScript
- MS Excel, PowerPoint, MS Access
- MS Project

### Testing Types
- Functional Testing
- System & Integration Testing
- Regression Testing (automated & manual)
- Smoke & Sanity Testing
- UAT (User Acceptance Testing)
- End-to-End Testing
- Cross-Browser Testing
- ETL Testing
- Backend SQL Validation
- GUI & Usability Testing
- Shift-Left Testing

### Methodologies
- Agile/Scrum
- Waterfall
- SDLC & STLC
- Shift-Left Quality Practices
- Requirements Traceability

---

## CI/CD Workflows

### 1. Rest Assured GitHub Actions Workflow
Repository: [RestAssuredgithubactions](https://github.com/anithaswam95-beep/RestAssuredgithubactions)

This workflow validates REST API automation using Java + Maven + Rest Assured.

```yaml
name: Rest Assured Automation Tests

on:
  push:
    branches:
      - master
  pull_request:
    branches:
      - main
  workflow_dispatch:

jobs:
  test:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout source code
        uses: actions/checkout@v4

      - name: Set up Java
        uses: actions/setup-java@v4
        with:
          java-version: '21'
          distribution: 'temurin'
          cache: maven

      - name: Check Java version
        run: java -version

      - name: Run Maven tests
        run: mvn clean test -DtrimStackTrace=false

      - name: Upload Surefire Report
        if: always()
        uses: actions/upload-artifact@v4
        with:
          name: surefire-report
          path: |
            target/reports/surefire.html
            target/surefire-reports/
          if-no-files-found: warn
```

### 2. Playwright GitHub Actions Workflow
Repository: [playwright-vscode-course](https://github.com/anithaswam95-beep/playwright-vscode-course)

This workflow runs browser automation tests in a CI pipeline using Playwright and Node.js.

```yaml
name: Playwright Tests
on:
  push:
    branches: [main, master]
  pull_request:
    branches: [main, master]
  workflow_dispatch:

permissions:
  contents: read

concurrency:
  group: playwright-${{ github.ref }}
  cancel-in-progress: true

jobs:
  test:
    timeout-minutes: 60
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: Setup Node.js
        uses: actions/setup-node@v4
        with:
          node-version: 20
          cache: npm
          cache-dependency-path: demo/package-lock.json

      - name: Install dependencies
        working-directory: demo
        run: npm ci

      - name: Install Playwright browsers
        working-directory: demo
        run: npx playwright install --with-deps chromium

      - name: Run Playwright tests
        working-directory: demo
        run: npx playwright test

      - name: Upload Playwright HTML report
        uses: actions/upload-artifact@v4
        if: '!cancelled()'
        with:
          name: playwright-report
          path: demo/playwright-report/
          retention-days: 30
          if-no-files-found: warn
```

---

## Flagship Projects

### 1. Lessons
**Selenium Framework Architecture & Best Practices**

- Complete Selenium framework with Page Object Model design pattern
- TestNG test execution with reporting
- Extent Reports for detailed HTML test reports
- Reusable utilities and base classes
- Professional-grade automation framework design

### 2. SeleniumMavenProject
**Java-Based UI Automation with Data-Driven Testing**

- 15+ test scenarios across real public websites
- TestNG test execution with groups and parameterization
- Excel-driven data input using Apache POI
- Cross-browser testing support
- Maven build automation

### 3. RestAssuredgithubactions
**API Automation with GitHub Actions CI/CD**

- REST API test automation using Rest Assured
- CRUD operation validation
- GitHub Actions CI/CD pipeline (automated on every push)
- Maven-based build execution
- Test reporting and artifact upload

### 4. playwright-vscode-course
**Modern Web Automation with Playwright & TypeScript**

- 57+ test scenarios using Playwright
- TypeScript-based automation
- Cross-browser execution
- API mocking and request interception
- HTML reporting with GitHub Actions CI/CD

### 5. MyfirstCucumberProject
**BDD Testing with Cucumber & Gherkin**

- Feature file-based test design
- Step definition implementations with Selenium
- TestNG execution with Cucumber plugin
- 16+ passing steps across multiple scenarios

### 6. [employee-analytics-capstone](https://github.com/anithaswam95-beep/employee-analytics-capstone)
**SQL Capstone on Employee Analytics & Department Performance (Databricks)**

- 194-cell SQL notebook: basics to advanced + 46 exercises incl. DAX-to-SQL translations
- Workforce & compensation analytics: headcount, avg salary, top earners, salary tiers + running totals
- Window functions, CTEs (incl. recursive), PIVOT/UNPIVOT, JSON/VARIANT, Delta Lake time travel
- Standalone `sql/key_queries.sql` highlights + `setup_sample_data.sql` to rerun anywhere

---

## Supporting Projects

- **websitelevel** — Selenium locator practice and element interaction
- **powerbi-portfolio** — Data visualization and analytics
- **linux-practice-portfolio** — Linux command line and shell scripting

---

## Technology Stack

| Category | Tools |
|----------|-------|
| **Languages** | Java, TypeScript, Gherkin, SQL, PL/SQL, C#, HTML, JavaScript, Python |
| **Automation** | Selenium, Playwright, TestNG, Cucumber, JUnit |
| **API Testing** | Rest Assured, Postman, SOAP UI |
| **Build & CI/CD** | Maven, Jenkins, GitHub Actions |
| **Database/ETL** | Oracle, SQL Server, PL/SQL, Databricks |
| **Test Management** | JIRA, QTEST, HP ALM, Quality Center |
| **Analytics** | Power BI, Pandas, NumPy, Google Colab |
| **AI Tools** | ChatGPT, Gemini, Copilot, Claude |
| **IDEs** | IntelliJ IDEA, Eclipse, VS Code |
| **Cloud/DevOps** | MS Azure, .NET, ASP.NET |

---

## Key Achievements & Metrics

✅ **6+ years** of hands-on QA automation and testing expertise across healthcare and enterprise applications  
✅ **200+ regression test cases** built and maintained, reducing regression cycle time by 30%  
✅ **5+ ETL pipelines** validated with zero production quality failures  
✅ **23 defects** identified pre-UAT in System Integration Testing (3 critical payment bugs prevented)  
✅ **2 full UAT cycles** completed: 120+ test cases, 0% defect escape rate to production  
✅ **95%+ defect closure rate** across 80+ defects managed in JIRA  
✅ **40% reduction** in late-stage defect discovery through shift-left testing practices  
✅ **35% reduction** in test case authoring time using AI-assisted workflows  
✅ **20% increase** in test coverage metrics per sprint using AI (ChatGPT, Gemini, Claude)  
✅ **Real-time dashboards** designed in Power BI for test execution metrics and release readiness  
✅ **Zero critical-defect production escapes** in final 18 months at SPARTA EHR  
✅ **100% requirements traceability** maintained across all releases  

---

## Professional Summary

Senior QA Automation Engineer with 6+ years of proven expertise in building scalable automation frameworks, designing comprehensive test strategies, and integrating quality assurance into enterprise CI/CD pipelines. Deep hands-on experience with Selenium, Playwright, Java, TestNG, REST APIs, SQL, ETL testing, and Oracle databases across healthcare and enterprise sectors. Expert in shift-left testing practices, AI-assisted test scenario generation, and delivering zero-defect UAT cycles. Skilled at translating business requirements into robust automation solutions, mentoring team members, and communicating quality metrics to technical and business stakeholders. Passionate about leveraging modern testing tools, AI capabilities, and data-driven insights to accelerate software delivery and improve product quality.

---

## Quick Links

- [Lessons](https://github.com/anithaswam95-beep/Lessons) — Framework Architecture
- [SeleniumMavenProject](https://github.com/anithaswam95-beep/SeleniumMavenProject) — UI Automation
- [RestAssuredgithubactions](https://github.com/anithaswam95-beep/RestAssuredgithubactions) — API + CI/CD
- [playwright-vscode-course](https://github.com/anithaswam95-beep/playwright-vscode-course) — Modern Automation
- [MyfirstCucumberProject](https://github.com/anithaswam95-beep/MyfirstCucumberProject) — BDD Testing
- [employee-analytics-capstone](https://github.com/anithaswam95-beep/employee-analytics-capstone) — SQL Capstone: Employee Analytics

---

## Let's Connect

I'm always interested in discussing QA automation strategy, test architecture, AI-assisted testing workflows, and continuous improvement opportunities. Feel free to reach out!

**Last Updated:** October 2026
