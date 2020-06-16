---
layout: post
title: E2E testing with Cypress
author: tonidahl
excerpt: Excerpt TODO
tags:
- E2E
- Cypress
- CI
- Jenkins
- cloud
---


I have been using Selenium based products for E2E testing for several years.
Running E2E tests on Selenium, can be sometimes painful. You might encounter flaky tests that seem to fail with no reason, testing dynamic content can be a challenge and debugging failing tests might eat up a lot of your precious time.
Luckily, in the recent years there has been a lot of effort in reducing this pain.
Newer testing tools, like Cypress have taken a different approach in their architecture in order to resolve some common issues arisen in traditional E2E testing.

In this post, we are going to concentrate mainly on Cypress and how it is leveraged in our [NAPOTE](https://github.com/finnishtransportagency/mmtis-national-access-point) project. When we started our project, we had an opportunity to choose Cypress as our E2E testing tool and test it thoroughly. 
You will learn about the pros and cons of Cypress, how to setup it in your testing environment and how to write some simple tests with it.


## What is Cypress and why would I use it?

Cypress is an E2E testing tool that can be ran locally or in headless mode on a server. It attempts to be as close as possible to the testable web application. Cypress accomplishes this by injecting the test code in the browser. 

* Generic stuff about selenium.
* Pros and cons of selenium
* Why cypress does this better?
* Cypress browser support cons, arguments against IE11.
* Why selenium is not that bad. Why many people are still using it?

## Testing locally

* Stuff about requirerements, nodejs cypress-cli, browsers etc.
* Electron/chrome/firefox. Electron by default.
* Some Cypress CLI features.

```bash
$ Cypress run
```

## Testing in the Cloud

* Intro.
* Overview graph of the architecture.
* Stuff about jenkins, circle ci, our docker image, link to cypress docker image.
* Explain the architecture.
* Cloud dashboard

## Write your first test

* Brief explanation of the test runner.

```javascript
// Stuff
```

## Bonus: Testing with naughty strings

As an experiment, I wanted to try out if we could break our app by inserting some "naughty strings" in our form fields.
For this, I created a simple random string generator that combines strings from a collection of troublesome strings that might cause problems if used as user-input.
I didn't use so much time for this feature, maybe 30 minutes or so, so it cannot be compared to more advanced fuzzing techniques.

To my surprise, the generated strings were able to cause a few issues in our app that were related to string parsing or form field validation.
Evidently, using these strings in combination with your ordinary input tests might catch a few more extra bugs.

```javascript
// Code
```



## Conclusion

I'd like to encourage you to try Cypress in your project. Give it a proper spin, maybe in a bigger project.
Sometimes, in our project, we thought that we encountered a flaky test. Turns out, in 90% of the cases (guesstimate) it was just either our misunderstanding in how Cypress handled things or
just plain old problem in our application code. Only one problem was caused by an actual bug in Cypress and that was readily fixed by the Cypress team in the next release.

Additionally, TestCafe seems to be an interesting competitor to Cypress that you might want to add into your watch list.

At this point, you might wonder whether to stay with Selenium or maybe choose another tool like Cypress. There are no fully right or wrong answers.
In my opinion, choosing a correct E2E testing tool (or any other tool) is a matter of trust. If you don't trust something, stop using it and look for alternatives.

*Read my other testing related post at here: [How to deploy test instances to AWS using CircleCI, GitHub API and simple Slack commands](/2018/08/16/easy-test-deployments-round-two.html)*