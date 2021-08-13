+++ 
draft = false
date = 2021-05-14T12:00:00-01:00
title = "GZoltar4Tests - Evaluating Spectrum-Based Fault Localization on Flaky Tests"
description = "spectrum-based fault localization for NOD flaky tests"
slug = ""
tags = []
categories = []
externalLink = ""
series = []
+++

#### By: Declan

Working with Professors [Marius Minea](https://www.cics.umass.edu/people/minea-marius) and [Yuriy Brun](https://www.cics.umass.edu/faculty/directory/brun_yuriy) for my undergraduate honors thesis, I modified an existing spectrum-based fault localization (SBFL) tool [GZoltar](https://github.com/GZoltar/gzoltar) to collect coverage on on test code across many re-execution in isolation. Our goal was to evaluate the effectivness on localizing the fault in the test code. By comparing the coverage between failing and passing test case executions, our tool attempts to locate the source of non-determinism in the test code. 

We evaluated GZoltar4Tests on a set of 13 known unfixed NOD flaky tests which used Maven with JUnit 4 on Java 8 and flaky failures were observed. Here's the [sheet](https://docs.google.com/spreadsheets/d/1Aumwx2lfOorT9TTw6Af6VviU-aYG4VP6/edit?usp=sharing&ouid=103834351673914647777&rtpof=true&sd=true) for tracking tests and tool's execution [outputs](https://drive.google.com/file/d/1Speq71Kho6dFlVqt8SRqjbhR1zlTuHZQ/view?usp=sharing).



*Abstract:*

Developers use continuous integration to incrementally check that software changes do not break existing functionality. When developers incrementally make changes to code, tests are run on the version with the changes to check whether the changes break existing system functionality. In an ideal world, failures from tests would reliably signal faults in the developer’s latest changes, be they in the code under test or the test code, and every test failure would warrant investigation. However some test failures are unreliable, stemming from flaky tests that can non-deterministically pass or fail for the same code under test. Flaky tests lead to unreliable signals from continuous integration and can erode the trust of developers in their regression testing. Flaky tests hinder progress as developers often have to spend hours only to discover that the occasional failures have nothing to do with their recent changes, but the failures are dangerous to ignore as they can expose real faults in the system. Using spectrum-based fault localization, we desire to identify faulty lines causing flaky failures by collecting coverage across test code. By localizing faults within the test code, developers or systems can directly attempt to modify these faulty lines to reduce the flaky failure rate. Our tool GZoltar4Tests localizes test code faults causing flakiness by quantifying the test failure execution through code coverage. We hope to use our presented tool to develop a system to suggest modifications to remove non-order-dependent flaky behavior.

Please read the [paper](https://drive.google.com/file/d/1mYiukKhcGH0xutQAsIGyGOfUZgAmMn-u/view?usp=sharing) if you'd like to learn more!

[Github Repo](https://github.com/graydh/gzoltar/tree/gzoltar4tests)
