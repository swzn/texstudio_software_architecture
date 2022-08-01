TeXstudio's main audience are users who want to edit LaTeX documents "as easily and comfortably as possible" [1]. It expects users who have some prior knowledge of LaTeX (basic commands, high-level compilation process), but may want to use wizards for task automation, lookup symbols graphically, preview the result as you type, etc.  TeXstudio expects a TeX environment to be pre-installed (such as TeX Live!), so it is by no means a “full package” solution by itself (though such solutions may exist, such as the Flatpak package for Linux systems, but this is community-maintained).
These users have a powerful influence over the project as they want something that works and is easy to use.  Despite this influence, their interest is likely quite low as other LaTeX editors exist, and they could just decide not to use one altogether!

In a shared environment (such as a school computer lab), system administrators must be able to install the program in a manner that will yield a consistent experience for all users.  Fortunately, TeXstudio is able to automatically detect TeX distribution installations [2].
Since administrators need only run the installer (or unpack a portable archive), they have a low influence and low interest on the project.

As a free & open-source project [3], anyone is able to contribute to TeXstudio, be it through providing code, reporting issues, or improving documentation.
Code contributors may provide new features or bug fixes.  They have a high influence on the project since the code they write becomes the program that the users use.  They have high interest in the project since they want their code to be used in a beneficial way.
Issue reporters can range from regular users who’ve encountered a bug, to dedicated testers who hunt for bugs.  As some users may not care enough to report issues, issue reporters will have some greater level of interest in the project, and a greater level of influence since reported bugs should eventually be fixed.
Documentation contributors have significant experience using the program and want to help new users understand the software through high-quality documentation.  They have a high influence on the project as documentation quality can sway a user’s perception, and a high interest since they want to see the project succeed.

TeXstudio’s 4 project leaders [4] must vet all code contributions for quality and relevance, and determine if issue reports are worthwhile.  Without them, the project will stagnate as no changes to the source can be made.  They have high influence on the project and high interest.

Tabulated:

| Name | Class(es) | Details | Power | Interest |
| ---- | --------- | ------- | ----- | -------- |
| LaTeX document editors | Users | Edit LaTeX documents using the features present in the editor | Lower-High: If they find it infeasible to edit LaTeX using TeXstudio, the project would fail to meet its one goal | Low: Don’t care about the low-level details, just want to edit LaTeX and can use something else if they don’t like TeXstudio |
| Shared environment administrators | System administrators, production engineers | Install TeXstudio for shared use| Higher-Low: Take advantage of the TeX autodetection, but ultimately leave it alone | Low: Once installed, they’re pretty much done with it (except for regular updates) |
| Code contributors | Developers | Contribute features & bug fixes through code | High: Code becomes TeXstudio, large influence on capabilities & quality | High: Usually (if ever) aren’t paid to work on it.  Do so because they want to see improvements for themselves or the community |
| Documentation contributors | Communicators | Write documentation to help users navigate & use TeXstudio | High: Prevents users from walking away due to lack of understanding | “ |
| Issue reporters (another form of contributor) | Testers, users | Users & testers that encounter issues with TeXstudio and report them | High: Without issue reports, bugs may go undetected.  Stimulate code quality improvements | “ |
| Project leaders | Maintainers, acquirers, developers | Primary developers, vet PRs for quality | High: All contributions must be approved by them.  If they stop, the project stagnates | High: It’s their project, dedicate significant time to its progress |

![Power-Interest Matrix](m1/matrix.png)

[1]: TeXstudio - A LaTeX editor. n.d. _Welcome to TeXstudio_. [online] Available at: \< https://www.texstudio.org/#home > [Accessed 11 February 2022].

[2]: TeXstudio - A LaTeX editor. n.d. _Features_. [online] Available at: \< https://www.texstudio.org/#features > [Accessed 11 February 2022].

[3]: GitHub. 2022. _texstudio-org/texstudio_. [online] Available at: \< https://github.com/texstudio-org/texstudio > [Accessed 11 February 2022].

[4]: TeXstudio - A LaTeX editor. n.d. _About_. [online] Available at: \< https://www.texstudio.org/#about > [Accessed 11 February 2022].
