# Code Quality

## (CQ-100) High Maintainability

Requirements:

-   All repositories _must_ maintain their `main` branch at a Code Climate maintainability
    score of B or above.
-   This score _must_ be updated immediately after code is merged into the `main`
    branch.
-   The maintainability score must be displayed near the top of the README at the
    root of the repository.

Rationale:

-   Code Climate provides a robust and industry-standard measure for the
    maintainability of a codebase. While this is only one of many possible
    measures, Code Climate provides a solid baseline for measuring code quality.

Exceptions:

-   The following types of repositories are excluded from this standard:
    -   Data science repositories containing only Jupyter Notebooks
    -   Static websites not containing any code
    -   Repos containing only programming languages not supported by Code Climate
-   The following types of code can be excluded from your maintainability score:
    -   Test code
    -   Data migration code
    -   Generated code
-   In addition to the above exclusions, the following filter settings may be used
    by all projects. Any additional filters require approval from an engineering
    manager.
    ```yaml
    # .codeclimate.yml
    version: "2"
    checks:
        # Disable checks for similar code.
        # Because this creates too many false positives.
        similar-code:
            enabled: false
        # Increase the number of lines allowed for a method.
        # Because this is more reasonable for JavaScript.
        method-lines:
            config:
                threshold: 50
    exclude_patterns:
        - "tests/"
        - "spec/"
        - "**/*.spec.js"
        - "**/*.spec.jsx"
        - "**/*.spec.ts"
        - "**/*.spec.tsx"
        - "**/vendor/"
        - "**/node_modules/"
    ```

## (CQ-110) Robust Test Coverage

Requirements:

-   All repositories are required to maintain a code coverage level of 40%
    or higher for their `main` branch.
-   Code coverage percentage _must_ be published whenever code is pushed
    into the `main` branch.
-   The code coverage percentage must be displayed near the top of the README at the
    root of the repository.
-   All application code _must_ be included in the coverage percentage, even if tests
    have yet to be written for the code.

Rationale:

-   Code coverage is an indicator of how well test cases cover the codebase. While
    not a singular indicator of test quality, it is an important factor in ensuring
    that test cases cover a wide area of the codebase.

Exceptions:

-   The following types of repositories are excluded from this standard:
    -   Data science repositories containing only Jupyter Notebooks
    -   Static websites not containing any code
-   The following code can be excluded from your test coverage percentage:
    -   Test code
    -   Data migration code

## (CQ-120) Code Cleanliness

When code is no longer wanted, delete it. Never commit commented out code.

Pull requests should not be approved until these comments have been removed.

Rationale:

-   Standard git usage already tracks removed code so that it's not lost.
-   Leaving commented code leave the code base `littered` with distractions to
    the actual code flow.

Exceptions:

-   None

## (CQ-130) Never Hardcode Data

Data is anything that could potentially change between runtime environments or
over time during runtime.

This includes:

-   URLs
-   User data
    -   Email addresses
    -   Usernames
    -   Addresses
-   Identifiers for accessing external resources (e.g. OAuth Client ID)

Data must _always_ be stored in an external persistent store, like a database, or
passed to the program as an environment variable. When in doubt, you probably should
consider using a database or environment variable to pass data to a program.

Rationale:

-   Data changes over time and if you hardcode it, you will need to redeploy your
    application to update the data. If you use a database or environment
    variable, you can change the data without requiring a new deployment.
-   While hardcoded data may not qualify as a secret, it still may be considered
    sensitive. For example, a hardcoded email address can be easily discovered in
    GitHub and used to send spam or for phishing attacks.

Exceptions:

-   None
