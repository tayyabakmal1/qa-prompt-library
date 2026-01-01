# QA Prompt Library - Complete Index

> **Quick Navigation**: Use `Ctrl+F` (or `Cmd+F` on Mac) to search for specific keywords, frameworks, or tags.

## How to Use This Index

This index provides a complete, searchable catalog of all prompts in the library. Each entry includes:
- **Prompt Name** with link to the file
- **Difficulty Level** (🟢 Beginner | 🟡 Intermediate | 🔴 Advanced)
- **Category** 
- **Key Tags**
- **Brief Description**

---

## Filter by Difficulty

- [🟢 Beginner Prompts](#beginner-prompts)
- [🟡 Intermediate Prompts](#intermediate-prompts)
- [🔴 Advanced Prompts](#advanced-prompts)

## Filter by Category

- [Manual QA](#manual-qa-prompts)
- [Automation QA](#automation-qa-prompts)
- [AI-Assisted QA](#ai-assisted-qa-prompts)
- [Mobile Testing](#mobile-testing-prompts)
- [Cursor AI Roles](#cursor-ai-roles)

## Filter by Framework

- [Selenium](#selenium) | [Playwright](#playwright) | [Cypress](#cypress)
- [Appium](#appium) | [Postman](#postman) | [REST Assured](#rest-assured)
- [JMeter](#jmeter) | [Gatling](#gatling) | [K6](#k6)

---

## Manual QA Prompts

### Test Case Creation

| Prompt | Difficulty | Tags | Description |
|--------|-----------|------|-------------|
| [Functional Test Cases](manual-qa/test-case-creation/functional-prompts.md) | 🟡 | `#intermediate` `#functional` `#test-cases` | Generate comprehensive functional test cases for features |
| [Edge Case Test Cases](manual-qa/test-case-creation/edge-case-prompts.md) | 🟡 | `#intermediate` `#edge-cases` `#test-cases` | Create test cases for edge cases and boundary conditions |
| [Regression Test Cases](manual-qa/test-case-creation/regression-prompts.md) | 🟡 | `#intermediate` `#regression` `#test-cases` | Generate regression test suites |

### Bug Reporting

| Prompt | Difficulty | Tags | Description |
|--------|-----------|------|-------------|
| [Bug Report Templates](manual-qa/bug-reporting/) | 🟢 | `#beginner` `#bug-reporting` `#documentation` | Create detailed bug reports with reproduction steps |
| [Root Cause Analysis](manual-qa/bug-reporting/) | 🔴 | `#advanced` `#debugging` `#analysis` | Analyze bugs for root causes |

### Test Planning

| Prompt | Difficulty | Tags | Description |
|--------|-----------|------|-------------|
| [Test Strategy](manual-qa/test-planning/) | 🟡 | `#intermediate` `#planning` `#strategy` | Create comprehensive test strategies |
| [Risk Analysis](manual-qa/test-planning/) | 🔴 | `#advanced` `#risk-analysis` `#planning` | Perform risk-based test planning |

### Checklists

| Prompt | Difficulty | Tags | Description |
|--------|-----------|------|-------------|
| [UI Testing Checklist](manual-qa/checklist-prompts/) | 🟢 | `#beginner` `#ui` `#checklist` | Comprehensive UI testing checklist |
| [API Testing Checklist](manual-qa/checklist-prompts/) | 🟢 | `#beginner` `#api` `#checklist` | API testing verification checklist |
| [Mobile Testing Checklist](manual-qa/checklist-prompts/) | 🟡 | `#intermediate` `#mobile` `#checklist` | Mobile app testing checklist |

### Exploratory Testing (NEW)

| Prompt | Difficulty | Tags | Description |
|--------|-----------|------|-------------|
| [Exploratory Testing](manual-qa/exploratory-testing/exploratory-testing-prompts.md) | 🟡 | `#intermediate` `#exploratory` `#session-based` `#charter` | Session-based testing charters and bug hunting strategies |

---

## Automation QA Prompts

### Web Automation

#### Selenium
| Prompt | Difficulty | Tags | Description |
|--------|-----------|------|-------------|
| [Selenium Test Scripts](automation-qa/test-script-generation/) | 🟡 | `#selenium` `#web` `#java` | Generate Selenium WebDriver test scripts |

#### Playwright
| Prompt | Difficulty | Tags | Description |
|--------|-----------|------|-------------|
| [Playwright Automation](automation-qa/playwright-automation/) | 🟡 | `#playwright` `#web` `#javascript` | Create Playwright test automation |

#### Cypress
| Prompt | Difficulty | Tags | Description |
|--------|-----------|------|-------------|
| [Cypress E2E Tests](automation-qa/test-script-generation/) | 🟡 | `#cypress` `#e2e` `#javascript` | Generate Cypress end-to-end tests |

### API Automation

| Prompt | Difficulty | Tags | Description |
|--------|-----------|------|-------------|
| [API Testing - Beginner](automation-qa/api-automation/api-testing-beginner.md) | 🟢 | `#beginner` `#api` `#postman` `#rest` | Beginner-friendly API testing with Postman |
| [Postman Collections](automation-qa/api-automation/postman-prompts.md) | 🟡 | `#postman` `#api` `#intermediate` | Create Postman test collections |
| [API Testing - Advanced](automation-qa/api-automation/api-testing-advanced.md) | 🔴 | `#advanced` `#api` `#contract` `#security` | Advanced API patterns: contract, security, performance |
| [REST Assured Tests](automation-qa/api-automation/) | 🟡 | `#rest-assured` `#api` `#java` | Generate REST Assured API tests |
| [Newman Scripts](automation-qa/api-automation/) | 🟡 | `#newman` `#api` `#ci-cd` | Create Newman CLI test scripts |

### Framework Design

| Prompt | Difficulty | Tags | Description |
|--------|-----------|------|-------------|
| [Framework Architecture](automation-qa/framework-design/) | 🔴 | `#advanced` `#framework` `#architecture` | Design test automation frameworks |
| [Page Object Model](automation-qa/framework-design/) | 🟡 | `#pom` `#design-pattern` `#web` | Implement Page Object Model |

### CI/CD Integration

| Prompt | Difficulty | Tags | Description |
|--------|-----------|------|-------------|
| [Jenkins Pipeline](automation-qa/ci-cd/) | 🟡 | `#jenkins` `#ci-cd` `#pipeline` | Create Jenkins test pipelines |
| [GitHub Actions](automation-qa/ci-cd/) | 🟡 | `#github-actions` `#ci-cd` `#automation` | Set up GitHub Actions workflows |
| [GitLab CI](automation-qa/ci-cd/) | 🟡 | `#gitlab` `#ci-cd` `#pipeline` | Configure GitLab CI/CD pipelines |

### Performance Testing

| Prompt | Difficulty | Tags | Description |
|--------|-----------|------|-------------|
| [JMeter Tests](automation-qa/load-testing/) | 🟡 | `#jmeter` `#performance` `#load-testing` | Create JMeter load tests |
| [Gatling Scenarios](automation-qa/load-testing/) | 🔴 | `#gatling` `#performance` `#scala` | Generate Gatling performance tests |
| [K6 Scripts](automation-qa/load-testing/) | 🟡 | `#k6` `#performance` `#javascript` | Write K6 performance scripts |

### Contract Testing

| Prompt | Difficulty | Tags | Description |
|--------|-----------|------|-------------|
| [Pact Contracts](automation-qa/contract-testing/) | 🔴 | `#pact` `#contract` `#microservices` | Create Pact consumer contracts |
| [Spring Cloud Contract](automation-qa/contract-testing/) | 🔴 | `#spring` `#contract` `#java` | Implement Spring Cloud Contract tests |

### Security Testing

| Prompt | Difficulty | Tags | Description |
|--------|-----------|------|-------------|
| [OWASP Top 10](automation-qa/security-testing/) | 🔴 | `#security` `#owasp` `#vulnerabilities` | Test for OWASP Top 10 vulnerabilities |
| [Penetration Testing](automation-qa/security-testing/) | 🔴 | `#security` `#pentesting` `#advanced` | Create penetration test scenarios |

### Accessibility Testing

| Prompt | Difficulty | Tags | Description |
|--------|-----------|------|-------------|
| [WCAG Compliance](automation-qa/accessibility-testing/) | 🟡 | `#accessibility` `#wcag` `#compliance` | Test for WCAG accessibility standards |
| [Screen Reader Testing](automation-qa/accessibility-testing/) | 🟡 | `#accessibility` `#screen-reader` `#a11y` | Create screen reader test scenarios |

### Database Testing

| Prompt | Difficulty | Tags | Description |
|--------|-----------|------|-------------|
| [SQL Testing](automation-qa/database-testing/) | 🟡 | `#database` `#sql` `#data-validation` | Generate SQL database tests |
| [NoSQL Testing](automation-qa/database-testing/) | 🟡 | `#database` `#nosql` `#mongodb` | Create NoSQL database tests |

### Cloud Testing

| Prompt | Difficulty | Tags | Description |
|--------|-----------|------|-------------|
| [AWS Testing](automation-qa/cloud-testing/) | 🔴 | `#cloud` `#aws` `#infrastructure` | Test AWS cloud services |
| [Azure Testing](automation-qa/cloud-testing/) | 🔴 | `#cloud` `#azure` `#infrastructure` | Test Azure cloud services |
| [GCP Testing](automation-qa/cloud-testing/) | 🔴 | `#cloud` `#gcp` `#infrastructure` | Test Google Cloud Platform services |

### Visual Testing (NEW)

| Prompt | Difficulty | Tags | Description |
|--------|-----------|------|-------------|
| [Visual Regression Testing](automation-qa/visual-testing/visual-testing-prompts.md) | 🟡 | `#intermediate` `#visual` `#regression` `#ui` | Screenshot comparison and visual testing with Percy, Applitools |

### E2E Testing (NEW)

| Prompt | Difficulty | Tags | Description |
|--------|-----------|------|-------------|
| [End-to-End Testing](automation-qa/e2e-testing/e2e-testing-prompts.md) | 🔴 | `#advanced` `#e2e` `#integration` `#user-journey` | Complete user journey and multi-system integration tests |

### Quick Reference (NEW)

| Prompt | Difficulty | Tags | Description |
|--------|-----------|------|-------------|
| [Selenium Quick Reference](automation-qa/web-automation/selenium-quick-reference.md) | 🟡 | `#intermediate` `#selenium` `#quick-reference` `#cheat-sheet` | Quick lookup guide for common Selenium operations |

---

## AI-Assisted QA Prompts

| Prompt | Difficulty | Tags | Description |
|--------|-----------|------|-------------|
| [Test Data Generation](ai-assisted-qa/test-data-generation-prompts.md) | 🟡 | `#ai` `#test-data` `#generation` | Generate realistic test data using AI |
| [Risk Analysis](ai-assisted-qa/risk-analysis-prompts.md) | 🔴 | `#ai` `#risk-analysis` `#prediction` | AI-powered risk analysis |
| [Exploratory Testing](ai-assisted-qa/exploratory-testing-prompts.md) | 🟡 | `#ai` `#exploratory` `#testing` | AI-guided exploratory testing |
| [Release Quality Assessment](ai-assisted-qa/release-quality-prompts.md) | 🔴 | `#ai` `#quality` `#assessment` | Assess release quality with AI |
| [AI-Powered Test Maintenance](ai-assisted-qa/ai-powered-test-maintenance.md) | 🔴 | `#ai` `#maintenance` `#self-healing` | Self-healing test scripts |
| [Intelligent Test Selection](ai-assisted-qa/intelligent-test-selection.md) | 🔴 | `#ai` `#test-selection` `#ml` | ML-based test selection |
| [Defect Prediction](ai-assisted-qa/defect-prediction-models.md) | 🔴 | `#ai` `#defect-prediction` `#ml` | Predict defects using ML models |

---

## Mobile Testing Prompts

| Prompt | Difficulty | Tags | Description |
|--------|-----------|------|-------------|
| [Mobile Test Scenarios](mobile-testing/) | 🟡 | `#mobile` `#scenarios` `#testing` | Generate mobile-specific test scenarios |
| [Appium Automation](mobile-testing/) | 🟡 | `#appium` `#mobile` `#automation` | Create Appium test scripts |
| [Mobile Checklists](mobile-testing/) | 🟢 | `#mobile` `#checklist` `#qa` | Comprehensive mobile testing checklists |

---

## Cursor AI Roles

### Web Automation Roles

| Role | Difficulty | Tags | Description |
|------|-----------|------|-------------|
| [Selenium Expert](cursor-ai/selenium-role.md) | 🟡 | `#selenium` `#web` `#automation` | Selenium WebDriver expert guidance |
| [Playwright Expert](cursor-ai/playwright-role.md) | 🟡 | `#playwright` `#web` `#automation` | Playwright automation expert |
| [Cypress Expert](cursor-ai/cypress-role.md) | 🟡 | `#cypress` `#e2e` `#javascript` | Cypress testing expert |

### Mobile Testing Roles

| Role | Difficulty | Tags | Description |
|------|-----------|------|-------------|
| [Appium Expert](cursor-ai/appium-role.md) | 🔴 | `#appium` `#mobile` `#automation` | Appium mobile automation expert |
| [Mobile Testing Expert](cursor-ai/mobile-testing-role.md) | 🟡 | `#mobile` `#testing` `#qa` | Mobile testing specialist |
| [Mobile Performance Expert](cursor-ai/mobile-performance-role.md) | 🔴 | `#mobile` `#performance` `#optimization` | Mobile performance testing expert |

### Framework Roles

| Role | Difficulty | Tags | Description |
|------|-----------|------|-------------|
| [TestNG Expert](cursor-ai/testng-role.md) | 🟡 | `#testng` `#java` `#framework` | TestNG framework expert |
| [JUnit Expert](cursor-ai/junit-role.md) | 🟡 | `#junit` `#java` `#testing` | JUnit testing expert |
| [pytest Expert](cursor-ai/pytest-role.md) | 🟡 | `#pytest` `#python` `#testing` | pytest framework expert |

### API Testing Roles

| Role | Difficulty | Tags | Description |
|------|-----------|------|-------------|
| [REST Assured Expert](cursor-ai/rest-assured-role.md) | 🟡 | `#rest-assured` `#api` `#java` | REST Assured API testing expert |
| [Karate DSL Expert](cursor-ai/karate-dsl-role.md) | 🔴 | `#karate` `#api` `#bdd` | Karate DSL testing expert |
| [GraphQL Expert](cursor-ai/graphql-testing-role.md) | 🔴 | `#graphql` `#api` `#testing` | GraphQL API testing expert |

### Design Pattern Roles

| Role | Difficulty | Tags | Description |
|------|-----------|------|-------------|
| [POM Expert](cursor-ai/pom-role.md) | 🟡 | `#pom` `#design-pattern` `#web` | Page Object Model expert |
| [BDD Expert](cursor-ai/bdd-role.md) | 🟡 | `#bdd` `#gherkin` `#cucumber` | Behavior-Driven Development expert |
| [Data-Driven Expert](cursor-ai/data-driven-role.md) | 🟡 | `#data-driven` `#testing` `#framework` | Data-driven testing expert |
| [Framework Design Expert](cursor-ai/framework-design-role.md) | 🔴 | `#framework` `#architecture` `#design` | Test framework architecture expert |

### Specialized Testing Roles

| Role | Difficulty | Tags | Description |
|------|-----------|------|-------------|
| [Security Testing Expert](cursor-ai/security-testing-role.md) | 🔴 | `#security` `#owasp` `#pentesting` | Security testing specialist |
| [Performance Testing Expert](cursor-ai/performance-testing-role.md) | 🔴 | `#performance` `#load-testing` `#optimization` | Performance testing expert |
| [Accessibility Expert](cursor-ai/accessibility-testing-role.md) | 🟡 | `#accessibility` `#wcag` `#a11y` | Accessibility testing expert |

### Infrastructure Roles

| Role | Difficulty | Tags | Description |
|------|-----------|------|-------------|
| [Docker Testing Expert](cursor-ai/docker-testing-role.md) | 🔴 | `#docker` `#containers` `#testing` | Docker container testing expert |
| [Kubernetes Testing Expert](cursor-ai/kubernetes-testing-role.md) | 🔴 | `#kubernetes` `#cloud` `#testing` | Kubernetes testing expert |

---

## Quick Reference by Tag

### By Complexity
- **🟢 Beginner**: [View all beginner prompts](#beginner-prompts)
- **🟡 Intermediate**: [View all intermediate prompts](#intermediate-prompts)
- **🔴 Advanced**: [View all advanced prompts](#advanced-prompts)

### By Language
- **Java**: Selenium, REST Assured, TestNG, JUnit, Spring Cloud Contract
- **Python**: pytest, Selenium, Appium
- **JavaScript/TypeScript**: Cypress, Playwright, K6, Mocha
- **C#**: NUnit, Selenium

### By Testing Type
- **Functional**: Manual test cases, functional automation
- **API**: Postman, REST Assured, Karate, GraphQL
- **Performance**: JMeter, Gatling, K6
- **Security**: OWASP, penetration testing
- **Mobile**: Appium, mobile-specific scenarios
- **Accessibility**: WCAG, screen reader testing

---

## Recently Added

**Phase 2 Content Enhancement (2026-01-01)**:
- 🆕 [Exploratory Testing](manual-qa/exploratory-testing/exploratory-testing-prompts.md) - Session-based testing
- 🆕 [Visual Testing](automation-qa/visual-testing/visual-testing-prompts.md) - Screenshot comparison
- 🆕 [E2E Testing](automation-qa/e2e-testing/e2e-testing-prompts.md) - User journey validation
- 🆕 [API Testing - Beginner](automation-qa/api-automation/api-testing-beginner.md) - Beginner variant
- 🆕 [API Testing - Advanced](automation-qa/api-automation/api-testing-advanced.md) - Advanced patterns
- 🆕 [Selenium Quick Reference](automation-qa/web-automation/selenium-quick-reference.md) - Quick lookup

---

## Most Popular

*Based on community usage and feedback*

1. [Selenium Test Scripts](automation-qa/test-script-generation/)
2. [Postman Collections](automation-qa/api-automation/postman-prompts.md)
3. [Functional Test Cases](manual-qa/test-case-creation/functional-prompts.md)
4. [Page Object Model](cursor-ai/pom-role.md)
5. [CI/CD Integration](automation-qa/ci-cd/)

---

## Contributing

Found a broken link or want to add a new prompt? See our [contribution guidelines](docs/contribution-guidelines.md).

---

**Last Updated**: 2026-01-01
