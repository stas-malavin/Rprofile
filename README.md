# Rprofile
.Rprofile for Linux console R

### Main features:
1. Saves everything (including libraries attached) in a file called "[DIRNAME].RProj" and history in a file called "[DIRNAME].RHist".
2. [DIRNAME].RProj being opened by R loads history, all the objects, and attaches back all the libraries, so that you can continue working without any stop.
3. Saving is available at any moment using ".allSave" function, as well as on exit using ".zz" function (salut vim). You may quit without saving anything using ".zq" function.
4. Custom wrapper to "savePlot" function is provided, which saves plots into "Rplots" folder inside working directory.
5. http://cran.rstudio.com is set as a default mirror.
