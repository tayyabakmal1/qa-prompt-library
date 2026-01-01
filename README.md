# QA Prompt Library 🧪

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](docs/contribution-guidelines.md)
[![Prompts](https://img.shields.io/badge/Prompts-100+-blue.svg)](PROMPT_INDEX.md)

A comprehensive, standardized collection of AI prompts designed to enhance Quality Assurance workflows across manual testing, automation, and AI-assisted testing scenarios.

## 🚀 Quick Start

**New to the library?** Start here:
1. Read the [Quick Start Guide](QUICK_START.md) - 5-minute introduction
2. Browse the [Prompt Index](PROMPT_INDEX.md) to find what you need
3. Check out [Quick Start Examples](#-quick-start-examples)
4. Read the [Prompt Writing Guide](docs/prompt-writing-guide.md) to understand best practices
5. Use our [Templates](templates/) to create your own prompts

**Looking for something specific?**
- 🔍 [Search by Tag](docs/tagging-system.md)
- 📋 [Browse by Category](#-structure)
- 🎯 [Filter by Difficulty](PROMPT_INDEX.md)
- 🤖 [Cursor AI Roles](#cursor-ai-roles)

## 📚 Overview

This library provides ready-to-use prompts for QA professionals to leverage AI tools (like ChatGPT, Claude, Gemini, etc.) to improve testing efficiency, quality, and coverage.

## 🗂️ Structure

> **💡 Tip**: Each category has its own README with detailed information. Click the links below to explore!

### [Manual QA](manual-qa/)
Prompts for manual testing activities.

- **[Test Case Creation](manual-qa/test-case-creation/)**: Functional, regression, and edge case test scenarios
- **[Bug Reporting](manual-qa/bug-reporting/)**: Templates for defect descriptions, reproduction steps, and root cause analysis
- **[Test Planning](manual-qa/test-planning/)**: Strategic prompts for test plans, strategies, and risk analysis
- **[Checklists](manual-qa/checklist-prompts/)**: Comprehensive testing checklists for UI, API, and mobile applications
- **[Exploratory Testing](manual-qa/exploratory-testing/)**: Session-based testing and bug hunting
- **[Usability Testing](manual-qa/usability-testing/)** (NEW): UX evaluation and user testing

### [Automation QA](automation-qa/)
Comprehensive automation prompts for all testing needs.

**Web Automation**:
- **Selenium, Playwright, Cypress** - Modern web automation frameworks

**API Testing**:
- **Postman, REST Assured, Karate DSL** - API automation and validation

**Specialized Testing**:
- **[Contract Testing](automation-qa/contract-testing/)**: Pact, Spring Cloud Contract
- **[Load Testing](automation-qa/load-testing/)**: JMeter, Gatling, K6
- **[Security Testing](automation-qa/security-testing/)**: OWASP Top 10, penetration testing
- **[Accessibility Testing](automation-qa/accessibility-testing/)**: WCAG compliance
- **[Database Testing](automation-qa/database-testing/)**: SQL, NoSQL validation
- **[Cloud Testing](automation-qa/cloud-testing/)**: AWS, Azure, GCP

**Framework & CI/CD**:
- **[Framework Design](automation-qa/framework-design/)**: Architecture and design patterns
- **[CI/CD Integration](automation-qa/ci-cd/)**: Jenkins, GitHub Actions, GitLab CI
- **[Test Reporting](automation-qa/test-reporting/)**: Extent Reports, Allure
- **[Parallel Execution](automation-qa/parallel-execution/)**: TestNG, Selenium Grid, cloud execution

### [AI-Assisted QA](ai-assisted-qa/)
Leverage AI and ML for enhanced testing.

- **Test Data Generation**: Realistic, diverse test data using AI
- **Risk Analysis**: AI-powered risk assessment and prediction
- **Exploratory Testing**: AI-guided exploratory testing strategies
- **Release Quality Assessment**: Assess release readiness
- **AI-Powered Test Maintenance**: Self-healing locators and auto-refactoring
- **Intelligent Test Selection**: ML-based risk analysis and predictive failure detection
- **Defect Prediction Models**: Code quality metrics and bug pattern recognition

### [Mobile Testing](mobile-testing/)
Mobile-specific testing prompts.

- **Test Scenarios**: App lifecycle, permissions, gestures, network conditions
- **Automation**: Appium test script generation and mobile frameworks
- **Checklists**: Pre-release, security, performance checklists
- **Cross-Platform**: iOS and Android testing strategies

### [Specialized Testing](specialized-testing/) (NEW)
Testing for emerging and specialized domains.

- **[Blockchain Testing](specialized-testing/blockchain-testing/)**: Web3, smart contracts, DeFi testing
- **[IoT Testing](specialized-testing/iot-testing/)**: Device connectivity, sensor validation
- **[ML Model Testing](specialized-testing/ml-model-testing/)**: Model accuracy, bias detection
- **[Game Testing](specialized-testing/game-testing/)**: Gameplay, performance, multiplayer

### [Cursor AI Roles](cursor-ai/)
Expert AI roles for framework-specific guidance in your IDE.

**Web Automation**: Selenium, Playwright, Cypress
**Mobile Testing**: Appium, Mobile Testing, Mobile Performance
**Testing Frameworks**: TestNG, JUnit, pytest
**API Testing**: REST Assured, Karate DSL, GraphQL
**Design Patterns**: POM, BDD, Data-Driven, Framework Design
**Specialized**: Security, Performance, Accessibility
**Infrastructure**: Docker, Kubernetes

### [Templates](templates/)
Standardized templates for creating new prompts.

- **[Prompt Template](templates/prompt-template.md)**: Standard structure for all prompts
- **[Role Template](templates/role-template.md)**: Template for Cursor AI roles
- **[Usage Guide](templates/README.md)**: How to use the templates

### [Documentation](docs/)
Comprehensive guides and references.

- **[Prompt Writing Guide](docs/prompt-writing-guide.md)**: Learn to write effective prompts
- **[Tagging System](docs/tagging-system.md)**: Complete tag reference
- **[Contribution Guidelines](docs/contribution-guidelines.md)**: How to contribute
- **[Changelog](docs/changelog.md)**: Version history
- **[Glossary](docs/glossary.md)**: Testing terminology

### [Workflows](workflows/) (NEW)
Practical workflow guides for real-world testing scenarios.

- **[Daily Testing Workflow](workflows/daily-testing-workflow.md)**: Day-to-day testing activities
- **[Sprint Testing Workflow](workflows/sprint-testing-workflow.md)**: 2-week sprint cycle guide
- **[Release Testing Workflow](workflows/release-testing-workflow.md)**: Production release process

### AI Tool Integration Guides (NEW)
Learn how to use this library with popular AI tools.

- **[Using with ChatGPT](docs/using-with-chatgpt.md)**: Complete ChatGPT integration guide
- **[Using with Cursor AI](docs/using-with-cursor.md)**: Cursor AI roles and usage
- **[Using with GitHub Copilot](docs/using-with-copilot.md)**: Copilot integration patterns
- **[Best Practices](docs/best-practices.md)**: QA testing best practices


## 🚀 Quick Start Examples

### Example 1: Generate Selenium Test Code
1. Open [Selenium Role](cursor-ai/selenium-role.md) in Cursor AI
2. Describe your test scenario
3. Get production-ready Selenium code with best practices

### Example 2: Create API Test Cases
1. Browse [Postman Prompts](automation-qa/api-automation/postman-prompts.md)
2. Fill in your API details
3. Generate comprehensive Postman collections

### Example 3: Plan Sprint Testing
1. Use [Test Planning Prompts](manual-qa/test-planning/)
2. Input sprint goals and user stories
3. Get complete test strategy and estimates

## 📖 How to Use

1. **Find Your Prompt**
   - Browse [PROMPT_INDEX.md](PROMPT_INDEX.md) for complete catalog
   - Use category READMEs for focused navigation
   - Search by tags using the [Tagging System](docs/tagging-system.md)

2. **Customize the Prompt**
   - Copy the prompt template
   - Replace [PLACEHOLDERS] with your specific details
   - Add any additional context needed

3. **Use with AI Tools**
   - ChatGPT, Claude, Gemini for general prompts
   - GitHub Copilot, Cursor AI for code generation
   - Paste and run in your preferred AI tool

4. **Refine and Validate**
   - Review AI-generated output
   - Refine prompts for better results
   - Always validate before production use

## 💡 Featured Prompts

- 🌟 [Functional Test Cases](manual-qa/test-case-creation/functional-prompts.md) - Most popular
- 🚀 [Selenium Expert Role](cursor-ai/selenium-role.md) - Highly rated
- 🔥 [Postman API Testing](automation-qa/api-automation/postman-prompts.md) - Frequently used
- ⚡ [AI Test Data Generation](ai-assisted-qa/test-data-generation-prompts.md) - Trending

## 📚 Resources

### For Users
- **[Prompt Index](PROMPT_INDEX.md)** - Complete searchable catalog
- **[Prompt Writing Guide](docs/prompt-writing-guide.md)** - Write effective prompts
- **[Tagging System](docs/tagging-system.md)** - Find prompts by tags
- **[Examples](examples/)** - Real-world usage examples

### For Contributors
- **[Contribution Guidelines](docs/contribution-guidelines.md)** - How to contribute
- **[Templates](templates/)** - Standardized prompt templates
- **[Changelog](docs/changelog.md)** - Recent updates

## 🤝 Contributing

**We welcome contributions!** 🎉

1. Read the [Contribution Guidelines](docs/contribution-guidelines.md)
2. Use our [Templates](templates/) for new prompts
3. Follow the [Prompt Writing Guide](docs/prompt-writing-guide.md)
4. Submit a pull request

See [CONTRIBUTING.md](docs/contribution-guidelines.md) for detailed instructions.

## 📝 License

MIT License - Feel free to use and adapt these prompts for your projects.

## 🔄 Changelog

See [changelog.md](docs/changelog.md) for version history and updates.

---

**Note**: These prompts are templates. Always review and validate AI-generated content before using in production environments.
