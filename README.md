# c-test-api

A minimal C testing framework for small local projects and simple unit tests.

## Overview

This API exposes two functions to define and run test suites and individual tests:

- `void suite(char* name, void (*func)());`
- `void it(char* name, int condition);`

### `suite`

Defines a test suite by providing a name and a function containing related tests. When called, it prints the suite name to the console and executes the tests inside the provided function.

```c
void suite(char* name, void (*func)());
```

* ```name```: The name of the test suite.
* ```func```: A function wrapping the tests to execute in this suite.

### ```it```
Defines an individual test case by providing a test name and a boolean condition indicating pass or fail. It prints the test name with a green checkmark (✓) if passed, or a red cross (✗) if failed.

```c
void it(char* name, int condition);
```

* ```name```: The name of the test case.
* ```condition```: A boolean condition (non-zero = pass, zero = fail).

### Example Usage
```c
void test_suite_example() {
    it("should return true for valid input", my_function() == expected_value);
    it("should handle null input gracefully", my_function(NULL) == NULL);
}

int main() {
    suite("MyFunction Tests", test_suite_example);
    return 0;
}
```

## Implementation Details
* Uses ANSI escape codes to color output: green for passed tests, red for failed.
* Prints test suite and test names to console.
* Requires standard C libraries (stdio.h, stdlib.h, string.h).
