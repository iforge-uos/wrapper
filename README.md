# iForge Printer Pi Wrapper Files

This is the set of python files that provide a wrapper for the Raspberry Pi attached to our printers in order to facilitate communication between our VM and the Octoprint Instance

## Development

In order to contribute to this workspace first clone it to your local machine and enable the virtual environment. The method for doing so will depend on your system.

When you are satisfied with you changes create a PR confirm that the changes pass the testing process before merging.

This is the intended process for the github workflow to be run in order to catch any errors or omissions from the addition. This should be run on the creation of any pull requests.

1. Set up the correct Python version on the runner and install the required dependencies from the ???
2. Testing is then done as outlined in the [Test Process](#test-process)
3. The file is then built as a package and all of the Pis download the latest version

Steps 1 and 2 are intended to be run on creation of a PR and prevent merging on a failure.
Step 3 is done on a push to main as part of the deployment process.

### Test Process

1. The Ruff Linter confirms that all files within both the `wrapper_app` and the `test` packages are correct python files
2. The `verification.py` is run as a standard python file to confirm that all of the required tests are present.
3. All tests within the `test` package are run using `pytest` to confirm that all tests pass

If either the verification file determines that tests are missing or some tests fail the build process is aborted and a failure is returned to the person who pushed.
