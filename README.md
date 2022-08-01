# TeXstudio

This architectural documentation of [TeXstudio](https://www.texstudio.org/) serves to provide a rigorous architectural description of the open-source software as a result of the study conducted on the software.

## Introduction to TeXstudio

TeXstudio is a popular LaTeX editor that is designed to make LaTeX typesetting easier and comfortable. It provide a user-friendly GUI that allows anybody to quickly start writing a _tex_ file. In fact, it also provides the user with a plethora of features, such as: bookmarks, autocompletion, link overlay, assistants, wizards, mathematical symbols, table-formatting, e.t.c. It is an open-source project, mainly hosted on [Github](https://github.com/texstudio-org/texstudio), and initally started in 2009 as a fork from [Texmaker](https://en.wikipedia.org/wiki/Texmaker).


## Objectives

This architectural documentation has the following objectives:
- Provide a view of the TeXstudio under the Functional viewpoints
- Provide a describing model for each view
- Provide evidence for architectural conformance of the Functional view
- Identify an architectural perspective that can be applied to the views

## Scope

The scope of this architectural documentation will be to provide **reliable**, **code-conforming** and **clear** documentation that can be understood and used by developers, contributors, maintainers or acquirers of TeXstudio. This architectural documentation should be useful in writing code, designing features or producing other architectural documentation for the software.  

## Table of Contents
1. [Perspective](perspective.md)
2. [Functional View](functional.md)

### Optional Readings
1. [Functional Scenario](functional_scenario.md)

## Notes

- Ideally we would have also used a dynamic analysis tool to get a runtime call graph of TeXstudio using a Profiler, however the different tools we have attempted to use weren't successful. We tried to use Valgrind on a remote machine (the mimi server) and a local Ubuntu installation, and Valgrind refused to work because of the [following error](m2/evidence/img/valgrind_error.png). Our second option was Bug Validator from SoftwareVerify, however they never responded to our email for access to the private beta. Other tools that we have found are behind paywalls, thus we were not able to produce a runtime call graph. However if we were able to get access to one, we would use it to somewhat justify and align with the static call graphs we have produced. 


