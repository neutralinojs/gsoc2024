# GSoC 2022 - Neutralinojs

Google Summer of Code 2022 ideas and guidelines - Neutralinojs

## What is GSoC?

GSoC (Google Summer of Code) is an international program that motivates developers to contribute to open-source projects. Google awards stipends for contributors who
successfully complete the GSoC program. GSoc contributors typically work on open-source development tasks under the guidance of organization mentors. Read more details about GSoC from the [official website](https://summerofcode.withgoogle.com/).

## How to become a GSoC contributor?

Anyone who is older than 18 can become a contributor with the GSoC 2022 program. Please follow the following steps:

- Join Neutralinojs Discord channel using [this invitation link](https://discord.gg/cybpp4guTJ).
- Introduce yourself in the #gsoc channel on Discord.
- Become familiar with the main project and sub-projects, start with the [documentation](https://neutralino.js.org/), and then [codebases](https://github.com/neutralinojs).
- Watch [framework](https://youtu.be/QGZywYDsSyg), [JavaScript API](https://youtu.be/V-RD6ia5YjY), and [CLI](https://youtu.be/XUj20aJDJiI) code explanation videos for detailed codebase explanations. 
- Read both [contribution guide](https://neutralino.js.org/docs/contributing/framework-developer-guide) and [code style guide](https://neutralino.js.org/docs/contributing/code-style-guide), then start contributing.
- Tell us about tasks that you would like to work on. If you have new ideas, tell us about goals.
- Start drafting a proposal by discussing with mentors.
- Submit your proposal and achieve the planned milestones based on the GSoC program [schedule](https://summerofcode.withgoogle.com/programs/2022).

## How to start writing a project proposal?

- Make sure to follow the above initial steps and become familiar with the project.
- Select a project idea out of the mentioned below
- If you have an idea of your own / want to initiate one , post its summary and goals in a [new GitHub discussion thread](https://github.com/neutralinojs/gsoc2022/discussions/new?category=ideas).
- Wait until project maintainers give a feedback to the post (We can identify possible changes in the early stage).
- Start drafting your proposal based on the Neutralinojs GSoC contributor proposal outline.

## What is the project proposal template?

Please create your GSoC proposal according to the following outline:

- Contact details (Name, Country, Email, GitHub username, Discord username, and a small description about yourself)
- Neutralinojs experience (Explain your familiarity with Neutralinojs)
- Contributions (Add links to your pull-requests, issues, and discussion threads)
- Project description (Describe the project idea)
- Goals (Summary of deliverables)
- Tasks Timeline (Decompose your goals into tasks and map with the GSoC timeline)
- Future contributions (How do you plan to contribute to Neutralinojs in the future?)

## GSoC 2022 project ideas

We have listed down some crucial tasks below for contributing. But, feel free to discuss
your own ideas with us via [Discord](https://discord.gg/cybpp4guTJ) or email (`neutralinojs[AT]gmail.com`). You can contribute Neutralinojs framework, CLI, client library and templates.

Thanks for contributing to open-source 🎉

### Make Neutralinojs compatible with older Windows versions

Issue: https://github.com/neutralinojs/neutralinojs/issues/486

Neutralinojs is tested on Windows 10 and 11, but it is not well-tested 
with previous Windows versions. The goal of this idea is to update Neutralinojs framework
source, build scripts, and DevOps workflow to officially support older Windows versions.

Areas: Windows API, DevOps, and Configuration

Difficulty rating: Medium

Project size: ~350h

### Support Unicode characters in Neutralinojs Windows version

Issue: https://github.com/neutralinojs/neutralinojs/issues/613

Unicode characters work without any issue on Neutralinojs Linux and macOS versions. But, 
Neutralinojs Windows version doesn't render Unicode characters correctly.
The goal of this task is to use Windows Unicode APIs and fully support Unicode in the Neutralinojs Windows version.

Areas: Windows API, Refactoring, and Text Encoding

Difficulty rating: Medium

Project size: ~350h

### Fix os.setTray function problem for older macOS versions

Issue: https://github.com/neutralinojs/neutralinojs/issues/615

The os.setTray function fails on macOS Catalina and some other versions.
The goal of this task to debug the Neutralinojs macOS binary on different macOS versions and 
apply a generic solution.

Areas: Cocoa API and Debugging

Difficulty rating: Medium

Project size: ~350h

### Adding opacity setting to the configuration

Issue: https://github.com/neutralinojs/roadmap/issues/1

Add the `opacity` option to the configuration to control the webview's opacity on all supported platforms. When the setting is set to `0`, and the 
CSS background also has `opacity` as `0`, the user should be able to see through the window clearly. For other opacity values, the transparency value needs to be applied accordingly.

Areas: GTK, Cocoa, Win32 APIs

Difficulty rating: Hard

Project size: ~350h

### NodeNeutralino: a community project to explain Neutralinojs custom backends

The goal is to create a sample wrapper project to guide developers to use a Node.js backend for a Neutralinojs app with
the extension API. This project will use Neutralinojs via Node.js child process API and communicate with the Neutralinojs extension API.

Areas: Node.js and Neutralinojs

Difficulty rating: Easy

Project size: ~175h

Possible Mentors: Athif Shaffy, Carlonn Rivers

### C++/JavaScript integration test system enhancements

Issue: https://github.com/neutralinojs/neutralinojs/issues/706

Neutralinojs project has a integration test suite for testing both C++ and JavaScript code at once. Currently, Neutralinojs integration tests covers minimal tests 
to detect possible function breakdowns. The goal of this task is to write a complete test suite covering all aspects of Neutralinojs APIs and global variables. Also, we expect to run the test suite on Windows CI instance too.

Areas: Neutralinojs, Unit/Integration testing, Node.js and GitHub Actions

Difficulty rating: Medium

Project size: ~350h

Possible Mentors: Shalitha Suranga

### Writing a test suite for the Neutralinojs CLI

Issue: https://github.com/neutralinojs/neutralinojs-cli/issues/95

The goal is to create a complete test suite for Neutralinojs CLI similar to the Neutralinojs [framework integration test suite](https://github.com/neutralinojs/neutralinojs/tree/main/spec). The suggested approach is to invoke CLI commands with the Node.js child process API and test Neutralinojs CLI's behavior (asserting command output, exit codes, file updates, etc.). We expect to implement Mocha tests for all CLI commands and options.

Areas: Node.js, Mocha, Testing and Neutralinojs

Difficulty rating: Easy

Project size: ~175h

Possible Mentors: Shalitha Suranga

### Neutralinojs Builder: a community project to generate Neutralino app packages

Neutralinojs CLI generates platform-specific binaries for Linux, macOS, and Windows with a platform-independent resource file. Right now, Neutralinojs application developers need to use various tools to generate application installers (i.e.,: AppImage, NSIS) for each operating system. However, we have no plans to add application installer generation support to the official CLI to keep the CLI implementation minimal and less platform-dependent. Therefore, we are planning to create a new community project called "Neutralinojs Builder" to generate application installers. The idea is to create this as a CLI plugin.

Areas: Node.js, Neutralinojs, Application bundling on operating systems

Difficulty rating: Medium

Project size: ~350h

Possible Mentors: Shalitha Suranga
