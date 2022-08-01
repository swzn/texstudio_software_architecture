## Functional View:

### M2 :

* A bit of boilerplate in the view introduction 
    - Decision: Partially Address
    - Changes: Removed the description of what a general functional structure model should look like
    - Reason: The main purpose that the Functional View serves in our AD is to provide new developers and experienced developers with enough documentation for them to understand how the main features of TeXstudio are implemented. For that reason, all parts of the view introduction that were added for _academic purposes_ have been removed.

* Counterintuitive that the QT widgets depend on application code
    - Decision: Partially Address
    - Changes: Described how Qt widgets are instantiated through _inheritance_ from the Qt framework
    - Reason: That part cannot be removed as it wouldn't be true to the code. Therefore, we choose to clarify how Qt widgets are instantiated through inheritance.

* Is "Qt Widgets" a single component or many? If many, are the provided/required interfaces in the diagram for each widget or just some of them?
    - Decision: Completely Address
    - Changes: The Qt widgets are connectors and are now shown to be connectors in the General Functional Structure Model
    - Reason: Qt widgets have been easily the most difficult part to represent, both in the presentations and on paper. They have now been representated as a set of widgets which hold Menus, Buttons, Dropdowns, but ellipses are used to show these widgets can be many more things.

* Counter-intuitive decision to aggregate Persistence and Version Control capabilities.
    - Decision: Ignore
    - Reason: Although counter-intuitive, one cannot use the Version Control capabilities without the persistence functionality. In other words, having version control as its own would simply be a subset of the Persistence functional element. It is more representative to show that the Version Control is _entirely_ dependent on the Persistence by aggregating the two.

* 2nd model is just a subset of the first, adds little value
    - Decision: Partially Address
    - Changes: The section containing the second model was refactored to a different file
    - Reason: This section was meant to be used as a functional scenario rather than simply a different version of the functional model. This section was refactored to its own file and now contains more details.

* Explanation of Doxygen output is copied from another source, without credit
    - Decision: Completely Address
    - Changes: Credit now given
    - Reason: Oversight on the initial submission, it is now fixed.

### M3

* A lot of the feedback that was given to us or the questions that were asked during the presentation in Milestone 3 only concern things that were said or left unsaid during the presentation. Most of the answers to these questions can be found throughout the architectural documentation for the functional view. However the feedback was very constructive in terms of how the presentation should be laid out for Milestone 4. It would now make more sense to first define what each functional element is and explain their responsabilities. The interaction between the elements should only be presented after each functional element was first defined. This was detrimental to the presentation in Milestone 3 because we first explained the interactions between the elements, and then we explained their inner workings, which leads to a lot of confusion.  

## Information View: 

### M2 :

* Preamble also a bit wordy and boilerplate. Better to just state scope and concerns as directly as possible.
    - Decision: Completely Address
    - Changes Made: Summarize introduction, remove unnecessary statements
    - Reason: Keep view concise
* Legend might be more usable than inline description of the notation
    - Decision: Completely Address
    - Changes Made: Add legend
Reason: Improve readability of diagram
* Lower standards of traceability
    - Decision: Completely Address
    - Changes Made: add traceability section and set standard for code referencing throughout view
    - Reason: Provide evidence and show coherence between claims made and the implementation in the codebase
* Arrows going in all directions negatively affects the flow of the diagram 
    - Decision: Ignore
    - Reason: Unidirectional and bidirectional arrows are important to capturing the relevant data flows, changing these would lead to inconsistency with the code or information loss in an already simplistic diagram
* Text description contains a lot of useful information that is not on the diagram (e.g., .png files) and easy to miss when scanning the text
    - Decision: Ignore
    - Reason: Diagram needs to be easily digestible, and is already dense in information; adding text would only make it harder to understand the information being communicated

### M3:
* There is no explanation as to how the ‘invalid input’ case is handled
    - Decision: Completely Address
    - Changes Made: new scenario added to highlight the failure scenario of the preview scenario
    - Reason: It is important in this case to highlight both the success and failure scenarios, as the failure scenario can be encountered quite easily

* No explanation as to the case in which a corrupted file is encountered
    - Decision: Ignore
    - Reason: This is a quite technical detail, and the answer is quite trivial. Obviously corrupted files can’t be opened and encountering a corrupted file would halt a subroutine.
* Technical details which are omitted from the functional view are also omitted in this view
    - Decision: Partially Address
    - Reason: The information view is meant to be at a high level of abstraction, therefore there is no incentive to include technical details omitted from the functional view, however as part of the traceability improvements there are more references to the control flow of certain processes in the codebase.
* There is no scenario
    - Decision: Completely Address
    - Reason: even though the view models a specific scenario, the failure scenario was indeed missing, and it has been added. 

# Deployment View:

### M2:

* I question whether this is the best choice, since it's a desktop app. Not clear if the view provides enough insights to justify the documentation [and...]
* In any case, given that choice, there was some opportunities to dig deeper, e.g., by detailing what the Poppler libraries are, their development status, and how to import dictionaries, etc. [and...]
* Some requirements are pretty obvious or not particularly relevant to TeXstudio
    - Decision: Focus on advanced feature that requires less trivial deployment
    - Reason: View as given in M2 was unfocused, too broad, too obvious - most things configured automatically by installer or at runtime.  Focus on LanguageTool integration, which requires non-trivial deployment
* Justification mentions compilation from source, but this concern is not addressed by the view
    - Decision: Focus scope of view to eliminate from-source installation
    - Reason: Very rare case that from-source installs will be conducted, instead focus on deployment scenario that has better chance of being used (LanguageTool)
