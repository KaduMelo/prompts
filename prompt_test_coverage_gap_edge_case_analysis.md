Analyze the entire test suite of the system, including both backend and frontend tests, considering the full context of the codebase.

The objective of this analysis is to understand what the current automated tests cover and, more importantly, identify critical gaps where tests are missing — especially around edge cases, failure scenarios, and "sad paths".

The goal is to identify realistic failure scenarios that could happen in production but are currently not protected by automated tests.

---

## 1. Current Test Coverage Mapping

First, analyze all existing automated tests and identify:

* What parts of the system are currently covered
* Which features or flows have automated tests
* Which types of tests exist (unit, integration, e2e, component)
* What behaviors or logic are currently validated

Summarize the key areas currently protected by tests.

---

## 2. Identify Missing Edge Cases and Failure Scenarios

Based on the current coverage and the codebase behavior, identify important scenarios that are not currently tested.

Focus especially on:

* Error handling scenarios
* Rate limiting behavior
* Security-related flows
* Failure in external service dependencies
* Timeout scenarios
* Invalid or unexpected inputs
* Partial failures in async processes
* Network failures
* Race conditions
* Boundary value conditions
* Edge cases in business rules
* Missing validation scenarios
* Inconsistent states between components

These represent potential "sad paths" that may occur in production but are not currently protected by tests.

---

## 3. Explore the Codebase for Risk Scenarios

Explore the code to understand:

* Core application flows
* Critical business logic
* Important system behaviors
* External integrations
* Areas where exceptions may occur but are not explicitly handled

Identify realistic failure scenarios that could occur during real system usage.

Focus on areas such as:

* API boundaries
* asynchronous workflows
* background jobs
* distributed communication
* complex conditional logic
* feature orchestration across modules

---

## 4. Categorize Missing Tests

Categorize the missing tests into meaningful groups, such as:

Error Handling Tests
Rate Limiting Tests
Security-related Tests
Boundary Condition Tests
Validation Tests
Integration Failure Tests
Async Workflow Tests
Concurrency or Race Condition Tests
Feature-level Edge Cases

Provide this categorization separately for:

Backend
Frontend

---

## 5. Identify High-Risk Test Gaps

Highlight the most critical missing tests that could lead to:

* Production incidents
* Security vulnerabilities
* Data inconsistency
* System instability
* Poor user experience

Explain why these gaps represent real risks.

---

## 6. Estimate New Tests Required

Provide an estimate of:

* The number of new tests that should be created
* The distribution by category
* Which tests should be prioritized first

Separate the estimates for:

Backend
Frontend

Focus only on tests that add real protection to the system and improve regression safety.

---

## 7. Expected Output Format

Structure the response as follows:

EXECUTIVE SUMMARY
Overview of current coverage and the most important testing gaps.

CURRENT TEST COVERAGE
Key areas currently protected by automated tests.

MISSING EDGE CASES AND SAD PATHS
List of important scenarios not currently tested.

BACKEND TEST GAPS
Missing backend tests categorized by type.

FRONTEND TEST GAPS
Missing frontend tests categorized by type.

HIGH-RISK GAPS
Most critical missing tests that could lead to production issues.

NEW TEST ESTIMATE
Estimated number of new tests required and prioritization.

RECOMMENDED NEXT STEPS
Practical recommendations to improve coverage while keeping the test suite maintainable.
