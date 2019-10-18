# Test-Driven Development (TDD)
Test-driven development is a development process that relies on the repetition of a very short development cycle: requirements are turned into highly specific test cases, and the software is improved only such that the new tests pass. It was developed or rediscovered by Kent Beck.  It forces the developer writing the code to focus on requirements first.  The changes made in response to a new test should be very limited in scale and scope.  By focusing on writing only the code necessary to pass tests, designs can often be cleaner and clearer than other approaches.

The basic process is:

- Add a test
- Run all tests and see if the new test fails (it should)
- Write the code (only satisfies the test, elegance not needed)
- Run all tests again
- Refactor
- Repeat

It can be summarized by the motto “Red, Green, Refactor”.

# Benefits
Test-driven development has many benefits:

- Validates the correctness of code and provides constant feedback
- Potential for developers to be more productive
- Encourages design by contract
- Ensures all code written is covered by at least one test
- Defects are limited and discovered earlier
- Encourages smaller units of code, looser coupling, independence, and cleaner interfaces
- Unit tests act as documentation

# Drawbacks
Some drawbacks are:

- Does not provide sufficient testing where full functional tests are required
- Success is dependent upon culture / management support
- Tests may share blind spots with the code being tested
- High numbers of passing tests may lead to a false sense of security
- Tests do add overhead to project work, with poorly formed tests adding much overhead
