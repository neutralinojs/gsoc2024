__***Note: Neutralinojs wasn't selected for GSoC 2023. We are planning to apply again for the 2024 program in future.***__

# GSoC 2023 - Neutralinojs

Google Summer of Code 2023 ideas and guidelines - Neutralinojs

## What is GSoC?

GSoC (Google Summer of Code) is an international program that motivates developers to contribute to open-source projects. Google awards stipends for contributors who
successfully complete the GSoC program. GSoc contributors typically work on open-source development tasks under the guidance of organization mentors. Read more details about GSoC from the [official website](https://summerofcode.withgoogle.com/).

## How to become a GSoC contributor?

Anyone (including newcomers and beginners) who is older than 18 can become a contributor with the GSoC 2023 program. Please follow the following steps:

- Join Neutralinojs Discord channel using [this invitation link](https://discord.gg/cybpp4guTJ).
- Introduce yourself in the #gsoc channel on Discord.
- Become familiar with the main project and sub-projects, start with the [documentation](https://neutralino.js.org/), and then [codebases](https://github.com/neutralinojs).
- Watch [framework](https://youtu.be/QGZywYDsSyg), [JavaScript API](https://youtu.be/V-RD6ia5YjY), and [CLI](https://youtu.be/XUj20aJDJiI) code explanation videos for detailed codebase explanations. 
- Read both [contribution guide](https://neutralino.js.org/docs/contributing/framework-developer-guide) and [code style guide](https://neutralino.js.org/docs/contributing/code-style-guide), then start contributing.
- Tell us about tasks that you would like to work on. If you have new ideas, mention them in community channels including your project goals.
- Start drafting a proposal by discussing with mentors.
- Submit your proposal and achieve the planned milestones based on the GSoC program [schedule](https://summerofcode.withgoogle.com/programs/2023).

## How to start writing a project proposal?

- Make sure to follow the above initial steps and become familiar with the project.
- Select a project idea out of the mentioned below
- If you have an idea of your own / want to initiate one , post its summary and goals in a [new GitHub discussion thread](https://github.com/neutralinojs/gsoc2023/discussions/new?category=ideas).
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

## GSoC 2023 project ideas

We have listed down some crucial tasks below for contributing. But, feel free to discuss
your own ideas with us via [Discord](https://discord.gg/cybpp4guTJ) or email (`neutralinojs[AT]gmail.com`). You can contribute Neutralinojs framework, CLI, client library and templates.

Thank you for contributing to open-source 🎉

### 1. Neutralinojs Builder: a community project to generate Neutralino app packages

Neutralinojs CLI generates platform-specific binaries for Linux, macOS, and Windows with a platform-independent resource file. Right now, Neutralinojs application developers need to use various tools to generate application installers (i.e.,: AppImage, NSIS) for each operating system. However, we have no plans to add application installer generation support to the official CLI to keep the CLI implementation minimal and less platform-dependent. Therefore, the Neutralinojs community has initiated a project called "Neutralinojs Builder" to generate application installers. The Neutralinojs builder project is still a POC and experimental, so the idea is to finalize the project based on the suggested technical specification finalized by the framework developers.

Areas: Node.js, Neutralinojs, Application bundling on operating systems

Difficulty rating: Medium

Project size: ~350h

Possible Mentors: Shalitha Suranga, Sainath Rao, TBD

#### Suggested technical decisions

- Creating a CLI plugin for the solution.
- Expose a new command to generate application packages.

```bash
# Installing the plugin
neu plugins --add neutralinojs-builder

# neu builder <target> <arch>
neu builder nsis --x64 # NSIS setup for Windows x64
neu builder deb --ia32 # Debian package for GNU/Linux ia32
neu builder appimage --x64 # AppImage for GNU/Linux x64
neu builder deb # GNU/Linux Debian packages for all supported CPU architectures

# Use configuration from neutralino.config.json
neu builder

# Removing the plugin
neu plugins --remove neutralinojs-builder
```
- If the developer run `neu builder` without any parameters, get the targets from the config file:

```json
"cli": {
  "builder": {
    "linux": {
      "targets": [
        {
          "target": "deb",
          "arch": [
            "x64",
            "ia32",
            "armhf"
          ]
        }
      ]
    },
    "win": {
      "targets": [
        {
          "target": "nsis",
          "arch": [
            "x64",
            "ia32"
          ]
        }
      ]
    }
  }
}
```
- Even though Neutralinojs provides x64 binaries officially, implement multi-architecture support.
- Implement package targets as internal plugins (Import only required modules based on targets). Try to use modules like `targets/deb.js`, `targets/nsis.js` for dynamic loading.


### 2. Make Neutralinojs compatible with older Windows versions

Issue: https://github.com/neutralinojs/neutralinojs/issues/486

Neutralinojs is tested on Windows 10 and 11, but it is not well-tested 
with previous Windows versions. The goal of this idea is to update Neutralinojs framework
source, build scripts, and DevOps workflow to officially support older Windows versions.

Areas: Windows API, DevOps, and Configuration

Difficulty rating: Medium

Project size: ~350h

Possible Mentors: Sainath Rao, TBD

#### Suggested technical decisions

*None -- cause needs to be indentified first*

### 3. NodeNeutralino: a community project to explain Neutralinojs custom backends

The goal is to create a sample wrapper project to guide developers to use a Node.js backend for a Neutralinojs app with
the extension API. This project will use Neutralinojs via Node.js child process API and communicate with the Neutralinojs extension API.

Areas: Node.js and Neutralinojs

Difficulty rating: Easy

Project size: ~175h

Possible Mentors: Sainath Rao, TBD

#### Suggested technical decisions

- Implement an API similar to Electronjs [`BrowserWindow`](https://www.electronjs.org/docs/latest/api/browser-window) class.

Example NodeNeutralino app code:

```js
const { NeutralinoApp } = require('node-neutralino');

// Accepts all configuration options available in Neutralino.window.create
// Don't manipulate the config file -- use internal CLI arguments instead.
const app = new NeutralinoApp({
              url: '/resources', 
              modes: {
                window: {
                  width: 500,
                  height: 500
                }
              }
             });

// Every Neutralino.window API function is available except window.create and draggable regions API
app.window.setFullScreen();
app.window.hide();
app.window.show();

// All other Neutralino APIs are also available
app.storage.setData('testKey', 'testValue');
app.debug.log('Hello');
app.filesystem.createDirectory('TestDir');

// Neutralino.app functions are available directly via the app instance
app.broadcast('testEvent');
app.exit();
```
- Try to implement without any third-party Node module.
- Make every function asynchronous and throw Neutralinojs [error codes](https://neutralino.js.org/docs/api/error-codes) properly.
- Use Node.js [child process API](https://nodejs.org/api/child_process.html#child_processspawncommand-args-options) to spawn Neutralinojs binaries.
- Create an app template for Neutralinojs CLI.
- Use a project structure similar to the Neutralinojs client library.

### 4. Fix `os.setTray` function problem for older macOS versions

Issue: https://github.com/neutralinojs/neutralinojs/issues/615

The os.setTray function fails on macOS Catalina and some other versions.
The goal of this task to debug the Neutralinojs macOS binary on different macOS versions and 
apply a generic solution.

Areas: Cocoa API and Debugging

Difficulty rating: Medium

Project size: ~350h

Possible Mentors: TBD

#### Suggested technical decisions

- Add additional configuration code to the [webview fork](https://github.com/neutralinojs/webview) rather than updating `window.cpp` if possible.

### 5. Adding window transparent setting to the configuration

Issue: https://github.com/neutralinojs/roadmap/issues/1

Add the `transparent` (Boolean) option to the configuration to control the webview's opacity on all supported platforms. When the setting is set to `true`, and the 
CSS background also has `opacity` as `0`, the user should be able to see through the window clearly. Transparency can be disabled by setting the `transparent` property to `false`. The developer can adjust the window transparency level with CSS. 

Areas: GTK, Cocoa, Win32 APIs

Difficulty rating: Hard

Project size: ~350h

Possible Mentors: TBD

#### Suggested technical decisions

- Try to implement the solution within [`window.cpp`](https://github.com/neutralinojs/neutralinojs/blob/main/api/window/window.cpp)
- Add implementation via a new function named `setTransparent()` under the `window` namespace. Invoke from `__createWindow`.
- Use `false` as the default value.
- Add as a CLI argument too (`--window-transparent`)

### 6. C++/JavaScript integration test system enhancements

Issue: https://github.com/neutralinojs/neutralinojs/issues/706

Neutralinojs project has a integration test suite for testing both C++ and JavaScript code at once. Currently, Neutralinojs integration tests covers minimal tests 
to detect possible function breakdowns. The goal of this task is to write a complete test suite covering all aspects of Neutralinojs APIs and global variables. Also, we expect to run the test suite on Windows CI instance too.

Areas: Neutralinojs, Unit/Integration testing, Node.js and GitHub Actions

Difficulty rating: Medium

Project size: ~350h

Possible Mentors: Shalitha Suranga, Sainath Rao, TBD

#### Suggested technical decisions

- Increase test coverage by adding more test cases.
- Test global variables properly.

## Contributing

We really appreciate your code contributions. Please read [this contribution guide](https://neutralino.js.org/docs/contributing/framework-developer-guide#contribution-guidelines) before sending a pull request. Thank you for your contributions.

## Contributors

<a href="https://github.com/neutralinojs/gsoc2022/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=neutralinojs/gsoc2022" />
</a>

## Past programs

- [GSoC 2022](https://summerofcode.withgoogle.com/programs/2022/organizations/neutralinojs)

Image created with [contrib.rocks](https://contrib.rocks).
