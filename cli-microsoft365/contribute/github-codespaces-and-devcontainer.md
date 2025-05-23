-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# GitHub Codespaces & Visual Studio Remote Development Container

One of the difficulties of getting started with a new project is setting up the development environment, installing dependencies and hoping that you've followed all the instructions correctly.

We know that this can be time-consuming and also put off potential contributors to the project, so we've looked at ways in which we can make contributor onboarding as simple as possible, so we have provided a definition for creating an instant development environment that contains all the dependencies needed to contribute to CLI for Microsoft 365, whether that is making code changes or making an update to the documentation, we have you covered.

Our development environments contain the following dependencies

* Ubuntu 20.04 inc. sudo, zsh, jq, curl, git & wget
* PowerShell (7.1.0)
* node (v18.16.1) & npm (9.1.2)
* Python3 (3.10) & pip3 (22.3.1)
* oh-my-zsh (zsh-in-docker)
* zsh-autosuggestions
* zsh-completions
* zsh-syntax-highlighting
* spaceship-prompt

We've also bundled the following Visual Studio Code extensions in the container

* ESLint
* Test Explorer UI
* Mocha Test Explorer
* GitLens

We also automate the initial configuration steps for you when the development environment is being created, so we run npm install to install the necessary packages from npm, npm run build to build the CLI source and create a symbolic link by running npm link to ensure that when you execute m365 it uses the code in the src directory.

You can use our development environment in the cloud using GitHub Codespaces or locally using Visual Studio Code Remote Development Containers.

## GitHub Codespaces

GitHub Codespaces is an online development environment, hosted by GitHub and powered by Visual Studio Code, that allows you to develop entirely in the cloud.

To create an instant environment to develop and test the CLI.

* Fork this repository
* On GitHub, navigate to the main page of the repository
* Under the repository name, use the Branch drop-down menu, and select the branch you want to create a codespace for
* Under the repository name, use the Code drop-down menu, and select Open with Codespaces
* Click New codespace

## Local Remote Development Container

You may also use the development environment definition locally using Visual Studio Code.

To build and use a remote development container for local development, you first need the below prerequisites installed.

* Visual Studio Code
* Docker Desktop
* Remote Containers extension

Once the prerequisites are installed

* Fork this repository
* Clone your forked repository locally
* Open the repository in Visual Studio Code
* You will receive prompt Folder contains a remote development container
* Click Reopen in Container to build the remote development container and start the instant development environment

The initial build time will vary depending on your machine, but is a one-time operation (unless we change the container in the future) so the next time you run the CLI in a remote development container the build step will not be required.
