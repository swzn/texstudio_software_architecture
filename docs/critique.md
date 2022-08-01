# Critique 1: God Class Antipattern + Single Responsibility Principle

The Texstudio codebase contains a notable god class, namely the Texstudio class in texstudio.{cpp,h}. The scope of this class, which contains over 12,000 lines of code, is so large that in our Functional View, different parts of this class were assigned to entirely different functional elements. Certain sections of this class are considered to logically be part of the following functional elements, as described in our AD:
* Qt Widget
* GUI
* Previewer
* Persistence

This is of course a very common software antipattern. The main drawbacks of having a god class in a codebase is that it introduces tight coupling between the god class and all the other classes and methods it references or invokes, which is oftentimes unnecessary. Also, the existence of god classes makes the codebase as a whole less comprehensible to new developers and less maintainable, as minor refactoring can introduce a host of unintended consequences to unrelated parts of the program. 

An alternative approach would be to divide this class into different classes that have some sort of functional or logical connection, or in some cases merge parts of this class with other existing classes. This of course solves the god class problem, but would entail an increase in the number of classes in the codebase and increases the number of required header imports for most classes. However, the benefit is greatly increased readability and maintainability of the codebase, which is more important in the long-term. It would also give some insight as to the function of certain subroutines.

In general, this codebase would heavily benefit from some sort of code re-organization. The root src directory contains 97 .cpp files, and there is minimal organization into packages. The files at the root src directory are responsible for many different functions, and are often unrelated to each other. There is also no naming convention that would indicate that a certain file belongs to some logical element, which only furthers confusion for a new developer joining the project. 

An honorable mention in relation to classes that violate the single responsibility principle is the buildmanager.cpp class, which contains 2527 lines of code. This class controls various aspects of the ‘building’ process for documents (such as compilation, generating previews, setting up the environment, etc.), but also includes many implemented concurrency functions, which are at times confusingly named (example: BuildManager::firstProcessOfDirectExpansion). These functions are invoked from the texstudio class as well, and the texstudio class includes subroutines that are heavily linked to  and build upon the concurrency functions defined in the BuildManager class. We believe in terms of readability and maintainability, BuildManager can be broken down into multiple classes.


# Critique 2: Inappropriate intimacy

There are many instances of public class fields which are frequently accessed directly from methods in other classes.  This represents a substantial failure to encapsulate, and thus causes an undesirable dependency on the implementation of these classes, which could make refactoring quite difficult.

One example of this is the relationship between the Texstudio and ConfigManager classes.  Performing a REGEX search for ‘configManager.([A-Za-z0-9]+)(;|,|\)|\s+)’ in texstudio.cpp yields 192 results, indicating a lower bound of 192 direct accesses to ConfigManager fields.  It is most likely that there are many more cases of inappropriate intimacy throughout the code.

Should some implementation detail of ConfigManager be changed, it is possible that the Texstudio class would require a major refactoring in order to perform the same tasks.  Using setter & getter methods would mitigate the need to perform major refactoring in Texstudio, as the getter/setter methods can just be rewritten in a way that maintains the expected interface.  Of course code would need to be rewritten to use these new getters & setters, but this is a relatively simple task compared to large logical refactoring.
