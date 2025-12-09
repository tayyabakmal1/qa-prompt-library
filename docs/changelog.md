# Changelog

All notable changes to the QA Prompt Library will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.0] - 2025-12-05

### Added
- Initial release of QA Prompt Library
- Manual QA prompts:
  - Test case creation (functional, regression, edge cases)
  - Bug reporting (defect description, reproduction steps, root cause analysis)
  - Test planning (strategy, plans, risk analysis)
  - Testing checklists (UI, API, mobile)
- Automation QA prompts:
  - Test script generation (Selenium, Playwright, Cypress)
  - API automation (Postman, REST Assured, Newman)
  - Framework design prompts
  - CI/CD integration prompts
- AI-Assisted QA prompts:
  - Test data generation
  - Risk analysis
  - Exploratory testing
  - Release quality assessment
- Examples and documentation
- Contribution guidelines
- README with quick start guide

### Changed
- N/A (Initial release)

### Deprecated
- N/A (Initial release)

### Removed
- N/A (Initial release)

### Fixed
- N/A (Initial release)

### Security
- N/A (Initial release)

---

## [1.1.0] - 2025-12-05

### Added
- **Mobile Testing Section**: Comprehensive mobile testing resources
  - Mobile test scenarios prompts (app lifecycle, permissions, gestures, network, notifications)
  - Mobile automation prompts (Appium scripts, cross-platform testing, gestures)
  - Mobile testing checklists (pre-release, security, performance, cross-platform)
- **Cursor AI Mobile Roles**:
  - Appium role for mobile automation (iOS and Android)
  - Mobile testing strategy role (device coverage, network testing, platform-specific scenarios)
  - Mobile performance testing role (launch time, memory, battery, FPS measurement)
- **Examples**:
  - Mobile testing example for e-commerce app with complete Page Object Model
- **Documentation Updates**:
  - Updated main README with mobile testing section
  - Updated cursor-ai README with mobile roles
  - Added mobile testing to library structure

### Changed
- Enhanced README structure to include mobile testing category
- Expanded Cursor AI roles section with mobile-specific expertise

---

## [1.2.0] - 2025-12-05

### Added
- **Automation QA - Contract Testing**:
  - Pact consumer-driven contract testing prompts (consumer/provider tests, JavaScript, Java, Python examples)
  - Spring Cloud Contract prompts (Groovy DSL, producer/provider setup, Maven/Gradle config)
  - Consumer-driven contract principles and workflows (contract evolution, versioning, multi-consumer management)

- **Automation QA - Load Testing**:
  - JMeter load testing prompts (test plans, CLI execution, CSV parameterization, performance patterns)
  - Gatling load testing prompts (Scala/Kotlin simulations, load injection strategies, advanced scenarios)
  - K6 load testing prompts (JavaScript tests, cloud execution, WebSocket/browser testing)

- **Automation QA - Test Reporting**:
  - Extent Reports prompts (Java/Python/JavaScript integration, step logging, customization)
  - Allure Reports prompts (annotations, attachments, BDD integration, CLI commands)
  - Custom reporting prompts (HTML generators, Slack notifications, database storage, real-time dashboards)

- **Automation QA - Parallel Execution**:
  - TestNG parallel execution prompts (thread-safe design, parallel methods/classes/tests)
  - Selenium Grid prompts (Docker Compose setup, RemoteWebDriver, hub/node configuration)
  - Cloud execution prompts (BrowserStack, Sauce Labs, LambdaTest parallel testing)

- **AI-Assisted QA - Advanced Features**:
  - AI-powered test maintenance (self-healing locators, auto-refactoring, update detection)
  - Self-healing test scripts (visual AI element detection, DOM structure learning, OCR)
  - Intelligent test selection (risk-based selection, ML predictive failure analysis, code change impact)
  - Defect prediction models (ML-based defect probability, bug pattern recognition, quality metrics)

- **Cursor AI Roles - Testing Frameworks**:
  - TestNG Role: Annotations, data providers, parallel execution, listeners
  - JUnit Role: JUnit 5 features, parameterized tests, nested tests, extensions
  - pytest Role: Fixtures, parametrization, markers, plugins, conftest.py

- **Cursor AI Roles - API Testing**:
  - REST Assured Role: BDD syntax, authentication, POJO serialization, specifications
  - Karate DSL Role: Gherkin syntax, data-driven tests, parallel execution
  - GraphQL Testing Role: Queries, mutations, subscriptions, schema validation

- **Cursor AI Roles - Infrastructure**:
  - Docker Testing Role: Testcontainers, Docker Compose, container testing strategies
  - Kubernetes Testing Role: Deployment testing, service validation, Helm tests, chaos engineering

### Changed
- Enhanced README structure with categorized Cursor AI roles (Web, Mobile, Frameworks, API, Design Patterns, Infrastructure)
- Expanded Automation QA section with 4 new major categories
- Expanded AI-Assisted QA section with 4 advanced AI/ML features

---

## [1.3.0] - 2025-12-09

### Added
- **Automation QA - Database Testing**:
  - SQL testing prompts (schema validation, stored procedures, transactions, SQL injection, performance)
  - NoSQL testing prompts (MongoDB, Redis, Cassandra, DynamoDB, Elasticsearch, Neo4j)
  - Data migration testing prompts (ETL, schema mapping, reconciliation, rollback, zero-downtime)

- **Automation QA - Security Testing**:
  - OWASP Top 10 testing prompts (A01-A10 comprehensive coverage)
  - Penetration testing prompts (reconnaissance, vulnerability assessment, exploitation, post-exploitation)
  - Vulnerability assessment prompts (network, web, database, OS, cloud, wireless, IoT, MDM)

- **Automation QA - Accessibility Testing**:
  - WCAG 2.1 compliance prompts (Level A, AA, AAA success criteria)
  - Screen reader testing prompts (NVDA, JAWS, VoiceOver, TalkBack, ARIA implementation)
  - Keyboard navigation testing prompts (focus management, skip links, forms, modals, custom components)

- **Automation QA - Cloud Testing**:
  - AWS testing prompts (EC2, S3, Lambda, RDS, API Gateway, DynamoDB, ECS/EKS, security, Well-Architected Framework)
  - Azure testing prompts (VMs, App Service, Functions, SQL Database, Storage, AKS, DevOps, Cosmos DB, security)
  - GCP testing prompts (Compute Engine, Cloud Storage, Cloud Functions, Cloud SQL, GKE, Pub/Sub, Cloud Run, BigQuery)

### Changed
- Enhanced README structure with new testing categories
- Expanded Automation QA section with 4 major new categories (12 new prompt files)

---

## Template for Future Releases

## [Unreleased]

### Added
- New features or prompts

### Changed
- Changes to existing functionality

### Deprecated
- Features that will be removed in upcoming releases

### Removed
- Features that have been removed

### Fixed
- Bug fixes

### Security
- Security improvements or fixes
