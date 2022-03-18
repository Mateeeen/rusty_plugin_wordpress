# 👋💻😅 Welcome to Fastech Coding Test
We’re excited to welcome you to the next stage – you earned it. Now it’s time to get started writing some code.

## 🐕 The Rusty Inc. Org Chart WordPress Plugin

Rusty Inc. is the leading corporation offering free benefits to both canine and human societies.

To improve their internal website, you will help them with the organizational chart editor and viewer. It’s implemented as a WordPress plugin. Activate the plugin and you will see a “Rusty Inc. Org Chart” item almost at the top of the menu.

Right now some of the functionality is missing and we need your help! Below are your tasks, **please answer any questions asked in GitHub issues.**

## 🤹 Your Tasks
* Implement the back-end save functionality: clicking “✅ Save” should persist the tree, and if it was requested, also regenerate the secret key. Feel free to use functionality already in the plugin, like the `regenerate_key` method in `Rusty_Inc_Org_Chart_Sharing`.
* Find a way to speed up rendering the tree on the back-end: when the corporation grows and we reach more levels (try with each team having 3 sub-teams and 9 levels), rendering the tree starts taking too much time. The HTTP response for the plugin admin page should be a lot faster than it is now, especially for larger datasets. More importantly – how would you explain to the junior colleague who wrote this code: why it was so slow, and how your fix addresses the issue. Please be explicit about any of your findings.
* There are open issues for security audits. Please follow the instructions in the issues and leave your findings as one or more comments. Finding the security problems is a crucial part of this test, so it deserves a small hint. In the code, you will find a few classic OWASP Top 10 vulnerabilities, a logic error, and a problem only relevant if the plugin was to be released and installed on several sites. None of them are WordPress or PHP-specific. We don't expect you to fix the existing problems, but it is important to make sure that all code that you add is secure.
* Please make sure to accompany your code changes with some automated tests, where you find necessary. While tests will not detect all problems, they can help point out the obvious ones.
* Answer this question in the open issue in your GitHub repo: how many different/distinct secret keys can be generated with the current approach using `wp_generate_password`?

To keep things simpler, a couple of limitations:
- The plugin shouldn’t need a build process or additional dependencies.
- DOM manipulation should be limited to the framework level (`framework.js`) and ideally the UI level should contain only declarations of DOM structure.

## ⏳ Time
* **The amount of time you take does not indicate anything about your coding ability or chance of success.** People have told us they’ve spent anywhere from 6 - 25+ hours on the code test. People who say they take 6 hours have passed and succeeded at trial. People who say they take 25 hours have passed and succeeded at trial. 
* **We intentionally don’t track anything in your VS Code environment.** We don’t track time, as we trust our colleagues to make best use of their time. The hiring process is no different. We trust you to do what is best for you. We provide an online environment to save you time, not track it.
* **Please don't rewrite the plugin from scratch.**  Feel free to add, remove, and/or update existing code however you feel is best. The expectation is to keep your code changes focused on the tasks. Changes that are unrelated to any specific task are discouraged.


* When you're done, please ping us on Skype. From there, we will organize a member of our team to review your work.

## 🎹 Development
👷 Everything should be already be set up for you! We're experimenting with a zero-setup cloud based editing environment using VSCode, to avoid lengthy setup issues and to get you started straight away. We recommend using Chrome-based browsers, as Microsoft are still working out some kinks in other browsers.

* Visit <a id="vscode-url" href="https://548c0afafad8.vscode.prod1.devex.live">https://548c0afafad8.vscode.prod1.devex.live</a> to access our cloud-based editor, use the password <code id="vscode-password">1de4524a40c6323aa6538764185d7b08</code> to login, then wait until this `README.md` loads before you get started!
* Your WordPress development site is available at <a id="wordpress-url" href="https://548c0afafad8.wp.prod1.devex.live">https://548c0afafad8.wp.prod1.devex.live</a>. Use <code id="vscode-user">548c0afafad8</code> as the username, and `1de4524a40c6323aa6538764185d7b08` as the password.
* Here's a link to the plugin page for your convenience: <a id="plugin-url" href="https://548c0afafad8.wp.prod1.devex.live/wp-admin/admin.php?page=rusty-inc-org-chart">https://548c0afafad8.wp.prod1.devex.live/wp-admin/admin.php?page=rusty-inc-org-chart</a>
* You have access to a `bash` terminal within VSCode, via the hamburger menu's Terminal item.
* You will need to use `git` for source control. Please ensure you're familiar [with the basics](https://guides.github.com/introduction/git-handbook/) before starting out.
* When `git fetch`ing or `git push`ing via the terminal, you'll need to enter a Personal Access Token as your password for GitHub. Please [create a personal access token](https://help.github.com/en/github/authenticating-to-github/creating-a-personal-access-token-for-the-command-line) with the `repo` scope from [this settings page](https://github.com/settings/tokens), and keep it safe.

### ⏸ Debugging PHP with XDebug
* Click the debugging icon on the VSCode sidebar, and you can start XDebug by clicking "Play" for the "Listen for XDebug" configuration. You will be able to add breakpoints on specific lines in the editor, and view the callstack etc. To activate the debugger when visiting the site, make sure to append the `XDEBUG_SESSION_START` param to either GET or POST parameters.
* To debug the CLI functionalities, click the debugging icon on the VSCode sidebar and click "Play" for the "WP-CLI - Listen for XDebug" configuration. To initialize the debugging session, you can write the following in the command line, as an example: `XDEBUG_MODE=debug XDEBUG_TRIGGER=1 wp rusty set --type=sample`

### ⏱ Profiling PHP with XDebug
* Append `XDEBUG_PROFILE` param to either GET or POST parameters. The profiler will write to the `.cachegrind` folder, and you should download the files it outputs locally, using `kcachegrind`, or`qcachegrind` etc to open them. The URL will be `https://548c0afafad8.wp.prod1.devex.live/wp-content/plugins/rusty-inc-org-chart/.cachegrind/<file>`
* To profile the CLI functionalities, you can write the following in the command line, as an example: `XDEBUG_MODE=profile XDEBUG_TRIGGER=1 wp rusty set --type=sample`

Note that the online editor instance will not show the `.cachegrind` folder by default. In order to download it you will need to rename it to something that doesn't start with a dot character (using the console) and then download it by right-clicking it on the tree explorer and choosing "Download". For example, to rename it to `foo` you can execute the following in the console: `mv .cachegrind foo`. This will make a `foo` folder appear in the online editor.  

### 👉 Process

* The final deliverable should be multiple [pull requests](https://help.github.com/articles/creating-a-pull-request/) in the repository.
* If it will help you, feel free to use the GitHub issues or project functionality, though it's not mandatory at all.
* If you have any questions, let us know, we'd be happy to help.

### 💉 Running tests:

* For the PHP tests, run `phpunit` from your terminal in VSCode.
* For the JavaScript tests, visit [https://548c0afafad8.wp.prod1.devex.live/wp-content/plugins/rusty-inc-org-chart/tests/test.html](https://548c0afafad8.wp.prod1.devex.live/wp-content/plugins/rusty-inc-org-chart/tests/test.html)

### 🪡💉Running coding standards checks
* You can run `phpcs` from your terminal in VSCode.

### 💡 Helpful tips:

* Back-end entry point: have a look at `class-rusty-inc-org-chart-plugin.php` and the `add_init_action`.
* Front-end entry point: the bootstrap code is in `admin-page-inline-script.php`. Hydrating the UI is much easier through an inline script than via AJAX calls.

## ✅ What To Pay Attention To Besides The Tasks
* Simplicity – we would consider it a win if the code does not get more complex after adding more features and fixing issues.
* Make the changes easy to review – detailed pull request descriptions, small pull requests, commit granularity, descriptive commit messages.
* Design and code quality — separation of concerns, abstraction, naming…
* Backwards compatibility – if you make changes to how the plugin works, make sure users who have already installed it won’t have trouble upgrading.
* Browser compatibility – the plugin should work well under the latest two versions for all major browsers – see [Browse Happy](https://browsehappy.com/) for current latest versions.

## 😐 What To Not Pay Too Much Attention To
These are still important, but we thought for this test they would be a distraction:

* WordPress or PHP internals – the language should have familiar enough syntax and we have tried to put some extra pointers about how WordPress works. Ideally you shouldn't need more than a quick Google search to accomplish what you need. **This is not a test for your PHP or WordPress skills.**
* PHP minimum version – WordPress core still works on PHP 5.6 (ancient). On WordPress.com we run the latest PHP version, so no need to worry about that.
* Internationalization – normally a very important part of the development process, because it allows people from all over the world to use our software. However, in this case, it would add too much complexity, so we decided to omit it for now.
* Asset size and number of HTTP requests – another usually important consideration that we can forgo for now, because the plugin will be used in an intranet and under HTTP/2.

## 🙋 Frequently Asked Questions

### I found a problem. Is fixing it part of the task?
It depends on the severity of the problem. This will be a great case for your prioritization skills to shine :) Please note all problems, order them by their priority, fix the top ones if you think they're essential, and show us the prioritized list of the ones that still need fixing.

### It’s taking up too much of my time, what should I do?
It depends on why is it taking longer. Few tips:

* Avoid spending too much time on any one task and getting lost in the details.
* Prioritize – make sure you do the most important tasks first and leave the “nice to haves” for later. You can open issues to log whatever extra things you would have liked to address.
* “The technologies are too foreign” – we have assumed familiarity with: how a web server side works, a C-based server-side language, and some browser and JavaScript knowledge. We have left some comments to guide you through the WordPress-specific bits, but by all means, if you can't find an answer to your question with a quick Google search, ask us. The goal is not to test the knowledge about a specific language or framework.

### I can’t reproduce the org chart rendering performance problem. Can you help me?
Run `wp rusty set --type=big` in the terminal, and then try opening the plugin admin page 🐌

### The WordPress/DB cloud instance cannot initialize
Each instance is quota limited to 500MB - this likely is the cause for it. Usually, flushing the cachegrind cache by wiping the folder `wordpress/wp-content/plugins/rusty-inc-org-chart/.cachegrind/` resolves the issue. If this doesn't resolve it, please contact us.

### I deleted the plugin directory by accident.
Please contact our recruiters to have your cloud instance re-initialized. Any changes that were pushed to the repository will persist, and conversely, any local (non-pushed) changes cannot be restored.

### What is considered a descriptive commit message?
✅ Contains a header line (up to 50 chars) and optionally an additional body separated from the header by a line break.

✅ Is understandable even by seeing only the header of the message.

✅ Is unambiguous.

✅ Instead of only answering "what are the changes?" (we can already see that in the diff), it answers “What are the changes for?”. In other words, it explains the motivation for the change. 

