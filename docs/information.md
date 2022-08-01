# Information View

## Concerns

The Information View for TeXStudio represents the flow of data and how data is manipulated throughout the lifecycle of the program. We have identified a specific scenario that encapsulates many of the core responsibilities of TeXStudio, and found that modelling the data flows during this scenario would be crucial to understanding the architecture of the system as a whole. The preview scenario is responsible for the conversion of plain LaTeX text into graphical format and showing the generated document to the user. This helps highlight some of the most important data flows within the system, as well as between the system and its environment.

## Traceability

Since we are describing processes at a high-level of abstraction, we try to keep our description general, such that our findings remain true if minor refactorings take place. For the purpose of traceability, however, it should be noted that the following discussion of the preview scenario is based on the BuildManager::preview() subroutine, as it handles the invocation of necessary processes in order to generate the preview document. Where other subroutines are involved, they are explicitly named. 

## Model

The model we have chosen is the Gane Sarson Data Flow Diagram. This diagram shows data flows in the context of different processes; since TexStudio is a data processing program, understanding the order of processes and the data flows that each of them entail is important. 

There are three different types of entities modelled in this diagram. The first are functional elements, these are consistent with the functional view and are high-level abstractions of different architectural elements in the program. Secondly, we model processes, for which the numerical headings indicate their chronological order. Lastly, we model data stores, which are certain locations on the file system where related files are saved. We include a legend of the graphical representation of each of these entities:

![legend](m4/img/legend.png)


![diagram](m4/img/fig_2.png)


We do not concern ourselves with the manner in which these processes are invoked and only focus on the transfer of data within and outside of the system. To help highlight the system boundary, we have grouped all internal elements on the left of the diagram, and all external elements on the right. 

We see that for the preview scenario there are two separate local stores of files used by the program. The first, temp file store, is used to save and retrieve intermediate files for different stages of the LaTeX compile process. After parsed text is dumped into a .tex file, the compile command is invoked during which the TeX distribution on the machine reads the tex file produces a ‘.dvi’ file. The dvi output is stored in the temp file store, and is again converted into Previewer-compatible ‘.png’ format and saved in a separate directory where all preview files are stored. The Previewer then opens this file from the appropriate directory and displays it to the user. 

Since temporary and intermediary files have limited utility after the compilation process is completed, TeXStudio ensures that these files are deleted from the temp file store so as not to create bloat on the filesystem.

It is important to note that process 4.0 involves no data flow into the system. This is because the conversion of dvi files is delegated to an external system service, and the only data kept by the system to execute this operation is a pointer to the dvi file. In other words, the data from the dvi file is not read or altered by any of the internal elements of the system during the conversion process.  

## Scenario: Invalid LaTeX

An important alternative scenario to consider in the scope of the preview function is how the system handles invalid inputs. An invalid input refers to any raw text present in our source document that our TeX compiler is not able to ‘understand’. Fortunately, this scenario does not deviate heavily from our success scenario. In this case, we alter our initial Gane-Sarson diagram as such: 

 ![scenario-diagram](m4/img/fig_3.png)

As can be seen in the diagram, invalid LaTeX is not handled by the LatexParser or BuildManager, but rather by the compiler which is able to generate the appropriate error message to then be displayed to the user. This error information is stored in the .dvi file generated from the compile process. The main method responsible for the preview scenario (BuildManager::preview()) then detects that the compile process did not exit normally, after which processes related to creating the preview document are terminated.  

TeX compilation errors have to be parsed, formatted, and sent to the correct GUI element. This main data flow for this process is captured in process 4.0 on our new diagram. The main function controlling error parsing (Texstudio::viewLogorRerun()) reads the data from our .dvi file, formats the necessary messages, and updates the appropriate GUI element (in our case, LogWidget). 

