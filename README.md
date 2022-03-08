# GSoC 2022 - Neutralinojs

Google Summer of Code 2022 ideas and guidelines - Neutralinojs

## What is GSoC?

GSoC (Google Summer of Code) is an international program that motivates developers to contribute to open-source projects. Google awards stipends for contributors who
successfully complete the GSoC program. GSoc contributors typically work on open-source development tasks under the guidance of organization mentors. Read more details about GSoC from the [official website](https://summerofcode.withgoogle.com/).

## How to become a GSoC contributor?

Anyone who is older than 18 can become a contributor with the GSoC 2022 program. Please follow the following steps:

- Join Neutralinojs Discord channel using [this invitation link](https://discord.gg/cybpp4guTJ)
- Introduce yourself in the #gsoc channel.
- Become familiar with the project, and start contributing
- Tell us about tasks that you would like to work on. If you have new ideas, tell us about goals
- Start drafting a proposal by discussing with mentors
- Submit your proposal and achieve the planned milestones based on the GSoC program [schedule](https://summerofcode.withgoogle.com/programs/2022).

## How to become a GSoC mentor?

If you are familiar with Neutralinojs internals and the codebase, you can become a mentor. Please discuss more details about mentorship by sending an email
to `neutralinojs[AT]gmail.com`

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

### C++/JavaScript integration test system enhancements

Neutralinojs project has a integration test suite for testing both C++ and JavaScript code at once. Currently, Neutralinojs integration tests covers minimal tests 
to detect possible function breakdowns. The goal of this task is to write a complete test suite covering all aspects of Neutralinojs APIs and global variables. Also, we expect to run the test suite on Windows CI instance too.

Areas: Neutralinojs, Unit/Integration testing, Node.js and GitHub Actions

Difficulty rating: Medium

Project size: ~350h
