# Prompt Writing Guide

## Introduction

This guide will help you create effective, high-quality prompts for the QA Prompt Library. Whether you're contributing new prompts or improving existing ones, following these guidelines ensures consistency and maximum value for users.

## What Makes a Great QA Prompt?

A great QA prompt is:
- **Specific**: Clearly defines what the AI should generate
- **Structured**: Organized with clear sections and placeholders
- **Reusable**: Can be adapted to multiple scenarios
- **Complete**: Includes all necessary context and requirements
- **Validated**: Tested with AI tools and produces quality output

## The Anatomy of a Quality Prompt

### 1. Clear Objective
Start with a clear statement of what the prompt achieves.

**Good Example**:
```
Generate comprehensive test cases for a login feature including happy path, 
error scenarios, and security validations.
```

**Poor Example**:
```
Make some tests for login.
```

### 2. Structured Format
Use a consistent structure with clear sections.

**Good Example**:
```
Feature: [FEATURE_NAME]
Context: [BUSINESS_CONTEXT]
Requirements:
- [REQUIREMENT_1]
- [REQUIREMENT_2]

Generate test cases covering:
- Happy path scenarios
- Error handling
- Edge cases
```

**Poor Example**:
```
Test this feature: [FEATURE_NAME]
```

### 3. Meaningful Placeholders
Use descriptive placeholders in [BRACKETS] that clearly indicate what should be filled in.

**Good Placeholders**:
- `[FEATURE_NAME]` - Clear and specific
- `[API_ENDPOINT_URL]` - Describes exactly what's needed
- `[EXPECTED_RESPONSE_CODE]` - Self-explanatory

**Poor Placeholders**:
- `[X]` - Too vague
- `[THING]` - Not descriptive
- `[DATA]` - Ambiguous

### 4. Context and Constraints
Provide enough context for the AI to generate relevant output.

**Good Context**:
```
System: E-commerce checkout flow
Technology: React frontend, Node.js backend
Authentication: JWT tokens
Payment Gateway: Stripe integration
```

**Poor Context**:
```
Web application
```

## Prompt Writing Techniques

### Technique 1: The Sandwich Method
Structure your prompt in three layers:

1. **Top Bun**: Context and objective
2. **Filling**: Specific requirements and details
3. **Bottom Bun**: Expected output format

**Example**:
```
[CONTEXT: What system/feature this is about]

Requirements:
- [Detailed requirement 1]
- [Detailed requirement 2]

[OUTPUT: What format the response should be in]
```

### Technique 2: The Checklist Approach
Use checklists to ensure comprehensive coverage.

**Example**:
```
Generate test cases ensuring coverage of:
- [ ] All input fields validated
- [ ] Error messages are user-friendly
- [ ] Success scenarios work as expected
- [ ] Edge cases are handled
- [ ] Security considerations addressed
```

### Technique 3: The Example-Driven Method
Provide examples to guide the AI's output.

**Example**:
```
Generate API test cases similar to this example:

Test Case: Verify successful user creation
- Endpoint: POST /api/users
- Payload: {"name": "John", "email": "john@example.com"}
- Expected: 201 Created, user object returned

Now generate test cases for: [YOUR_SCENARIO]
```

### Technique 4: The Constraint-Based Method
Explicitly state what to include and exclude.

**Example**:
```
Generate Selenium test code with these constraints:

Include:
- Page Object Model pattern
- Explicit waits (no Thread.sleep)
- Meaningful assertions
- Exception handling

Exclude:
- Hard-coded test data
- Absolute XPath locators
- Browser-specific code
```

## Common Pitfalls to Avoid

### ❌ Pitfall 1: Too Vague
**Problem**: "Create some test cases"
**Solution**: "Create 10 functional test cases for user registration covering valid inputs, invalid inputs, and boundary conditions"

### ❌ Pitfall 2: Too Prescriptive
**Problem**: Providing exact code instead of letting AI generate
**Solution**: Describe requirements and patterns, let AI create the implementation

### ❌ Pitfall 3: Missing Context
**Problem**: "Test the API"
**Solution**: "Test the REST API for user management with endpoints for CRUD operations, using JWT authentication"

### ❌ Pitfall 4: Unclear Expected Output
**Problem**: Not specifying what format the output should be
**Solution**: "Provide output as a table with columns: Test ID, Description, Steps, Expected Result"

### ❌ Pitfall 5: No Examples
**Problem**: Abstract descriptions without concrete examples
**Solution**: Include at least one filled example showing proper usage

## Prompt Templates by Category

### Template 1: Test Case Generation
```
Generate test cases for [FEATURE_NAME]:

Feature Description: [DESCRIBE_FEATURE]
User Story: [USER_STORY]
Acceptance Criteria:
- [CRITERIA_1]
- [CRITERIA_2]

Create test cases covering:
- Happy path scenarios
- Error scenarios
- Edge cases
- [SPECIFIC_REQUIREMENT]

Format: [TABLE/GHERKIN/STRUCTURED_TEXT]
```

### Template 2: Code Generation
```
Generate [FRAMEWORK_NAME] test automation code for:

Scenario: [TEST_SCENARIO]
Technology Stack: [TECH_STACK]
Design Pattern: [PATTERN_NAME]

Requirements:
- [REQUIREMENT_1]
- [REQUIREMENT_2]

Code should include:
- [SPECIFIC_ELEMENT_1]
- [SPECIFIC_ELEMENT_2]

Language: [PROGRAMMING_LANGUAGE]
```

### Template 3: Analysis and Review
```
Analyze the following [ARTIFACT_TYPE]:

[PASTE_ARTIFACT_HERE]

Provide analysis on:
- [ANALYSIS_ASPECT_1]
- [ANALYSIS_ASPECT_2]
- [ANALYSIS_ASPECT_3]

Include:
- Identified issues
- Recommendations
- Best practice violations
- Improvement suggestions
```

## Testing Your Prompts

Before submitting a prompt, test it with at least one AI tool:

### Testing Checklist
- [ ] Prompt generates relevant output
- [ ] Output quality is high and useful
- [ ] Placeholders are clear and well-explained
- [ ] Examples work as expected
- [ ] Output matches expected format
- [ ] No ambiguous instructions
- [ ] Works with multiple AI tools (ChatGPT, Claude, Gemini)

### Testing Process
1. **Fill in placeholders** with realistic test data
2. **Run the prompt** with your preferred AI tool
3. **Evaluate the output** for quality and relevance
4. **Iterate and refine** based on results
5. **Test with different scenarios** to ensure versatility

## Optimizing for Different AI Tools

### ChatGPT Optimization
- Use clear, conversational language
- Break complex prompts into steps
- Specify output format explicitly

### Claude Optimization
- Provide detailed context upfront
- Use structured formats (XML-like tags work well)
- Be explicit about constraints

### Gemini Optimization
- Use clear, direct instructions
- Include examples for complex tasks
- Specify technical details precisely

### GitHub Copilot Optimization
- Use code comments as prompts
- Be specific about function signatures
- Include type hints and annotations

## Advanced Techniques

### Chain-of-Thought Prompting
Guide the AI through reasoning steps:

```
Let's approach this step-by-step:
1. First, identify all input fields
2. Then, determine validation rules for each
3. Next, create positive test cases
4. Finally, create negative test cases

[YOUR_SCENARIO]
```

### Few-Shot Learning
Provide multiple examples:

```
Example 1: [EXAMPLE_1]
Example 2: [EXAMPLE_2]
Example 3: [EXAMPLE_3]

Now create similar output for: [YOUR_SCENARIO]
```

### Role-Based Prompting
Assign a role to the AI:

```
You are a senior QA automation engineer with 10 years of experience 
in Selenium and Java. Create a robust test framework for...
```

## Prompt Versioning

### When to Update a Prompt
- User feedback indicates improvements needed
- New framework features become available
- Better techniques are discovered
- Output quality can be improved

### Version Numbering
- **1.0**: Initial version
- **1.1, 1.2**: Minor improvements, clarifications
- **2.0**: Major restructuring or significant changes

### Changelog
Document changes in the prompt file:
```markdown
## Changelog
- **v1.2** (2026-01-01): Added examples for API testing
- **v1.1** (2025-12-15): Clarified placeholder descriptions
- **v1.0** (2025-12-01): Initial version
```

## Quality Standards

Every prompt should meet these standards:

### Content Quality
- [ ] Clear objective stated
- [ ] Structured format used
- [ ] Placeholders are descriptive
- [ ] At least one example provided
- [ ] Expected output described

### Technical Quality
- [ ] Tested with AI tools
- [ ] Produces useful output
- [ ] Follows best practices
- [ ] No technical errors

### Documentation Quality
- [ ] Metadata complete (difficulty, tags, version)
- [ ] Related prompts linked
- [ ] Additional resources provided
- [ ] Tips and troubleshooting included

## Examples of Excellent Prompts

### Example 1: Beginner-Friendly Prompt
```markdown
# API Test Case Generation - Beginner

## Objective
Generate comprehensive test cases for REST API endpoints with clear 
descriptions and expected results.

## Prompt
Create test cases for the following API endpoint:

Endpoint: [METHOD] [ENDPOINT_URL]
Description: [WHAT_THIS_ENDPOINT_DOES]
Authentication: [AUTH_TYPE]

Request Body (if applicable):
[JSON_STRUCTURE]

Generate test cases for:
1. Successful request (200 OK)
2. Invalid authentication (401)
3. Missing required fields (400)
4. Invalid data types (400)
5. Resource not found (404)

For each test case, provide:
- Test case ID
- Description
- Request details
- Expected response code
- Expected response body
```

### Example 2: Advanced Technical Prompt
```markdown
# Selenium Page Object Model - Advanced

## Objective
Generate a complete POM implementation with advanced patterns including 
fluent interfaces, custom expected conditions, and retry logic.

## Prompt
Create a Page Object Model implementation for:

Page: [PAGE_NAME]
URL: [PAGE_URL]
Elements: [LIST_KEY_ELEMENTS]

Requirements:
- Fluent interface pattern for method chaining
- Custom ExpectedConditions for complex waits
- Retry mechanism for flaky elements
- Logging for all interactions
- Screenshot capture on failures

Language: [Java/Python/JavaScript]
Framework: Selenium 4.x
```

## Resources

- [Official Prompt Engineering Guide](https://platform.openai.com/docs/guides/prompt-engineering)
- [Anthropic's Prompt Design Guide](https://docs.anthropic.com/claude/docs/prompt-design)
- [Google's Prompting Best Practices](https://ai.google.dev/docs/prompt_best_practices)

## Getting Help

- Review existing prompts for inspiration
- Check the [contribution guidelines](contribution-guidelines.md)
- Open an issue for questions
- Join community discussions

---

**Remember**: Great prompts are iterative. Start with a solid foundation and refine based on real-world usage and feedback.
