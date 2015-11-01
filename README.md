# jvTest
A simple testing framework for scripts produced in the jvInterpreter.  Inspired by [Jasmine](https://github.com/jasmine/jasmine).

## Installation
To install jvTest, simply combine the *Edit Scripts* folder in the repository with whatever directory is holding the scripts to be executed within your jvInterpreter environment.

### With xEdit
As an example, [xEdit](http://github.com/TES5Edit/TES5Edit) script developers should combine the *Edit Scripts* folder with xEdit's Edit Scripts folder.

### Other environments
For other environments, you'll want to make sure you have the [jvInterpreter](http://jvcl.delphi-jedi.org/JvInterpreter.htm) set up properly.  See the [JEDI Visual Component Library](https://github.com/project-jedi/jvcl) repository on GitHub.

## Usage
Feel free to check out the example script to get an idea of how to use jvTest.

### Quick run-down
* Always initialize jvTest before testing with `jvtInitialize;`
* When you have a group of tests to perform, use the Describe function to inform the framework that you're in a group of tests.
* Wrap all your tests in a try-except block, with `Pass;` being the last line of code in the try, and `on x: Exception do Fail(x)` for the exception handler (you can expand the exception handler for tear-down as necessary).
* You can use `Expect(boolean, string) or `ExpectEqual(Variant, Variant, string)` to test results
* You can print a report of the tests performed before finalizing jvTest with `jvtPrintReport;`
* Always finalize jvTest when done testing with `jvtFinalize;`