A basic test api used for small local projects and coding.

Api exposes to functions:
- void suite(char* name, void (*func)());
- void it(char* name, int condition);

Function "it" takes the name of a test and the condition being tested. Using these arguments, the function prints test name to console in green or red (I.e. pass or fail) based on condition. Function "it" can be called by itself or wrapped in a function with other similar tests.

Function "suite" takes the name of a test suite and a function which wraps the tests. Test suite prints out test suite name to console and executes function which wraps tests.
