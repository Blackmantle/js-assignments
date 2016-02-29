[![Brest Rolling Scopes](http://brest.rollingscopes.com/images/logo_rs_text.svg)](http://brest.rollingscopes.com/)
#Brest Rolling Scopes School
## Javascript Assignments  [![Build Status](https://travis-ci.org/aorgish/rolling-scopes-js-assignments.svg?branch=master)](https://travis-ci.org/aorgish/rolling-scopes-js-assignments)

Yet another javascript assingments. There are a lot of interactive javascript resources for beginers, but most of them are online and do not cover the modern programming workflow. There are some excelent training resources on github (https://github.com/rmurphey/js-assessment, https://github.com/mrdavidlaing/javascript-koans etc) but they are not exactly simulate the everyday programming process. So the motivation of this project is to show TDD process in the wild to the begginers. Assingment tests are implemented in various ways to feel a difference and gain the expirience what manner is good, what is bad and what is ugly.

Another idea is to prepare assignment to cover all standard javascript functions, to drilling and mastering skills. Some tasks are practical, but some tasks are rather synthetic.

And the last idea is to inure trainees to work using unit test and feel unconfortable when programming without tests.

To start javascript assignments please follow the next steps:
*  [Fork this repo](#user-content-how-to-fork-this-repo)
*  [Setup travis-ci to test the commits](#user-content-how-to-setup-travis-ci)
*  [Setup the work environment](#user-content-how-to-setup-work-environment)
*  [Implement assignments using TDD fashion](#user-content-how-to-implement-assignments-using-tdd-fashion)
*  [How to debug tasks](#how-to-debug-tasks)

### How to fork this repo
* Click the **Fork** button at the top-right corner of this page and the repository will be copied to your own account.
* Run `git clone https://github.com/<your-account>/rolling-scopes-js-assignments.git` from command line to download the repo.

### How to setup travis-ci
* Open [https://travis-ci.org/](https://travis-ci.org/) and sign in with your github account.
* Activate your foked repo **rolling-scopes-js-assignments**.
* Edit local README.md file and update all links (just replace all occurences of `'aorgish'` with your account name).
* Commit and push updated README.md to github:
```bash
  git add README.md
  git commit -m "Update the links"
  git push origin master
```
* Open https://github.com/aorgish/rolling-scopes-js-assignments and test the build icon. Now it will run all tests and update status once you push changes to github. Keep this icon green!


### How to setup work environment
* Download and install the latest [Nodejs](https://nodejs.org/en/download/stable/).
* Run `npm install` from you repository folder to download the required modules. All dependent modules will be located in the  *node_modules* folder.
* Open your favovire editor and complete tasks.
* Open your terminal and use `npm test` command to run all tests. You can run single file by passing it as argument `npm test ./test/01-strings-tests.js`.
* The local repo folder has the following structure: <pre>
    node_modules - app dependences restored by `npm install` command, you can delete this folder and restore later again.
    task - folder with tasks modules, it's your main folder.
    test - folder with tests modules to verify the tasks completion.
</pre>

### How to implement assignments using TDD fashion
Now you are ready to implement assignments. Tasks modules are located in the **task** folder. Each module consists of several tasks for specified topic. Each task is usually a regular function:
```javascript
  /**
   * Returns the result of concatenation of two strings.
   *
   * @param {string} value1
   * @param {string} value2
   * @return {string}
   *
   * @example
   *   'aa', 'bb' => 'aabb'
   *   'aa',''    => 'aa'
   *   '',  'bb'  => 'bb'
   */
  function concatenateStrings(value1, value2) {
     throw new Error('Not implemented');
  }
```
Resolve this task using the following [TDD steps](https://en.wikipedia.org/wiki/Test-driven_development#Test-driven_development_cycle):
* Run unit tests and make sure that everything is OK and there are no failing tests.
* Read the task description in the comment above the function. Try to undestand the idea. If you got it you are to write unit test first, but unit tests are already prepared :) Skip step with writing unit tests.
* Remove the throwing error line from function body
```javascript
     throw new Error('Not implemented');
```
and run the unit tests again. Find one test failed (red). Now it's time to fix it!
* Implement the function by any way and verify your solution by running tests until the failed test become passed (green).
* Your solution work, but now time to refactor it. Try to make your code as pretty and simple as possible keeping up the test green.
* Once you can't improve your code and tests are passed you can commit your solution.
* Push your updates to github server and check if tests passed on [travis-ci](https://travis-ci.org/aorgish/rolling-scopes-js-assignments/builds).
* If everything is OK you can try to resolve the next task.

### How to debug tasks
To debug tests you can use **Node inspector**. To install it just run `npm install -g node-inspector` in your terminal. Then follow next steps:
* Add `debugger;` to the first line of your task.
* Run your test file with `npm run test-debug ./test/01-strings-tests.js`.
* In another terminal run `node-inspector` and copy link from the output.
* Open the link in your favorite browser. You should see Chrome Developers Tools like interface where you can debug your tasks.
* When you found and fix your issue, close the browser's tab with the debug tools, stop the node-inspector by pressing Ctrl-C, stop the test runner by pressing Ctrl-C, remove the `debugger;` from your task.

##Contribution
Feel free to contribute into this project. New tasks and katas are welcome.
