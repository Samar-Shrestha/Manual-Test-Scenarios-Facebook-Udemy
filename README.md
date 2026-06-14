# Manual Test Scenarios — Facebook (Signup & Login) and Udemy (Search)

## About this project
This project documents a manual QA test design exercise covering three real-world feature areas across two well-known applications:

- **Facebook — Signup** (form validation, field rules, age limits)
- **Facebook — Login** (authentication flows, security checks, cross-browser/device compatibility)
- **Udemy — Search** (category, instructor, and course search behavior)

Test scenarios were planned and tracked using **Trello** (Kanban board, organized by feature), with the final test cases documented in **Excel** and **Markdown**.

## What's inside
```
test-scenarios/
├── facebook-signup-test-cases.md / .xlsx
├── facebook-login-test-cases.md / .xlsx
└── udemy-search-test-cases.md / .xlsx
screenshots/
└── trello-board.png
```

Each `.md` file contains a quick-glance table (renders directly on GitHub); each `.xlsx` file contains the full detailed test case (Preconditions, Postconditions, Expected/Actual Results, Status, Executed By, etc.).

## Test approach
- Test cases were grouped into **valid (positive)** and **invalid (negative)** scenarios for each feature, plus a dedicated **compatibility testing** set for Facebook Login
- Negative test design focused on field-level validation: empty fields, length boundaries (very short/very long inputs), special characters, format errors (email/phone), password complexity rules, and age boundaries
- Compatibility testing covered Chrome, Firefox, Edge, and Safari across desktop, iPhone, and Android
- Udemy search testing covered category, instructor, and course search, including spelling mistakes, synonyms, and multi-language queries

## Summary
| Feature Area | Total Scenarios | Positive | Negative |
|---|---|---|---|
| Facebook Signup | 28 | 6 | 22 |
| Facebook Login | 24 | 12 | 12 |
| Udemy Search | 21 | 18 | 3 |
| **Total** | **73** | **36** | **37** |

*(Facebook Login's 7 compatibility scenarios are counted as positive checks for browser/device support.)*

## Sample test cases

**Facebook Signup** (see [facebook-signup-test-cases.md](./test-scenarios/facebook-signup-test-cases.md) for all 28):

| Test ID | Test Scenario | Test Type | Priority | Status |
|---|---|---|---|---|
| TC_FBS_001 | Validate signup with valid email address | Positive | Medium | Pass |
| TC_FBS_017 | Validate a password with less than 6 characters (e.g. Abcd12#) | Negative | High | Pass |
| TC_FBS_021 | Validate providing a date of birth resulting in age less than 13 | Negative | High | Pass |

**Facebook Login** (see [facebook-login-test-cases.md](./test-scenarios/facebook-login-test-cases.md) for all 24):

| Test ID | Test Scenario | Test Type | Priority | Status |
|---|---|---|---|---|
| TC_FBL_009 | Login with an invalid password 3 times in a row | Negative | High | Pass |
| TC_FBL_018 | Test login using Safari on iPhone | Positive | Low | Pass |

**Udemy Search** (see [udemy-search-test-cases.md](./test-scenarios/udemy-search-test-cases.md) for all 21):

| Test ID | Test Scenario | Test Type | Priority | Status |
|---|---|---|---|---|
| TC_UDS_005 | Validate searching for a parent category with a spelling mistake | Negative | High | Pass |
| TC_UDS_017 | Validate searching for a course using its rating | Positive | Medium | Pass |

## Trello board
The planning board used for this project can be viewed here: **[https://trello.com/b/y7ulwX5m/example-defect-reprts]**

## Key learnings
- Practiced designing comprehensive test scenarios for real-world applications across multiple feature areas
- Applied boundary value analysis and equivalence partitioning to field validation (length limits, age ranges, password rules)
- Designed cross-browser and cross-device compatibility test scenarios
- Structured test scenarios into valid/invalid groupings to ensure balanced positive and negative coverage
