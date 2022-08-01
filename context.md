# Systems:

Internal systems:
- None

External Systems:
- OS: File I/O, keyboard/mouse events, graphics
- LaTeX distribution

# Roles (stakeholders and systems):

Data Providers/Consumers:
- End User
- File System

Service providers/consumers:
- QT (GUI provider)
- Poppler (PDF viewer functionality provider)
- Phonon (Movie viewer functionality provider)
- TeX distribution (MiKTeX/TeX Live!) - TeX processing provider

Event providers/consumers:
- End User
- QT (consumes user GUI interaction events)




[UML Diagram](m1/uml.webp)

# General Description of the Context View Model: 

TeXStudio is downloaded and installed on a machine by some user. This user can give it input, in the form of text and numbers written in the editor. The user can also give TeXStudio commands such as Load and Save, compile, zoom in/out, etc. In return, TeXStudio will display the document the user is writing through the use of a pdf viewer, and it will give live feedback on what the user is writing through linting, which gives syntax and error highlighting.
The latex documents are saved on the file system on which TeXStudio is installed. TeXStudio can access these when saving or loading files. TeXStudio can also access installed Latex packages as well as its required dependencies (so that they can run as independent programs as we will see next).
When running, TeXStudio’s runtime dependencies are QT (to render the GUI), Poppler (to render pdfs) and Phonon (to play movies in the pdf viewer). TeXStudio will call the programs it needs for different functionalities.
Finally, a TeX distribution is required to run TeXStudio, since it does not come with one. This means that it must be installed from the user. Afterwards, TeXStudio will use it for compiling as well as linting.
