# Build Workflow

## Lifecycle

The application lifecycle includes several steps:

- `build`: Compile the source code to a binary named `awesome-api` using `go build`. The name `awesome-api` is derived from `go mod init github.com/<your github handle>/awesome-api`. Note that the first build may take some time.

- `run`: Run the application in the background by executing the `awesome-api` binary. Logs are written to a file named `awesome-api.log` using the command `./awesome-api > ./awesome-api.log 2>&1 &`.

- `stop`: Stop the application by killing the process with the Process ID (PID) of the application. Use the command `kill "$(pgrep awesome-api)"` to stop it.

- `post`: Create a new blog post. The filename and title are specified by the environment variables `POST_TITLE` and `POST_NAME`.

- `clean`: Stop the application, delete the `awesome-api` binary, and delete the `awesome-api.log` file.

- `test`: Run tests to ensure that the application behaves as expected.

- `unit-tests`: Run unit tests.

- `integration-tests`: Run integration tests.

- `lint`: Lint Go language code.

- `check`: Lint the markdown source and check for dead links.

- `validate`: Validate the `dist/index.html` file using the command-line Holberton's W3C Validator.

- `workflow`: Use GitHub Actions for testing.

- `package`: Create a zip file containing the necessary files.

- `help`: Display the help message.
