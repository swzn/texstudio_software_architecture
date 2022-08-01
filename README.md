# TeXstudio

This architectural documentation of [TeXstudio](https://www.texstudio.org/) serves to provide a rigorous architectural description of the open-source software as a result of the study conducted on the software.

## Introduction to TeXstudio

TeXstudio is a popular LaTeX editor that is designed to make LaTeX typesetting easier and comfortable. It provide a user-friendly GUI that allows anybody to quickly start writing a _tex_ file. In fact, it also provides the user with a plethora of features, such as: bookmarks, autocompletion, link overlay, assistants, wizards, mathematical symbols, table-formatting, e.t.c. It is an open-source project, mainly hosted on [Github](https://github.com/texstudio-org/texstudio), and initally started in 2009 as a fork from [Texmaker](https://en.wikipedia.org/wiki/Texmaker).


## Objectives

This architectural documentation has the following objectives:
- Identify the stakeholders and provide a power/interest matrix to describe involvement in the system
- Identify a list of concerns that TeXstudio bases its architecture on
- Identify an architecural style that TeXstudio operates under
- Provide a view of the TeXstudio under the Context, Functional, Information and Deployment viewpoints
- Provide a describing model for each view
- Provide evidence for architectural conformance of the Functional view
- Identify an architectural perspective that can be applied to the views
- Provide an architectural critique on aspects of TeXstudio's design that are questionable

## Scope

The scope of this architectural documentation will be to provide **reliable**, **code-conforming** and **clear** documentation that can be understood and used by developers, contributors, maintainers or acquirers of TeXstudio. This architectural documentation should be useful in writing code, designing features or producing other architectural documentation for the software.  

## Table of Contents
1. [Stakeholders](m4/stakeholders.md)
2. [Perspective](m4/perspective.md)
3. [Context View](m4/context.md)
4. [Functional View](m4/functional.md)
5. [Information View](m4/information.md)
6. [Deployment View](m4/deployment.md)
7. [Architectural Critique](m4/critique.md)

### Optional Readings
1. [Functional Scenario](m4/functional_scenario.md)

### Appendix
1. [Revision Plan](m4/revision.md)
2. [Presentation Slides](m4/slides.md)

## Notes

- Ideally we would have also used a dynamic analysis tool to get a runtime call graph of TeXstudio using a Profiler, however the different tools we have attempted to use weren't successful. We tried to use Valgrind on a remote machine (the mimi server) and a local Ubuntu installation, and Valgrind refused to work because of the [following error](m2/evidence/img/valgrind_error.png). Our second option was Bug Validator from SoftwareVerify, however they never responded to our email for access to the private beta. Other tools that we have found are behind paywalls, thus we were not able to produce a runtime call graph. However if we were able to get access to one, we would use it to somewhat justify and align with the static call graphs we have produced. 


