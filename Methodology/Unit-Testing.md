[<< Back to Methodology](index.md)

# Unit Testing
Unit tests exercises individual units of code to determine whether such code is correct and fit for use.

# Best Practices
Test cases should be effectively laid out with the following structure:

- Setup
- Execution
- Validation
- Cleanup

Additional best practices:

- Tests should abstract common setup and teardown logic
- Tests should allow a margin for time-related tests
- Test code should be treated with the same love, care and respect as your production code!  Test code must work for both positive and negative cases, last a long time, be readable and maintainable, and use sound patterns and conventions.

# Anti-Patterns
Test code has anti-patterns, just like product code.  Some of the biggest offenders are:

- Tests should not depend on system state that were manipulated by previous tests
- Tests should not depend on other tests
- Tests should not test precise timing or performance
- Tests should not have all-knowing oracles
- Tests should not test implementation details
- Tests should not be slow
