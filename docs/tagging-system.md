# Tagging System Guide

## Overview

The QA Prompt Library uses a comprehensive tagging system to help users quickly discover relevant prompts. Tags are used in the metadata section of each prompt to categorize and classify content.

## Tag Categories

### 1. Complexity Tags
Indicate the skill level required to use the prompt effectively.

- `#beginner` - Basic prompts for newcomers to testing or the framework
- `#intermediate` - Standard prompts for professionals with basic experience
- `#advanced` - Complex scenarios, edge cases, and expert-level content

**Usage Guidelines**:
- Use `#beginner` for prompts with step-by-step guidance and explanations
- Use `#intermediate` for balanced prompts assuming basic knowledge
- Use `#advanced` for concise prompts assuming deep expertise

### 2. Domain Tags
Specify the testing domain or platform.

- `#web` - Web application testing
- `#mobile` - Mobile application testing (iOS/Android)
- `#api` - API and service testing
- `#desktop` - Desktop application testing
- `#cloud` - Cloud-based testing
- `#database` - Database testing
- `#embedded` - Embedded systems testing

### 3. Testing Type Tags
Classify by testing methodology or type.

- `#functional` - Functional testing
- `#regression` - Regression testing
- `#smoke` - Smoke testing
- `#integration` - Integration testing
- `#e2e` - End-to-end testing
- `#unit` - Unit testing
- `#performance` - Performance and load testing
- `#security` - Security testing
- `#accessibility` - Accessibility testing
- `#visual` - Visual regression testing
- `#exploratory` - Exploratory testing
- `#usability` - Usability testing
- `#contract` - Contract testing

### 4. Framework Tags
Identify specific testing frameworks or tools.

**Web Automation**:
- `#selenium` - Selenium WebDriver
- `#playwright` - Playwright
- `#cypress` - Cypress
- `#puppeteer` - Puppeteer
- `#webdriverio` - WebDriverIO

**Mobile Automation**:
- `#appium` - Appium
- `#xcuitest` - XCUITest (iOS)
- `#espresso` - Espresso (Android)
- `#detox` - Detox (React Native)

**API Testing**:
- `#postman` - Postman
- `#rest-assured` - REST Assured
- `#karate` - Karate DSL
- `#supertest` - SuperTest
- `#graphql` - GraphQL testing

**Test Frameworks**:
- `#testng` - TestNG
- `#junit` - JUnit
- `#pytest` - pytest
- `#mocha` - Mocha
- `#jest` - Jest
- `#nunit` - NUnit

**Performance Tools**:
- `#jmeter` - Apache JMeter
- `#gatling` - Gatling
- `#k6` - k6
- `#locust` - Locust

### 5. Language Tags
Specify programming languages used.

- `#java` - Java
- `#python` - Python
- `#javascript` - JavaScript
- `#typescript` - TypeScript
- `#csharp` - C#
- `#ruby` - Ruby
- `#go` - Go
- `#kotlin` - Kotlin

### 6. Use Case Tags
Describe the specific use case or activity.

- `#ci-cd` - CI/CD integration
- `#debugging` - Debugging and troubleshooting
- `#refactoring` - Code refactoring
- `#code-review` - Code review
- `#documentation` - Documentation generation
- `#test-data` - Test data generation
- `#reporting` - Test reporting
- `#maintenance` - Test maintenance
- `#framework-design` - Framework architecture

### 7. Design Pattern Tags
Identify design patterns used.

- `#pom` - Page Object Model
- `#bdd` - Behavior-Driven Development
- `#data-driven` - Data-driven testing
- `#keyword-driven` - Keyword-driven testing
- `#screenplay` - Screenplay pattern

### 8. AI Tool Tags
Specify which AI tools work best with the prompt.

- `#chatgpt` - Optimized for ChatGPT
- `#claude` - Optimized for Claude
- `#gemini` - Optimized for Google Gemini
- `#copilot` - Optimized for GitHub Copilot
- `#cursor` - Optimized for Cursor AI

## Tag Usage Best Practices

### 1. Tag Selection
- **Use 3-6 tags per prompt** - Enough for discoverability, not overwhelming
- **Choose relevant tags** - Only use tags that accurately describe the prompt
- **Include at least one from each category** when applicable:
  - One complexity tag (required)
  - One domain tag (if applicable)
  - One testing type tag (required)
  - Framework/tool tags (as needed)

### 2. Tag Formatting
- Always use lowercase
- Use hyphens for multi-word tags: `#rest-assured`, `#data-driven`
- Prefix with `#` in the metadata section
- Separate tags with spaces

**Example**:
```markdown
**Tags**: #intermediate #web #functional #selenium #java #pom
```

### 3. Tag Consistency
- Use existing tags whenever possible
- Check the tag index before creating new tags
- Maintain consistent naming across similar prompts

## Tag Combinations for Discovery

### Common Combinations

**Beginner Web Automation**:
```
#beginner #web #functional #selenium #java
```

**Advanced API Testing**:
```
#advanced #api #integration #rest-assured #java #ci-cd
```

**Mobile Performance Testing**:
```
#intermediate #mobile #performance #appium #python
```

**E2E Testing with BDD**:
```
#intermediate #web #e2e #cypress #javascript #bdd
```

## Tag Index

### Quick Reference
Use this index to find all prompts with specific tags:

**By Complexity**:
- [All Beginner Prompts](#) - `#beginner`
- [All Intermediate Prompts](#) - `#intermediate`
- [All Advanced Prompts](#) - `#advanced`

**By Domain**:
- [Web Testing](#) - `#web`
- [Mobile Testing](#) - `#mobile`
- [API Testing](#) - `#api`

**By Framework**:
- [Selenium](#) - `#selenium`
- [Playwright](#) - `#playwright`
- [Cypress](#) - `#cypress`
- [Appium](#) - `#appium`

## Adding New Tags

### When to Create a New Tag
Create a new tag when:
- No existing tag accurately describes the content
- A new framework/tool is added to the library
- A new testing methodology emerges

### How to Add a New Tag
1. Check this guide to ensure the tag doesn't exist
2. Follow naming conventions (lowercase, hyphens)
3. Add the tag to the appropriate category in this guide
4. Update the tag index
5. Use the tag in your prompt metadata

### Tag Proposal Process
For major new tag categories:
1. Open an issue describing the new tag
2. Explain the use case and need
3. Get community feedback
4. Update this guide once approved

## Examples

### Example 1: Selenium Test Generation Prompt
```markdown
**Tags**: #intermediate #web #functional #selenium #java #pom #test-data
```

**Rationale**:
- `#intermediate` - Requires basic Selenium knowledge
- `#web` - Web application testing
- `#functional` - Functional test generation
- `#selenium` - Uses Selenium WebDriver
- `#java` - Java language
- `#pom` - Uses Page Object Model
- `#test-data` - Includes test data generation

### Example 2: Mobile Accessibility Testing
```markdown
**Tags**: #beginner #mobile #accessibility #appium #python
```

**Rationale**:
- `#beginner` - Step-by-step guidance provided
- `#mobile` - Mobile testing
- `#accessibility` - Accessibility focus
- `#appium` - Uses Appium framework
- `#python` - Python language

### Example 3: Advanced API Contract Testing
```markdown
**Tags**: #advanced #api #contract #pact #javascript #ci-cd #microservices
```

**Rationale**:
- `#advanced` - Complex contract testing scenarios
- `#api` - API testing
- `#contract` - Contract testing methodology
- `#pact` - Uses Pact framework
- `#javascript` - JavaScript language
- `#ci-cd` - CI/CD integration included
- `#microservices` - Microservices architecture

## Searching by Tags

### In GitHub
Use GitHub's search functionality:
```
#selenium #intermediate path:automation-qa/
```

### In Your IDE
Use find-in-files with tag patterns:
```
Search: "Tags.*#selenium.*#java"
```

### Future Enhancements
- Web-based tag filter interface
- CLI tool for tag-based search
- VS Code extension with tag navigation

---

**Remember**: Tags are for discovery. Use them thoughtfully to help users find exactly what they need quickly.
