## see help(Startup) for documentation on ~/.Rprofile and Rprofile.site

# options(width=65, digits=5)
# options(show.signif.stars=FALSE)
# setHook(packageEvent("grDevices", "onLoad"),
#         function(...) grDevices::ps.options(horizontal=FALSE))
# set.seed(1234)
.First <- function() {
	if (exists('.libs')) {
		cat('Reloading packages:',.libs,'\n')
		for (lib in .libs) library(lib, character = T)
	}
}
# .Last <- function()  cat("\n   Goodbye!\n\n")

local({
	old <- getOption("defaultPackages")
	r <- getOption("repos")
	r["CRAN"] <- "http://cran.rstudio.com"
	options(defaultPackages = c(old, "ggplot2"), repos = r)
})

.zz <- function() {
	.libs <<- .packages()
	save.image(paste0(basename(getwd()),'.Rproj'))
	savehistory(paste0(basename(getwd()),'.Rhist'))
	q('no')
}

.zq <- function() q('no')

.savePlot <- .plSave <- function(basename, ext = 'png') {
	if (!('Rplots' %in% dir())) dir.create('Rplots')
	if (missing(basename)) {
		suppressWarnings(if (grep('plot\\d{3}', dir('Rplots')) > 0) {
			t <- regmatches(dir('Rplots'), regexpr('plot\\d{3}', dir('Rplots')))
			t <- max(as.integer(regmatches(t, regexpr('\\d{3}', t))))
			basename <- paste0('plot', sprintf('%03.0f', t+1))
		} else basename <- 'plot001')
	}
	savePlot(file.path('Rplots', paste(basename, ext, sep = '.')))
}

.saveAll <- .allSave <- .f2 <- function() {
	.libs <<- .packages()
	save.image(paste0(basename(getwd()),'.Rproj'))
	savehistory(paste0(basename(getwd()),'.Rhist'))
}
