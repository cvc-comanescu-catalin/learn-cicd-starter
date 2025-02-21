# learn-cicd-starter (Notely)

![CI badge](https://github.com/cvc-comanescu-catalin/learn-cicd-starter/actions/workflows/ci.yml/badge.svg)

This repo contains the starter code for the "Notely" application for the "Learn CICD" course on [Boot.dev](https://boot.dev).

## Local Development

Make sure you're on Go version 1.22+.

Create a `.env` file in the root of the project with the following contents:

```bash
PORT="8080"
```

Run the server:

```bash
go build -o notely && ./notely
```

*This starts the server in non-database mode.* It will serve a simple webpage at `http://localhost:8080`.

You do *not* need to set up a database or any interactivity on the webpage yet. Instructions for that will come later in the course!

Run go fmt ./... in the root of your project. You should see the code get formatted properly.
Unfortunately (in my opinion) the go fmt command always exits with status code 0.
Luckily go fmt prints the names of all the files it fixes, so if we want to fail a CI check when a repo isn't formatted, the easiest way is to make sure that nothing is printed to stdout.

test -z $(go fmt ./...)
The echo $? command prints the exit code of the last command that was run.

https://staticcheck.dev/docs/getting-started/
go install honnef.co/go/tools/cmd/staticcheck@latest

To run staticcheck on the entire Notely codebase, run this from the root of the project:
staticcheck ./...

Catalin's version of Boot.dev's Notely app.