# Deployment view:

While most installations of TeXstudio are quite simple, there may arise situations where the user wants to use some advanced features.  We will focus on the scenario of using a remote LanguageTool server.

LanguageTool is a style & grammar checker that accepts requests from a built-in HTTP server.  When used, it provides TeXstudio with grammar checking hints in the form of squiggly blue underlines.  While TeXstudio can manage LanguageTool itself when run locally, some configuration is required when using a remote server instance.

LanguageTool is a Java program, and thus requires a JRE installation on the host you intend to run it on.  If using a remote instance of LanguageTool, you must have a network connection that can reach the server host.

If run locally, you must tell TeXstudio where it can find the LanguageTool JAR file, and it will execute the server automatically.
Otherwise, you must navigate to the configuration window, select the “Language Checking” tab, check “show advanced options”, and modify the “Server URL” entry to point to the LanguageTool server.

We can relate this back to our simplicity concern with the fact that configuring TeXstudio to use this remote LanguageTool server is very easy in that you need only make a quick configuration edit in the settings dialog.
