Analyze the entire test suite of the project, including both backend and frontend tests, considering the full context of the codebase.

The goal of this analysis is not only to evaluate test coverage but to determine whether the current testing strategy effectively protects the system from meaningful regressions and whether the tests provide value proportional to their maintenance cost.

Use modern software engineering testing principles such as:

* Test Pyramid
* Testing Trophy
* Behavior-driven testing
* Boundary testing
* Contract testing
* Risk-based testing

---

### 1. Test Value Classification

Classify the existing tests into the following categories:

HIGH VALUE
Tests that:

* Protect critical business rules
* Cover core application flows
* Validate important integrations between services or modules
* Ensure correct behavior of critical features
* Would realistically detect production regressions

MEDIUM VALUE
Tests that:

* Validate important but non-critical behavior
* Test important components in isolation
* Verify contracts between modules or services

LOW VALUE
Tests that:

* Validate trivial logic
* Test simple transformations
* Test predictable behavior with little business impact
* Provide minimal protection against real regressions

NEGATIVE VALUE
Tests that:

* Test external libraries
* Test validations already guaranteed by frameworks or libraries (e.g., zod, pydantic)
* Are duplicated or redundant
* Are extremely fragile
* Have a high maintenance cost
* Test implementation details instead of behavior
* Would not detect meaningful regressions

---

### 2. Detect Test Smells

Identify problematic testing patterns such as:

* Over-mocking
* Excessive snapshot testing
* Tests validating internal implementation details
* Highly coupled tests
* Extremely long or hard-to-read tests
* Redundant or duplicated tests
* Brittle tests that break easily during refactoring
* Tests that provide false confidence

Explain where these patterns appear and why they are harmful.

---

### 3. Evaluate the Overall Testing Strategy

Assess whether the current testing approach follows good practices such as:

* Test Pyramid balance
* Testing Trophy principles
* Appropriate distribution between:

  * Unit tests
  * Integration tests
  * Contract tests
  * End-to-end tests

Identify structural problems such as:

* Too many trivial unit tests
* Lack of integration tests
* Missing contract tests
* Too many or too few end-to-end tests
* Gaps in critical business flow coverage

---

### 4. Identify Simplification Opportunities

Estimate:

* The approximate number of tests that could be removed
* The percentage of reduction possible without increasing regression risk
* Which types of tests should be removed first

Provide this analysis separately for:

Backend
Frontend

---

### 5. Recommend an Ideal Test Strategy

Based on the current project structure, recommend an improved testing strategy including:

* The ideal test distribution
* Which types of tests should increase or decrease
* How to better protect the system against regressions
* How to reduce test maintenance costs
* Suggestions to improve test reliability and signal quality

---

### 6. Expected Output Format

Provide the results structured as follows:

EXECUTIVE SUMMARY
A high-level overview of the health of the testing strategy.

TEST VALUE DISTRIBUTION
Estimated distribution of tests by category:

* High value
* Medium value
* Low value
* Negative value

BACKEND ANALYSIS
Key issues and recommendations.

FRONTEND ANALYSIS
Key issues and recommendations.

TEST SMELLS FOUND
List and explanation of problematic patterns detected.

REMOVAL ESTIMATE
Approximate number and percentage of tests that could be removed with minimal risk.

RECOMMENDED TEST STRATEGY
An improved testing strategy tailored to this project.
