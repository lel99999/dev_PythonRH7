# dev_PythonRH7
Out of band Dev Python RHEL7

#### Update R packages from list
updpackages <- function(pkg){
            new.pkg <- pkg[!(pkg %in% installed.packages()[, "Package"])]
            if (length(new.pkg)) 
                install.packages(new.pkg, dependencies = TRUE)
            sapply(pkg, require, character.only = TRUE)
}

# invoke
newpackages <- c("depth","fma","manipulate","rstudio","TukeyC","ccpr","ccpusr","cfpbdesign","fastmap","lifecycle","metro2","microbenchmark","rlang","seasonal","tictoc","x13binary","class","dplyr","filestrings","ggplot2","ggseas","glmnet","gridExtra","lme4","magick","onehot","reshape2","zoo","devtools","mapproj","maps","shiny","digest","dummies","ellipsis","fastDummies","foreign","formattable","haven","insight","ISLR","kableExtra","nycflights13","pillar","popbio","questionr","rbenchmark","Rcpp","sjlabelled","stargazer","survey","tidyr","tidyverse","UScensus2010","vctrs","xtable","askpass","asserthat","BioGenerics","BioInstaller","callr","cbsa","ccdbr","clisymbols","CodeDepends","data.table","directlabels","dptemplate","dptemplate_old","drake","egg","evaluate","filelock","flextable","forcats","fs","fst_old","geofacet","ggjoy","gh","glue","here","highr","hms","httr","ini","IRanges","jsonlite","knitr","kpbkh","LaF","magrittr","markdown","mime","mintel","mondate","munsell","openssl","pkgbuild","pkgconfig","pkgload","processx","ps","purrr","R6""rcmdcheck","readr","remotes","ReporteRs","ReporteRsjars","rmarkdown","rocuments","rocx","rstudioapi","S4Vectors","scales","sessioninfo","stringi","stringr","sys","tibble","tidyselect","tinytex","txtq","usethis","xfun","xopen","yaml","bayestestR","effectsize","emmeans","ggeffects","glmmTMB","optiRun","parameters","performance","sjmisc","sjPlot","sjstats","TMB","anytime","backports","BH","blastula","blme","bridgesampling","brms","Brobdingnag","C50","captioner","cfpbdown","cfpbMail","checkmate,"cli","clipr","coda","colorspace","commonmark","cowplot","ctcats","curl","datapasta","devEMF","dygraphs","ebbr","emailr","enc","fansi","feather","flexdashboard","foreach","gamlss","gamlss.data","gamlss.dist","generics","geometry","ggwaffle","gtable","iterators","lazyeval","linprog","lintr","lobstr","lpSolve","madlibR","mailDown","merTools","nleqslv","patchwork","prettydoc","proxyC","quanteda","r2d3","rakeR","RcppArmadillo","recipes","rethinking","roxygen2md","rsvd","salesforcer","SnowballC","spacyr","spelling","stm","stopwords","stringdist","testthat","tidylo","treemap","tsibble","tuffe","waffle","webshot","xml2","xmlparsedata","ATE","cdiTools",


updpackages(newpackages)
