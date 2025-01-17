# Contributing to Ratify

Welcome! We are very happy to accept community contributions to Ratify, whether those are [Pull Requests](#pull-requests), [Plugins](#plugins), [Feature Suggestions](#feature-suggestions) or [Bug Reports](#bug-reports)! Please note that by participating in this project, you agree to abide by the [Code of Conduct](./CODE_OF_CONDUCT.md), as well as the terms of the [CLA](#cla).

## Getting Started

* If you don't already have it, you will need [go](https://golang.org/dl/) v1.16+ installed locally to build the project.
* You can work on Ratify using any platform using any editor, but you may find it quickest to get started using [VSCode](https://code.visualstudio.com/Download) with the [Go extension](https://marketplace.visualstudio.com/items?itemName=golang.Go). 
* Fork this repo (see [this forking guide](https://guides.github.com/activities/forking/) for more information).
* Checkout the repo locally with `git clone git@github.com:{your_username}/ratify.git`.
* Build the Ratify CLI with `go build -o ./bin/ratify ./cmd/ratify` or if on Mac/Linux/WSL `make build-cli`.

## Developing

### Components

The Ratify project is composed of the following main components:

* **Ratify CLI** (`cmd/ratify`): the `ratify` CLI executable.
* **Config** (`config`): an example configuration file for `ratify`.
* **Deploy** (`deploy`): the deployment files for using ratify in a Kubernetes cluster.
* **Ratify Internals** (`pkg`): the internal modules containing the majority of the Ratify code.
* **Plugins** (`plugins`): the referrer store and verifier plugins for the Ratify Framework.

### Running the tests

* You can use the following command to run the full Ratify test suite:
    * `go test -v ./cmd/ratify` on Windows
    * `make test` on Mac/Linux/WSL

### Running the Ratify CLI

* Once built run Ratify from the bin directory `./bin/ratify` for a list of the available commands.
* For any command the `--help` argument can be passed for more information and a list of possible arguments.

## Pull Requests

If you'd like to start contributing to Ratify, you can search for issues tagged as "good first issue" [here](https://github.com/deislabs/ratify/labels/good%20first%20issue).

### Ratify Code

* Ensure that an issue has been created to track the feature enhancement or bug that is being fixed.
* In the PR description, make sure you've included "Fixes #{issue_number}" e.g. "Fixes #242" so that GitHub knows to link it to an issue.
* To avoid multiple contributors working on the same issue, please add a comment to the issue to let us know you plan to work on it.
* If a significant amount of design is required, please include a proposal in the issue and wait for approval before working on code. If there's anything you're not sure about, please feel free to discuss this in the issue. We'd much rather all be on the same page at the start, so that there's less chance that drastic changes will be needed when your pull request is reviewed.

### Plugins

If you'd like to contribute to the collection of plugins:

#### Referrer Store

* A referrer store should implement the `ReferrerStore` interface (`pkg/referrerstore/api.go`).
* This should provide a mechanism to list referrers, and retrieve manifests and blob content.
* A sample referrer store is provided at `plugins/reffererstore/sample/sample.go`.

#### Verifier

* A verifier should implement the `ReferenceVerifier` interface (`pkg/verifier/api.go`).
* This should provide a mechanism to perform verification against blobs and manifests from a referrer store.
* A sample verifier is provided at `plugins/verifier/sample/sample.go`.

## Feature Suggestions

* Please first search [Open Ratify Issues](https://github.com/deislabs/ratify/issues) before opening an issue to check whether your feature has already been suggested. If it has, feel free to add your own comments to the existing issue.
* Ensure you have included a "What?" - what your feature entails, being as specific as possible, and giving mocked-up syntax examples where possible.
* Ensure you have included a "Why?" - what the benefit of including this feature will be.

## Bug Reports

* Please first search [Open Ratify Issues](https://github.com/deislabs/ratify/issues) before opening an issue, to see if it has already been reported.
* Try to be as specific as possible, including the version of the Ratify CLI used to reproduce the issue, and any example arguments needed to reproduce it.

## CLA

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.opensource.microsoft.com.

When you submit a pull request, a CLA bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., status check, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.
