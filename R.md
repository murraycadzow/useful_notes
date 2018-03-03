
## rJava

A package I'm not fond of because of prior experience trying to get it to work

Fastest way (for ubuntu) is in bash:
```
sudo apt-get install r-cran-rjava
```
after installation you may need to run (in bash)
```
sudo R CMD javareconf
```

## knit Rmd from commandline

To be able to knit rmarkdown from cmd line R needs to know where pandoc lives (the special one that is bundled with rstudio)

Temporary way to fix:

Go into RStudio and find the system environment variable for RSTUDIO_PANDOC

```
Sys.getenv("RSTUDIO_PANDOC")
```
Then put that in your R script prior to calling the render command.
```
Sys.setenv(RSTUDIO_PANDOC="--- insert directory here ---")
```

The more permanant easy solution is to use soft-links (shortcuts) 

first soft link Rstudios pandoc:
Newer Systems (Debian/Ubuntu/Fedora/RHEL6+) 
For newer Linux systems you can make a standalone version of pandoc v1.12.3 available to the system by soft-linking the binaries included with RStudio:
```
sudo ln -s /usr/lib/rstudio/bin/pandoc/pandoc /usr/local/bin 
sudo ln -s /usr/lib/rstudio/bin/pandoc/pandoc-citeproc /usr/local/bin 
```

then to knit an Rmd from bash:
```
R CMD -e 'rmarkdown::render("input.Rmd")
```


## Multiple versions of R

Sometimes multiple versions of R might be installed, in which case you can tell rstudio which one to use by doing the following

run rstudio from cmd line with particular install of R:
```
export RSTUDIO_WHICH_R=/usr/local/bin/R
rstudio
```

## YAML header I often use for Rmd

Dual output and table of contents created on knit:

```
---
title: "title"
author: "name"
date: '`r format(Sys.Date())`'
output:
  pdf_document:
    toc: yes
  html_document:
    toc: yes
---
```
