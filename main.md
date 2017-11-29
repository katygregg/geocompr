
--- 
title: 'Geocomputation with R'
author: 'Robin Lovelace, Jakub Nowosad, Jannes Muenchow'
date: '2017-11-29'
knit: bookdown::render_book
site: bookdown::bookdown_site
documentclass: book
bibliography:
  - refs.bib
  - packages.bib
biblio-style: apalike
link-citations: yes
description: "Forthcoming book on geographic data with R."
github-repo: "Robinlovelace/geocompr"
url: 'http\://robinlovelace.net/geocompr'
---



# Welcome {-}

Welcome to the [online home](http://robinlovelace.net/geocompr) of *Geocomputation with R*, a forthcoming book with [CRC Press](https://www.crcpress.com/Chapman--HallCRC-The-R-Series/book-series/CRCTHERSER).

## Development {-}

Inspired by [**bookdown**](https://github.com/rstudio/bookdown) and other open source projects we are developing this book in the open.
Why?
To encourage contributions, ensure reproducibility and provide access to the material as it evolves.

The book's development can be divided into four main phases:

1. Foundations
2. Basic applications
3. Geocomputation methods
4. Advanced applications

Currently the focus is on Part 2, which we aim to be complete by December.
New chapters will be added to this website as the project progresses, hosted at [robinlovelace.net/geocompr](http://robinlovelace.net/geocompr) and kept up-to-date thanks to [Travis](https://travis-ci.org/Robinlovelace/geocompr).
Currently the build is:

[![Build Status](https://travis-ci.org/Robinlovelace/geocompr.svg?branch=master)](https://travis-ci.org/Robinlovelace/geocompr) 

The version of the book you are reading now was built on 2017-11-29 and was built on [Travis](https://travis-ci.org/Robinlovelace/geocompr).

## How to contribute? {-}

**bookdown** makes editing a book as easy as editing a wiki, provided you have a GitHub account ([sign-up at github.com](https://github.com/)).
Once logged-in to GitHub, clicking on the 'edit me' icon highlighted in the image below will take you to the source [R Markdown](http://rmarkdown.rstudio.com/) where you can make changes:

[![](figures/editme.png)](https://github.com/Robinlovelace/geocompr/edit/master/index.Rmd)

To raise an issue about the book's content (e.g. code not running) or make a feature request, check-out the [issue tracker](https://github.com/Robinlovelace/geocompr/issues).

## Reproducibility {-}

To reproduce the book, you need a recent version of [R](https://cran.r-project.org/) and up-to-date packages, which can be installed with the following command (which requires [**devtools**](https://github.com/hadley/devtools)):


```r
devtools::install_github("robinlovelace/geocompr")
```

To build the book locally, clone or [download](https://github.com/Robinlovelace/geocompr/archive/master.zip) the [geocompr repo](https://github.com/Robinlovelace/geocompr/), load R in root directory (e.g. by opening [geocompr.Rproj](https://github.com/Robinlovelace/geocompr/blob/master/geocompr.Rproj) in RStudio) and run the following lines:


```r
bookdown::render_book("index.Rmd") # to build the book
browseURL("_book/index.html") # to view it
```

Further details can be found at [Robinlovelace/geocompr](https://github.com/Robinlovelace/geocompr#geocomputation-with-r).

# Preface {-}

This book is aimed at people who want to do spatial data analysis, visualization and modeling with a modern programming language (R).
There is no single target audience but we expect the book to be especially useful for:

- People who have learned spatial analysis skills using a desktop Geographic Information System (GIS) such as [QGIS](http://qgis.org/en/site/), [ArcMap](http://desktop.arcgis.com/en/arcmap/), [GRASS](https://grass.osgeo.org/) or [SAGA](http://www.saga-gis.org/en/index.html), who want access to a powerful (geo)statistical and visualization programming language and the benefits of a command-line approach [@sherman_desktop_2008]:

> With the advent of 'modern' GIS software, most people want to point and click their way through life. That’s good, but there is a tremendous amount of flexibility and power waiting for you with the command line.

- Graduate students and researchers from fields specializing in geographic data including Geography, Remote Sensing, Planning, GIS and Geographic Data Science
- Academics and post-graduate students working on projects in fields including Geology, Regional Science, Biology and Ecology, Agricultural Sciences (precision farming), Archaeology, Epidemiology, Transport Modeling, and broadly defined Data Science which require the power and flexibility of R for their research <!-- please add further fields-->
- Applied researchers and analysts in public, private or third-sector organisations who need the reproducibility, speed and flexibility of a command-line language such as R in applications dealing with spatial data as diverse as Urban and Transport Planning, Logistics, Geo-marketing (store location analysis) and Emergency Planning <!-- please add further examples-->

The book is designed to be accessible to a wide audience.
The chapters progress gradually in difficulty and exercises are provided at the end of each chapter to ensure understanding.
However, R novices may find the reproducible code chunks --- an integral part of the book --- difficult to understand and implement at first. 

Impatient readers are welcome to dive straight into the first practical examples in Chapter \@ref(spatial-class).
However we suggest most R beginners get up-to-speed with R before diving-in to chapters onwards (unless you're reading the book for an understanding of the concepts).
R has a supportive community that has developed a wealth of resources that can help here, three of which we highly recommend: [An introduction to R](http://colinfay.me/intro-to-r/) [@venables_introduction_2017],  [R for Data Science](http://r4ds.had.co.nz/) [@grolemund_r_2016] and [Efficient R Programming](https://csgillespie.github.io/efficientR/) [@gillespie_efficient_2016], especially [Chapter 2](https://csgillespie.github.io/efficientR/set-up.html#r-version) (on installing and setting-up R/RStudio) and [Chapter 10](https://csgillespie.github.io/efficientR/learning.html) (on learning to learn).
There are also many interactive resources, including DataCamp's [Introduction to R](https://www.datacamp.com/courses/free-introduction-to-r) and tutorials created with [**learnr**](https://rstudio.github.io/learnr/examples.html).

With such material to hand we are confident that the command-line approach demonstrated in this book will be worthwhile within a few months for most people, including programming novices.
Over time and with practice R will likely become the natural choice for many geographic applications.
We expect you will eventually find its interface faster than the point-and-click interface emphasized in many desktop GISs.
For some applications such as Spatial Statistics and modelling R may be the *only* realistic way to get the work done.

As outlined in section \@ref(why-geocomputation-with-r) there are many reasons for using R for geocomputation:
R is well-suited to the interactive use required in many geographic data analysis workflows compared with other languages.
R excels in the rapidly growing fields of Data Science (which includes data carpentry, statistical learning techniques and data visualization) and (via efficient interfaces to databases and distributed computing systems) Big Data.

For some applications another language may be more appropriate, such as Python, Java or C++.
There are excellent resources for learning geocomputation *without R*, as discussed in section \@ref(software-for-geocomputation).
However we advocate learning one language (R) in *depth* to gain an understanding of the concepts.
Proficiency with one programming language is preferable to the *breadth* of knowledge (and potential for confusion) attainable by dabbling with many.

We believe that *Geocomputation with R* will equip you with the knowledge and skills needed to solve the majority of challenges that geographic data pose.
A logical question to ask if you've read this far may be: what *is* geocomputation anyway?
The answer is provided in section \@ref(what-is-geocomputation) which, alongside the rest of Chapter \@ref(intro), explains the motivations behind this book.

<!-- to think about, not sure if needed but then this would be a good place to point out why our book might have advantages over other books. Compare with:
- Bivand, R., Pebesma, E., Gomez-Rubio, V. (2013): Applied spatial data analysis with R.
- Blangiardo, M. & Cameletti, M. (2015): Spatial and spatio-temporal Bayesian models with R - INLA.
- Brunsdon, C. & Comber, L. (2015): An introduction to R for spatial analysis and mapping.
- Dorman, M. (2014): Learning R for geospatial analysis.
- Hijmans, R. (2016): Spatial data analysis and modeling with R.  http://rspatial.org/intr/index.html (haven't read it but might be more suitable for beginners, however, it does not consider sf; additionally, it provides more code than text, and hence, probably less explanations than our book) 
- Quiang, S. (2016): Environmental and Ecological Statistics with R (not really a competitor, I have ordered a copy, this book is really about modeling, and I would rather prefer the Zuur et al. books over it)
- Wegmann, M., Leutner, B., Dech, S. (2016): Remote Sensing and GIS for ecologists: Using Open Source Software.
- Zuur, A., Ieno, E., Saveliev, A. (2017): Beginner's guide to spatial, temporal and spatial-temporal ecological data analysis with R-INLA.

Put the competing books into categories, e.g., introduction to spatial analysis (Brundsdon, Dorman, Hijmans), advanced spatial analysis (Bivand), topical spatial analysis (Quiang, Wegmann),  (mainly) spatial modeling (Bivand, Blangiardo, Hijmans, Quiang, Zuur).
Point out where our book fits in and which gap it is filling -> somewhere between advanced (but not that hard) and spatial modeling with a broad range of topics (not just one like ecology).
We try to address a broad audiecence with an interest in spatial data, and how things can be **get done**, not just theoretically but in an applied way.
On the other hand, we embed the shown methods into the bigger field of GIScience, provide context and refer to further literature for the interested reader.

-->

<!-- ## Acknowledgements {-} -->
<!-- add list of people who helped with this book -->

<!--chapter:end:index.Rmd-->


# (PART) Foundations {-}

# Introduction {#intro}

This book is about harnessing the power of modern computers to *do things* with geographic data.
It teaches a range of spatial skills, including: reading, writing and manipulating geographic data; making static and interactive maps; applying geocomputation to solve real-world problems; and modeling geographic phenomena.
By demonstrating how various spatial operations can be linked, in reproducible 'code chunks' that intersperse the prose, the book also teaches a transparent and thus scientific workflow.
Learning how to use the wealth of geospatial tools available from the R command line can be exciting but creating *new ones* can be truly liberating, by removing constraints on your creativity imposed by software.
By the end of the book you should be able to create new tools for geocomputation in the form of shareable R scripts and functions.

Over the last few decades free and open source software for geospatial data ('FOSS4G') has progressed at an astonishing rate (see [foss4g.org](http://foss4g.org/)).
Thanks to FOSS4G and the wider open source movement geospatial analysis is no longer the preserve of those with expensive hardware and software: anyone can now download high performance spatial libraries on their computer.
However, despite the growth of geospatial software that is *open source*, much of it is still not easy to script.
Open source Geographic Information Systems (GIS) such as QGIS (see [qgis.org](http://qgis.org/en/site/)) have greatly reduced the 'barrier to entry' have an emphasis on the Graphical User Interface (GUI) rather than the Command-Line Interface (CLI).
This GUI-centred approach can discourage reproducibility.
This book focusses exclusively on the CLI, enabling reproducible, and 'computational' workflows, something we will expand on in Chapter 13.
<!--\@ref(gis) --><!-- REF NEEDS TO BE FIXED IN FUTURE-->

\BeginKnitrBlock{rmdnote}<div class="rmdnote">Reproducibility is a major advantage of command-line interfaces, but what does it mean in practice?
We define it as follows:

> A process is reproducible only if the same results can be generated by others using publicly accessible code.

This may sound simple and easy to acheive (which it is if you carefully maintain your R code in script files) but has profound implications for teaching and the scientific process [@pebesma_r_2012].</div>\EndKnitrBlock{rmdnote}

A major aim of this book is to make geographic data analysis more accessible as part of a reproducible workflow.
R is a flexible language that allows access to many spatial software libraries (see section \@ref(why-geocomputation-with-r)).
Before going into the details of the software, however, it is worth taking a step back and thinking about what we mean by geocomputation.

## What is geocomputation?

Geocomputation is a relatively young field with a ~30 year history, dating back to the first conference on the subject in 1996.^[The conference took place at the University of Leeds, where one of the authors (Robin) is currently based and where the 21^st^ GeoComputation was hosted in 2017 (see
[geocomputation.org](http://www.geocomputation.org/)).]
<!-- todo: which chapters? -->
What distinguishes geocomputation from the older quantitative geography, is its emphasis on "creative and experimental" GIS applications [@longley_geocomputation:_1998].
Additionally, it is also about developing new, research-driven methods [@openshaw_geocomputation_2000]:

> GeoComputation is about using the various different types of geodata and about
developing relevant geo-tools within the overall context of a 'scientific'
approach.

But geocomputation and this book teach more than just methods and code: they are about *doing* "practical work that is beneficial or useful" [@openshaw_geocomputation_2000].
Of course, reading this book will give you a solid *knowledge* of geocomputational methods, and how to use them via the reproducible examples implemented in the code chunks in each chapter.
But there is much more.
This book aims to teach how to do geocomputation rather than just to think about it.
Hence, you should be also able to apply the learned methods and mastered skills to real-world data, for evidence-based analysis in your own areas of interest.
Moreover, throughout the book we encourage you to make geographic research more reproducible, scientific and socially beneficial. 

This book is also related to a movement that has been labelled Geographical Information Science (GDS).
This recent concept essentially combines 'data science' with GIS and, like Geocomputation, can be defined in comparison with GIS (see Table \@ref(tab:gdsl)).
The focus on reproducibility and a command-line interface in this book is aligned with GDS.


Table: (\#tab:gdsl)Differences in emphasis between the fields of Geographic Information Systems (GIS) and Geographic Data Science (GDS).

Attribute          GIS                        GDS                              
-----------------  -------------------------  ---------------------------------
Home disciplines   Geography                  Geography, Computing, Statistics 
Software focus     Graphical User Interface   Code                             
Reproduciblility   Minimal                    Maximal                          

While embracing recent developments in the field, we also wanted to pay respects to the wider field of Geography, with its 2000 history [@roller_eratosthenes_2010], and the narrower field of *Geographic Information System* (GIS) [@neteler_open_2008].
Geography has played an important role in explaining and influencing humanity's relationship with the natural
world^[A good example of this is Alexander von Humboldt's travels to South America, which laid the foundations for physical and plant geography [@wulf_invention_2015].
]
and this book aims to contribute to this so-called 'Geographic Tradition' [@livingstone_geographical_1992].
GIS has become almost synonymous with handling spatial data on a computer, and provides a basis for excellent open source tools which can be accessed from R, as we will see in Chapter 13.
<!-- todo - add dynamic reference to c13-->

The book's links to older disciplines were reflected in suggested titles for the book: *Geography with R* and *R for GIS*.
Each has advantages.
The former conveys the message that it comprises much more than just spatial data: 
non-spatial attribute data are inevitably interwoven with geometry data, and Geography is about more than where something is on the map.
The latter communicates that this is a book about using R as a GIS, to perform spatial operations on *geographic data* [@bivand_applied_2013].
However, the term GIS conveys some connotations (see Table \@ref(tab:gdsl)) which simply fail to communicate one of R's greatest strengths:
its console-based ability to seamlessly switch between geographic and non-geographic data processing, modeling and visualization tasks.
By contrast, the term geocomputation implies reproducible and creative programming.
Of course, (geocomputational) algorithms are powerful tools that can become highly complex.
However, all algorithms are composed of smaller parts.
By teaching you its foundations and underlying structure, we aim to empower you to create your own innovative solutions to geographic data problems.

## Why Geocomputation with R?

Early geographers used a variety of tools including rulers, compasses and sextants to advance knowledge about the world. 
However, until John Harrison invented the marine chronometer in the 18th century it had been impossible to determine the exact longitude at sea ('the longitude problem').
Prior to his invention ships followed for centuries a line of constant latitude making each journey much longer, more expensive and often also more dangerous.
Nowadays this seems unimaginable with every smartphone having a GPS receiver at its disposal.
And there are a multitude of other sensors measuring the world in real-time (satellites, radar, autonomous cars, citizens, etc.).
For instance, an autonomous car could create 100 GB or more per day (see e.g., this [article](https://www.economist.com/news/science-and-technology/21696925-building-highly-detailed-maps-robotic-vehicles-autonomous-cars-reality)).
Equally, earth observation data (satellite imagery) has become so big that it is impossible to analyze the corresponding data with a single computer (see [http://r-spatial.org/2016/11/29/openeo.html](http://r-spatial.org/2016/11/29/openeo.html)).
Hence, we need computational power, software and related tools to handle and extract the most interesting patterns of this ever-increasing amount of (geo-)data.
(Geo-)Databases help with data management, storing and querying such large amounts of data.
Through interfaces we can access subsets of these data for further analysis, information extraction and visualization.
In this book we treat R as a 'tool for the trade' for the latter.

R is a multi-platform, open source language and environment for statistical computing and graphics ([https://www.r-project.org/](https://www.r-project.org/)).
With a wide range of packages R also supports advanced geospatial statistics, modeling and visualization.^[The integrated development environment (IDE) [RStudio](https://www.rstudio.com/) deserves mention here from a user perspective as it has made the interactive use of R more accessible].
At its core R is an object-oriented, [functional programming language](http://adv-r.had.co.nz/Functional-programming.html) [@wickham_advanced_2014], and was specifically designed as an interactive interface to other software [@chambers_extending_2016]. 
The latter also includes many 'bridges' to a treasure trove of GIS software, geolibraries and functions.
<!-- todo - add this reference to ref(gis) -->
It is thus ideal for quickly creating 'geo-tools', without needing to master lower level languages (compared to R) such as C, FORTRAN and Java (see section \@ref(software-for-geocomputation)). 
This can feel like breaking free from the metaphorical 'glass ceiling' imposed by GUI-based proprietary geographic information systems (see Table \@ref(tab:gdsl) for a definition of GUI).
What is more, advanced users might even extend R with the power of other languages (e.g., C++ through **Rcpp** or Python through **reticulate**; see also section \@ref(software-for-geocomputation)).

An example showing R's flexibility with regard to geographic software development is its support for generating interactive maps thanks to **leaflet** [@R-leaflet].
The packages **tmap** and **mapview** [@R-tmap; @R-mapview] are built on and extend **leaflet**.
These packages help overcome the criticism that R has "limited interactive [plotting] facilities" [@bivand_applied_2013]. 
The code below illustrates this by generating Figure \@ref(fig:interactive).




```r
library(leaflet)
popup = c("Robin", "Jakub", "Jannes")
leaflet() %>%
  addProviderTiles("NASAGIBS.ViirsEarthAtNight2012") %>% 
  addAwesomeMarkers(lng = c(-3, 23, 11),
                    lat = c(52, 53, 49), 
                    popup = popup)
```

<div class="figure" style="text-align: center">
preserve0f108e877afe5455
<p class="caption">(\#fig:interactive)World at night imagery from NASA overlaid by the authors' approximate home locations to illustrate interactive mapping with R.</p>
</div>

It would have been difficult to produce Figure \@ref(fig:interactive) using R a few years ago, let alone embed the results in an interactive html page (the interactive version can be viewed at [robinlovelace.net/geocompr](http://robinlovelace.net/geocompr/intro.html)).
This illustrates R's flexibility and how, thanks to developments such as **knitr** and **leaflet**, it can be used as an interface to other software, a theme that will recur throughout this book.
The use of R code, therefore, enables teaching geocomputation with reference to reproducible examples such as that provided in \@ref(fig:interactive) rather than abstract concepts.

## Software for geocomputation

R is a powerful language for geocomptation but there are many other options for spatial data analysis.
Awareness of these will help situate R in the wider geospatial ecosystem, and identify when a different tool may be more appropriate for a specific task.
Over time R developers have added various R interfaces (or 'bridges' as we call them in Chapter 13) to other software.
Therefore knowing what else is out there can also be useful from an R-spatial perspective because a) there may already be a bridge to something that adds the functionality you need and b) if there's not already a bridge there may be on the horizon.
With this motivation in mind the section briefly introduces the languages [C++](https://isocpp.org/), [Java](https://www.oracle.com/java/index.html) and [Python](https://www.python.org/) for geocomputation, with reference to R.

A natural choice for geocomputation would be C++ since major GIS packages (e.g., [GDAL](http://www.gdal.org/), [QGIS](www.qgis.org), [GRASS](https://grass.osgeo.org/), [SAGA](www.saga-gis.org), and even [ArcGIS](https://www.arcgis.com/)) often rely in great parts on it.
This is because well-written C++ can be blazingly fast, which makes it a good choice for performance-critical applications such as the processing of large spatial data.
Usually, people find it harder to learn than Python or R.
It is also likely that you have to invest a lot of time to code things that are readily available in R.
Therefore, we would recommend to learn R, and subsequently to learn C++ through **Rcpp** if a need for performance optimization arises.
Subsequently, you could even implement geoalgorithms you are missing from the most common desktop GIS with the help of **Rcpp**^[Though, in that case we would recommend to contribute the C++ code to one of the open-source GIS packages since this would make the geoalgorithm available to a wider audience.
In turn, you could access the GIS software via one of the available R-GIS interfaces. <!--(ref(gis))-->].

Java is another important (and versatile) language used in GIScience.
For example, the open-source desktop GIS [gvSig](http://www.gvsig.com/en/products/gvsig-desktop), [OpenJump](http://openjump.org/) and [uDig](http://udig.refractions.net/) are written in Java.
There are also many open source add-on libraries available for Java, including [GeoTools](http://docs.geotools.org/) and the [Java Topology Suite](https://www.locationtech.org/projects/technology.jts).^[Please note, that GEOS is a C++ port of the Java Topology Suite.]
Furthermore, many server-based applications use Java including among others [Geoserver/Geonode](http://geonode.org/), [deegree](http://www.deegree.org/) and [52°North WPS](http://52north.org/communities/geoprocessing/wps/).

Java's object-oriented syntax is similar to that of C++ but its memory management, at least from a user's perspective, is simpler and more robust.
Java is rather unforgiving regarding class, object and variable declarations, which encourages well-designed programming structure, useful in large projects with thousands of lines of codes placed in numerous files.
Following the *write once, run anywhere* principle, Java is platform-independent (which is unusual for a compiled language) and has excellent performance on large-scale systems.
This makes Java a suitable language for complex architecture projects such [RStudio](https://github.com/rstudio/rstudio), the Integrated Development Environment (IDE) in which this book was written!

Java is less suitable for statistical modeling and visualization than Python or R.
Although Java can be used for data science [@brzustowicz_data_2017], it has relatively few statistical libraries, especially compared with R.
Furthermore Java is hard to use interactively.
Interpreted languages (such as R and Python) are better suited for the type of interactive workflow used in many geographic workflows than compiled languages (such as Java and C++).
Unlike Java (and most other languages) R has native support for data frames and matrices, making it especially well suited for (geographic) data analysis.

Python is the final language for geocomputation that deserves attention in this section.
Like R, Python has gained popularity due to the rapid growth of data science [@robinson_impressive_2017].
Both languages are object-oriented, and have lots of further things in common.
Due to their similarities there is much on-line discussion framing the relative merits of each language as a competition, as exemplified by an [infographic](https://www.datacamp.com/community/tutorials/r-or-python-for-data-analysis) by DataCamp titled "DATA SCIENCE WARS: R vs Python", which arguably generates more heat than light.

In practice both languages have their strengths and to some extent which you use is less important than domain of application and the communication of results.
Learning either will provide a head-start in learning the other.
However there are major advantages of R over Python for geocomputation which explains its prominence in this book.
R has unparalled support for statistics, including spatial statistics, with hundreds of packages (unmatched by Python) supporting thousands of statistical methods.

The major advantage of Python is that it is a *general-purpose* programming language.
It is well-suited to many applications, including desktop software, computer games, websites and data science.
R, by contrast, is primarily suited to the latter, under a broad definition of data science.^[R
has been extended in various directions, notably in  **shiny**, a package for developing interactive we applications in R.]
This also explains Python's larger user base compared with R's.
Python is often the only shared language between different (geocomputation) communities, explaining why it has become the 'glue' that holds many GIS programs together.
Many geoalgorithms, including those in QGIS and ArcMap, can be accessed from the Python command line, making it well-suited as a starter language for command-line GIS.^[Python modules providing access to geoalgorithms include `grass.script` for GRASS (https://grasswiki.osgeo.org/wiki/GRASS_and_Python), `saga-python` for SAGA-GIS (http://saga-python.readthedocs.io/en/latest/), `processing` for QGIS and `arcpy` for ArcGIS.
]

For spatial statistics and predictive modeling, however, R is second-to-none.
This does not mean you must chose either R or Python: Python supports most common statistical techniques (though R tends to support new developments in spatial statistics earlier) and many concepts learned from Python can be applied to the R world.
Like R Python also supports spatial data analysis and manipulation with packages such as **osgeo**, **Shapely**, **NumPy** and **PyGeoProcessing** [@garrard_geoprocessing_2016].

## R's spatial ecosystem

Before cracking-on with the action, a few introductory remarks are needed to explain the approach taken here and provide context.
<!-- paragraphs (with references to chapters in the book): -->
<!-- 1. this book focus -> sf + raster/stars + leaflet/mapview (the recent state of spatial R); the history of R spatial is way longer -->

There are many ways to handle spatial data in R, with dozens of packages in the area.^[An overview of R's spatial ecosystem can be found in the CRAN Task View on the Analysis of Spatial Data
(see [cran.r-project.org/web/views/Spatial.html](https://cran.r-project.org/web/views/Spatial.html)).]
In this book we endeavor to teach the state-of-the-art in the field whilst ensuring that the methods are future-proof.
Like many areas of software development, R's spatial ecosystem is rapidly evolving.
Because R is open source, these developments can easily build on previous work, by 'standing on the shoulders of giants', as Isaac Newton put it in [1675](http://digitallibrary.hsp.org/index.php/Detail/Object/Show/object_id/9285).
This approach is advantageous because it encourages collaboration and avoids 'reinventing the wheel'.
The package **sf** (covered in Chapter \@ref(spatial-class)), for example, builds on its predecessor **sp**.

A surge in development time (and interest) in 'R-Geo' has followed the award of a grant by the R Consortium for the development of support for Simple Features, an open-source standard and model to store and access vector geometries. 
This resulted in the **sf** package (covered in \@ref(intro-sf)).
Multiple places reflect the immense interest in **sf**. This is especially true for the [R-sig-Geo Archives](https://stat.ethz.ch/pipermail/r-sig-geo/), a long-standing open access email list containing much R-spatial wisdom accumulated over the years.
Many posts on the list now discuss **sf** and related packages, suggesting that R's spatial software developers are using the package and, therefore, it is here to stay.

We even propose that the release of **sf** heralds a new era for spatial data analysis and geocomputation in R.
This era ^[We refrain from labeling it the **geoverse** with any seriousness awaiting a better name!] clearly has the wind in its sails, and is set to dominate future developments in R's spatial ecosystem for years to come.
So time invested in learning the 'new ways' of handling spatial data and, hopefully, reading this book, is well spent!

<div class="figure" style="text-align: center">
<img src="figures/spatial-package-growth.png" alt="The popularity of spatial packages in R. The y-axis shows the average number of downloads, within a 30-day rolling window, of R's top 5 spatial packages, defined as those with the highest number of downloads within the last 30 days." width="1050" />
<p class="caption">(\#fig:cranlogs)The popularity of spatial packages in R. The y-axis shows the average number of downloads, within a 30-day rolling window, of R's top 5 spatial packages, defined as those with the highest number of downloads within the last 30 days.</p>
</div>

It is noteworthy that shifts in the wider R community, as exemplified by the data processing package **dplyr** (released in [2014](https://cran.r-project.org/src/contrib/Archive/dplyr/)) influenced shifts in R's spatial ecosystem. 
Alongside other packages that have a shared style and emphasis on 'tidy data' (including e.g., **ggplot2**), **dplyr** was placed in the **tidyverse** 'metapackage' in late [2016](https://cran.r-project.org/src/contrib/Archive/tidyverse/).
The **tidyverse** approach, with its focus on long-form data and fast, intuitively named functions, has become immensely popular.
This has led to a demand for 'tidy spatial data' which has been partly met by **sf** and other approaches such as **tabularaster**.
An obvious feature of the **tidyverse** is the tendency for packages to work in harmony.
Although an equivalent **geoverse** is presently missing, there is an on-going discussion of harmonizing R's many spatial packages^[
See the [r-spatial](https://github.com/r-spatial/) organisation and conversations in the [discussion](https://github.com/r-spatial/discuss/issues/11) repo for more on this.
] and a growing number of actively developed packages which are designed to work in harmony with **sf** (Table \@ref(tab:revdep)). 


Table: (\#tab:revdep)The top 5 most downloaded packages that depend on sf, in terms of average number of downloads per day over the previous month. As of 2017-11-27 there are 44 packages which import sf.

package      Downloads
----------  ----------
plotly            1915
raster            1762
spdep             1088
leaflet            736
geojsonio          413

## The history of R-spatial

There are many benefits of using recent spatial packages such as **sf**, as advocated in this book.
However it is also important to be aware of the history of R's spatial capabilities: many functions, use-cases and teaching material are contained in older packages.
These can still be useful today, provided you know where to look.

R's spatial capabilities originated in early spatial packages in the S language [@bivand_implementing_2000].
The 1990s saw the development of numerous S scripts and a handful of packages for spatial statistics.
R packages arose from these and by 2000 there were R packages for various spatial methods "point pattern analysis, geostatistics, exploratory spatial data analysis and spatial econometrics", according to an [article](http://www.geocomputation.org/2000/GC009/Gc009.htm) presented at GeoComputation2000  [@bivand_open_2000]
Some of these, notably **spatial**, **sgeostat** and **splancs** are still available on CRAN [@rowlingson_splancs:_1993; @rowlingson_splancs:_2017;@venables_modern_2002; @university_sgeostat:_2016].

A subsequent article in R News (the predecessor of [The R Journal](https://journal.r-project.org/)) contained an overview of spatial statistical software in R at the time, much of which was based on previous code written for S/S-PLUS [@ripley_spatial_2001].
This overview described packages for spatial smoothing and interpolation (e.g., **akima**, **spatial**, **sgeostat** and **geoR**) and point pattern analysis [**splancs** and **spatstat**; @akima_akima:_2016; @rowlingson_splancs:_2017; @jr_geor:_2016].
<!-- there is something wrong with the citation: Jr and Diggle 2016 (@jr_geor:_2016)-->
While all these are still available on CRAN, **spatstat** stands out among them, as it remains dominant in the field of spatial point pattern analysis [@baddeley_spatial_2015].

The following R News issue (Volume 1/3) put spatial packages in the spotlight again, with an introduction to **splancs** and a commentary on future prospects regarding spatial statistics [@bivand_more_2001].
Additionally, the issue introduced two packages for testing spatial autocorrelation that eventually became part of **spdep** [@bivand_spdep:_2017].
Notably, the commentary mentions the need for standardization of spatial interfaces, efficient mechanisms for exchanging data with GIS, and handling of spatial metadata such as coordinate reference systems (CRS).

**maptools** [written by Nicholas Lewin-Koh; @bivand_maptools:_2017] is another important package from this time.
Initially, **maptools** just contained a wrapper around [shapelib](http://shapelib.maptools.org/), and permitted the reading of ESRI Shapefiles into geometry nested lists. 
The corresponding and nowadays obsolete S3 class called "Map" stored this list alongside an attribute data frame. 
The work on the "Map" class representation was nevertheless important since it directly fed into **sp** prior to its publication on CRAN.

In 2003, @hornik_approaches_2003 published an extended review of spatial packages. 
Around this time the development of R's spatial capabilities increasingly supported interfaces to external libraries, especially to GDAL and PROJ.4.
These interfaces facilitated geographic data I/O (covered in chapter \@ref(read-write)) and CRS transformations, respectively.
@hornik_approaches_2003 proposed a spatial data class system, including support for points, lines, polygons and grids based on GDAL's support for a wide range of spatial data formats.
All these ideas contributed to the packages **rgdal** and **sp**, which became the foundational packages for spatial data analysis with R [@bivand_applied_2013].

**rgdal** provided GDAL bindings for R which greatly extended R's spatial capabilities in terms of access to previously unavailable spatial data formats.
Initially, Tim Keitt released it in 2003 with support for raster drivers.
But soon, **rgdal** also enabled storing information about coordinate reference system (building on top of the PROJ.4 library), allowed map projections, datum transformations and OGR vector reading. 
Many of these additional capabilities were thanks to Barry Rowlingson who folded them into the **rgdal** codebase in March 2006.^[A presentation at the 2003 DSC conference in Vienna gives the background as he saw it then [@rowlingson_rasp:_2003]; see also his announcement of the **Rmap** package on [R-help](https://stat.ethz.ch/pipermail/r-help/2003-January/028413.html) in early 2003.]

**sp**, released in 2005, overcame R's inability to distinguish spatial and non-spatial objects [@pebesma_classes_2005].
It grew from a [workshop](http://spatial.nhh.no/meetings/vienna/index.html) before, and a session at the 2003 DSC conference in Vienna, gathering input from most interested package developers. 
At the same time, [sourceforge](https://sourceforge.net/) was chosen for development collaboration (migrated to [R-Forge](https://r-forge.r-project.org) five years later) and the [R-sig-geo mailing list](https://stat.ethz.ch/mailman/listinfo/r-sig-geo) was started.

Prior to 2005, spatial coordinates were generally treated as any other number. 
This changed with **sp** as it provided generic classes and methods for spatial data.
The sophisticated class system supported points, lines, polygons and grids, with and without attribute data. 

<!--???-->
<!-- points, multipoints, pixels, full grid, line, lines, spatial lines, polygon, polygons, spatial polygons -->
Making use of the S4 class system, **sp** stores each piece of 'spatially specific' information (such as bounding box, coordinate reference system, attribute table) in slots, which are accessible via the `@` symbol.
For instance, **sp**-classes store attribute data in the `data` slot as a `data.frame`.
This enables non-spatial data operations to work alongside spatial operations (see section \@ref(why-simple-features)).
Additionally, **sp** implemented generic methods for spatial data types for well-known functions such as `summary()` and `plot()` .

In the following, **sp** classes rapidly became the go-to standard for spatial data in R, resulting in a proliferation of packages that depended on it from around 20 in 2008 and over 100 in 2013 [@bivand_applied_2013].
Now more than 450 packages rely on **sp**, making it an important part of the R ecosystem. 
<!-- https://github.com/Robinlovelace/geocompr/issues/58 -->
<!-- https://github.com/edzer/sfr/issues/387#issuecomment-308949140 -->

Prominent R packages using **sp** include: **gstat**, for spatial and spatio-temporal geostatistics; **geosphere**, for spherical trigonometry; and **adehabitat** used for the analysis of habitat selection by animals [@R-gstat; @calenge_package_2006; @hijmans_geosphere:_2016].

While **rgdal** and **sp** solved many spatial issues, R was still lacking geometry calculation abilities.
Therefore, Colin Rundel started to develop a package that interfaces GEOS, an open-source geometry library, during a Google Summer of Coding project in 2010.
The resulting **rgeos** package [first released in 2010; @R-rgeos] brought geometry calculations to R by allowing functions and operators from the GEOS library to manipulate **sp** objects.
Another limitation of **sp** was its limited support of raster data.
The **raster**-package [first released in 2010; @R-raster] overcame this by providing `Raster*` classes and functions for creating, reading and writing raster data.
A key feature of **raster** is its ability to work with datasets that are too large to fit into the main memory (RAM), thereby overcoming one of R's major limitations when working on large raster data.^[The
**raster** package also provided tools for raster algebra, general raster functions and the development of more additional raster functions.]

In parallel with or partly even preceding the development of spatial classes and methods came the support for R as an interface to dedicated GIS software.
The **GRASS** package [@bivand_using_2000] and follow-on packages **spgrass6** and **rgrass7** (for GRASS GIS 6 and 7, respectively) were prominent examples in this direction [@bivand_spgrass6:_2016;@bivand_rgrass7:_2016].
Other examples of bridges between R and GIS include **RSAGA** [@R-RSAGA, first published in 2008], **ArcGIS** [@brenning_arcgis_2012, first published in 2008], and **RQGIS** [@R-RQGIS, first published in 2016].
<!-- More information about interfaces between R and GIS software could be find in ref(gis). -->

Map making was not a focus of R's early spatial capabilities.
But soon **sp** provided methods for advanced map making using both the base and lattice plotting system. 
Despite this, a demand for the layered grammar of graphics was growing especially after the release of **ggplot2** in 2007.
**ggmap** extended **ggplot2**'s spatial capabilities [@kahle_ggmap:_2013].
However, its main purpose was the easy access of several APIs to automatically download map tiles (among others, Google Maps and OpenStreetmap) and subsequent plotting of these as a basemap. 
<!--Additionally, *ggmap** lets you use (mainly Google's) geocoding and routing services.-->
Though **ggmap** facilitated map-making with **ggplot2**, one main limitation remained.
To make spatial data work with the **ggplot2** system, one needed to `fortify` spatial objects.
Basically, this means, you need to combine the coordinates and attribute slots of a spatial class object into one data frame.
While this works well in the case of points, it duplicates the same information over and over again in the case of polygons, since each coordinate (vertex) of a polygon receives the attribute data of the polygon.
This is especially disadvantageous if you need to deal with tens of thousands of polygons.
With the introduction of simple features to R this limitation disappears, and it seems likely that this will make **ggplot2** the standard tool for the visualization of vector data. 
This might be different regarding the visualization of raster data. Raster visualization methods received a boost with the release of **rasterVis** [@lamigueiro_displaying_2014] which builds on top of the lattice system.
More recently, new packages aim at easing the creation of complex, high-quality maps with minimal code.
The **tmap** package (released in 2014) might serve as an archetype for this kind of development [@R-tmap].
It facilitates the user-friendly creation of thematic maps with an intuitive command-line interface (see also [**mapmisc**](https://cran.r-project.org/package=mapmisc)) . 
<!-- ADD THIS LATTER -->
<!-- CITE the paper Tennekes, M. (2017) tmap: Thematic Maps in R. Forthcoming in the Journal
of Statistical Software http://von-tijn.nl/tijn/research/presentations/tmap_user2017.pdf-->
**tmap** is a sophisticated yet user friendly mapping package which works in harmony with the **leaflet** package (released in 2015) for interactive map making [@R-leaflet]. 
Similarly, the **mapview** package builds also on top of **leaflet** [@R-mapview] for interactive mapping based on **sp** or **sf** objects. **mapview** allows the access of a wide range of background maps, scale bars and more.

However, it is noteworthy that among all the recent developments described above, the support for simple features [**sf**; @R-sf] has been without doubt the most important evolution in R's spatial ecosystem.
Naturally, this is the reason why we will describe **sf** in detail in Chapter \@ref(spatial-class).

<!-- ## How to read this book -->

## Exercises

1. Think about the terms 'GIS', 'GDS' and 'Geocomputation' described above. Which is your favorite, and why?

2. Provide three reasons for using a scriptable language such as R for geocomputation instead of using an established GIS program such as QGIS.

3. Name two advantages and two disadvantages of using mature packages compared with 'cutting edge' packages for spatial data (for example **sp** vs **sf**).


<!--chapter:end:01-introduction.Rmd-->


# Geographic data in R {#spatial-class}

## Prerequisites {-}

This is the first practical chapter of the book, and therefore it comes with some software requirements.
We assume that you have installed on your computer a recent version of R and that you are comfortable using it at the command line, e.g., via an integrated development environment (IDE) such as RStudio (recommended).
R/RStudio works on all major operating systems.
You can install and set up both in a few minutes on most modern computers, as described in [section 2.3](https://csgillespie.github.io/efficientR/set-up.html#r-version) and [section 2.5](https://csgillespie.github.io/efficientR/set-up.html#rstudio) of @gillespie_efficient_2016.

If you are not a regular R user, we recommend that you familiarize yourself with the language before proceeding with this chapter.
You can do so using resources such as @gillespie_efficient_2016, @grolemund_r_2016 as well as online interactive guides such as [DataCamp](https://www.datacamp.com/courses/free-introduction-to-r).
We recommend organising your work as you learn, for example with the help of an RStudio '[project](https://csgillespie.github.io/efficientR/set-up.html#project-management)' called `geocomp-learning` or similar and a new script for each chapter.

The code you type to help learn the content of this chapter, for example, could be placed in a script called `chapter-02.R`.
Everyone learns in a different way so it is important that you structure your code in a way that makes sense to you and that you avoid copy-pasting to get used to typing code.
<!-- Another option is to use the RStudio project provided in the root directory of the [`geocompr`](https://github.com/Robinlovelace/geocompr) GitHub repository. -->
<!-- This will make it easier to run this book's worked examples on your computer. -->

* * *

After R/RStudio are installed and up-to-date --- use `update.packages()` to update packages --- the next step is to install and load the packages used in this chapter.
This can be done with `install.packages("package_name")` (not shown) and `library(package_name)` functions:


```r
library(raster)      # classes and functions for raster data
library(sf)          # classes and functions for vector data
```

The chapter also relies on two data packages: **spData** and **spDataLarge**, the latter of which must be installed after **spData** is loaded:^[**spDataLarge** can also be installed with the following command: `install.packages("spDataLarge", repos = "https://nowosad.github.io/drat/", type = "source")`]



```r
library(spData)        # load geographic data
```


```r
install.packages("spDataLarge") # after loading spData
```


```r
library(spDataLarge)   # load geographic data
```

\BeginKnitrBlock{rmdnote}<div class="rmdnote">On Mac and Linux a few requirements must be met to install **sf**.
These are described in the package's README at [github.com/r-spatial/sf](https://github.com/r-spatial/sf).</div>\EndKnitrBlock{rmdnote}

This chapter will provide brief explanations of the fundamental geographic data models: vector and raster.
We will introduce the theory behind each data model and the disciplines in which they predominate, before demonstrating their implementation in R.
<!-- Vector and raster models are vital to geospatial analysis [@longley_geographic_2015]. -->

The *vector data model* represents the world using points, lines and polygons.
This means, it supports data with discrete, well-defined borders.
Generally, vector datasets have a high level of precision (but not necessarily accuracy as we will see in \@ref(units)).

The *raster data model* is good at representing continuous phenomena such as elevation or rainfall with the help of grid cells that divide the surface up into a cells of constant size (*resolution*).
Rasters aggregate spatially specific features to a given resolution, meaning that they are spatially consistent and scalable (many worldwide raster datasets are available).
The downside of this is that small features can be blurred or lost.
<!-- todo: add figure(s) showing raster data and blurring? -->

The appropriate data model to use depends on the domain of application:

- Vector data tends to dominate the social sciences because human settlements and boundaries have discrete borders.
- By contrast, raster data often dominates the environmental sciences because these often use remotely sensed imagery. 

However, there is a substantial level of overlap:
ecologists and demographers, for example, commonly use both vector and raster data.
We, therefore, strongly recommend learning about each data model before proceeding to understand how to manipulate them in subsequent chapters.
This book uses **sf** and **raster** packages to work with vector data and raster datasets respectively.

## Vector data

\BeginKnitrBlock{rmdnote}<div class="rmdnote">Take care when using the word 'vector' as it can have two meanings in this book:
geographic vector data and `vector`s (note the `monospace` font) in R.
The former is a data model, the latter is an R class just like `data.frame` and `matrix`.
Still, there is a link between the two: the spatial coordinates which are at the heart of the geographic vector data model can be represented in R using `vector` objects.</div>\EndKnitrBlock{rmdnote}

The geographic vector model is based on points located within a coordinate reference system (CRS).
Points can represent self-standing features (e.g. the location of a bus stop) or they can be linked together to form more complex geometries such as lines and polygons.
Most point geometries contain only two dimension (3 dimensional CRSs contain an additional $z$ value, typically representing height above sea level).

In this system London, for example, can be represented by the coordinates `c(-0.1, 51.5)`.
This mean its location is -0.1 degrees east and 55.5 degrees north of the origin at 0 degrees longitude (the Prime Meridian) and 0 degree latitude (the Equator) in a geographic ('lon/lat') CRS (Figure \@ref(fig:vectorplots), left panel).
The same point could also be approximated in a projected CRS with 'Easting/Northing' values of `c(530000, 180000)` in the British National Grid (BNG).
In the vector data model this suggests that London is located 530 km *East* and 180 km *North* of the $origin$ of the CRS.
This can be verified visually: slightly more than 5 'boxes' --- square areas bounded by the grey grid lines 100 km in width --- separate the point representing London from the origin in Figure \@ref(fig:vectorplots).
This shows that the origin of the BNG is located in the sea to the southeast of the UK, ensuring that all locations in the UK can be represented with positive Easting and Northing values.
CRSs are described in section \@ref(crs-intro).



<div class="figure" style="text-align: center">
<img src="figures/vector_lonlat.png" alt="Illustration of vector (point) data in R with the location of London (the red X) represented with reference to an origin (the blue circle). The left plot represents a geographic CRS with an origin at 0° Longitude and latitude. The right plot represents a projected CRS with an origin at -2° longitude and 49° latitude, and units of meters." width="45%" /><img src="figures/vector_projected.png" alt="Illustration of vector (point) data in R with the location of London (the red X) represented with reference to an origin (the blue circle). The left plot represents a geographic CRS with an origin at 0° Longitude and latitude. The right plot represents a projected CRS with an origin at -2° longitude and 49° latitude, and units of meters." width="45%" />
<p class="caption">(\#fig:vectorplots)Illustration of vector (point) data in R with the location of London (the red X) represented with reference to an origin (the blue circle). The left plot represents a geographic CRS with an origin at 0° Longitude and latitude. The right plot represents a projected CRS with an origin at -2° longitude and 49° latitude, and units of meters.</p>
</div>


<!-- Commented out: not really necessary here - keeping as could be useful elsewhere: -->
<!-- In mathematical notation these points are typically represented as numbers separated by commas and enclosed by a pair of brackets:  -->
<!-- $(1, 3)$ for example, represents a point located one unit to the right and three units above the origin. -->
<!-- Instead of creating these points manually, one would commonly read-in data with functions such as `read_csv()` from the **tidyverse** or `read_sf()` from the **sf** package (see chapter \@ref(read-write)). -->
<!-- To generate new data (e.g., for testing), one can use the command `c()` (think of 'c' for 'combine'), as illustrated -->
<!-- below:^[Other methods for generating numbers include with the `seq()` function (short for 'sequence') for generating regular sequences or `runif()`, `rnorm()` and other functions generating random numbers following some kind of probability distribution. -->
<!-- The **mapedit** package can be used to create spatial data manually on an interactive map. -->
<!-- ] -->

<!-- ```{r} -->
<!-- p = c(1, 3) -->
<!-- ``` -->

<!-- Now this can be plotted in Cartesian space, as illustrated in figure \@ref(fig:cartesian): -->

<!-- ```{r cartesian, fig.cap="Illustration of vector point data in base R."} -->
<!-- plot(x = p[1], y = p[2], xlim =  c(0, 5), ylim = c(0, 5)) -->
<!-- ``` -->

### An introduction to simple features {#intro-sf}

Simple features is an open standard developed and endorsed by the Open Geospatial Consortium ([OGC](http://portal.opengeospatial.org/files/?artifact_id=25355)) to represent a wide range of geographic information.
It is a hierarchical data model that simplifies geographic data by condensing a complex range of geographic forms into a single geometry class.
Only 7 out of 68 possible types of simple feature are currently used in the vast majority of GIS operations (Figure \@ref(fig:sf-ogc)).
The R package **sf** [@R-sf] fully supports all of these (including plotting methods etc.).^[
The full OGC standard includes rather exotic geometry types including 'surface' and 'curve' geometry types, which currently have limited application in real world applications.
All 68 types can be represented in R, although (at the time of writing) all methods, such as plotting, are only supported for the 7 types that are used.
]

<div class="figure" style="text-align: center">
<img src="figures/sf-classes.png" alt="The subset of the Simple Features class hierarchy supported by sf." width="100%" />
<p class="caption">(\#fig:sf-ogc)The subset of the Simple Features class hierarchy supported by sf.</p>
</div>

**sf** can represent all common vector geometry types (raster data classes are not supported by **sf**): points, lines, polygons and their respective 'multi' versions (which group together features of the same type into a single feature).
**sf** also supports geometry collections, which can contain multiple geometry types in a single object.
Given the breadth of geographic data forms, it may come as a surprise that a class system to support all of them is provided in a single package, which can be installed from CRAN:^[The
development version, which may contain new features, can be installed with `devtools::install_github("r-spatial/sf").`
]
**sf** incorporates the functionality of the three main packages of the **sp** paradigm (**sp** [@R-sp] for the class system, **rgdal** [@R-rgdal] for reading and writing data, **rgeos** [@R-rgeos] for spatial operations undertaken by GEOS) in a single, cohesive whole.
This is well-documented in **sf**'s [vignettes](http://cran.rstudio.com/package=sf):


```r
vignette("sf1") # for an introduction to the package
vignette("sf2") # for reading, writing and converting Simple Features
vignette("sf3") # for manipulating Simple Features
```

As the first vignette explains, simple feature objects in R are stored in a data frame, with geographic data occupying a special column, a 'list-column'. This column is usually named 'geom' or 'geometry'.
We will use the `world` dataset provided by the **spData**, loaded at the beginning of this chapter (see [nowosad.github.io/spData](https://nowosad.github.io/spData/) for a list datasets loaded by the package).
`world` is a spatial object containing spatial and attribute columns, the names of which are returned by the function `names()` (the last column contains the geographic information):


```r
names(world)
#>  [1] "iso_a2"    "name_long" "continent" "region_un" "subregion"
#>  [6] "type"      "area_km2"  "pop"       "lifeExp"   "gdpPercap"
#> [11] "geom"
```

It is the contents of this modest-looking `geom` column that gives `sf` objects their spatial powers, a 'list-column' that contains all the coordinates.
The **sf** package provides a `plot()` method for vizualising geographic data:
the follow command creates Figure \@ref(fig:world-all).


```r
plot(world)
#> Warning: plotting the first 9 out of 10 attributes; use max.plot = 10 to
#> plot all
```

<div class="figure" style="text-align: center">
<img src="figures/world-all-1.png" alt="A spatial plot of the world using the sf package, with a facet for each attribute." width="576" />
<p class="caption">(\#fig:world-all)A spatial plot of the world using the sf package, with a facet for each attribute.</p>
</div>

Note that instead of creating a single map, as most GIS programs would, the `plot()` command has created multiple maps, one for each variable in the `world` datasets.
This behavior can be useful for exploring the spatial distribution of different variables and is discussed further in \@ref(basic-map) below.

Being able to treat spatial objects as regular data frames with spatial powers has many advantages, especially if you are already used to working with data frames.
The commonly used `summary()` function, for example, provides a useful overview of the variables within the `world` object.


```r
summary(world["lifeExp"])
#>     lifeExp                geom    
#>  Min.   :48.9   MULTIPOLYGON :177  
#>  1st Qu.:64.3   epsg:4326    :  0  
#>  Median :72.8   +proj=long...:  0  
#>  Mean   :70.6                      
#>  3rd Qu.:77.1                      
#>  Max.   :83.6                      
#>  NA's   :9
```

Although we have only selected one variable for the `summary` command, it also outputs a report on the geometry.
This demonstrates the 'sticky' behavior of the geometry columns of **sf** objects, meaning the geometry is kept unless the user deliberately removes them, as we'll see in section \@ref(vector-attribute-manipulation).
The result provides a quick summary of both the non-spatial and spatial data contained in `world`: the average life expectancy is 73 years (ranging from less than 50 to more than 80 years) across all countries.

\BeginKnitrBlock{rmdnote}<div class="rmdnote">The word `MULTIPOLYGON` in the summary output above refers to the geometry type of features (countries) in the `world` object.
This representation is necessary for countries with islands such as Indonesia and Greece.
Other geometry types are described in section \@ref(sf-classes).</div>\EndKnitrBlock{rmdnote}

<!-- TODO: cross-reference section covering CRSs. -->
It is worth taking a deeper look at the basic behavior and contents of this simple feature object, which can usefully be thought of as a '**S**patial data**F**rame).

`sf` objects are easy to subset.
The code below shows its first two rows and three columns.
The output shows two major differences compared with a regular `data.frame`: the inclusion of additional geographic data (`geometry type`, `dimension`, `bbox` and CRS information - `epsg (SRID)`, `proj4string`), and the presence of final `geometry` column:


```r
world[1:2, 1:3]
#> Simple feature collection with 2 features and 3 fields
#> geometry type:  MULTIPOLYGON
#> dimension:      XY
#> bbox:           xmin: 11.6401 ymin: -17.93064 xmax: 75.15803 ymax: 38.48628
#> epsg (SRID):    4326
#> proj4string:    +proj=longlat +datum=WGS84 +no_defs
#>   iso_a2   name_long continent                           geom
#> 1     AF Afghanistan      Asia MULTIPOLYGON (((61.21081709...
#> 2     AO      Angola    Africa MULTIPOLYGON (((16.32652835...
```

All this may seem rather complex, especially for a class system that is supposed to be simple.
However, there are good reasons for organizing things this way and using **sf**.

<!-- It's a `MULTIPOLYGON` with 177 features and a geographic (longitude/latidue) coordinate reference system (CRS) with an EPSG code of `4326`. -->

### Why simple features?

Simple features is a widely supported data model that underlies data structures in many GIS applications including QGIS and PostGIS.
A major advantage of this is that using the data model ensures your work is cross-transferable to other set-ups, for example importing from and exporting to spatial databases.

A more specific question from an R perspective is "why use the **sf** package when **sp** is already tried and tested"?
There are many reasons (linked to the advantages of the simple features model) including:

- Fast reading and writing of data
- Enhanced plotting performance
- **sf** objects can be treated as data frames in most operations
- **sf** functions can be combined using `%>%` operator and works well with the [tidyverse](http://tidyverse.org/) collection of R packages
- **sf** function names are relatively consistent and intuitive (all begin with `st_`)

Due to such advantages some spatial packages (including **tmap**, **mapview** and **tidycensus**) have added support for **sf**.
However, it will take many years for many packages to transition, and some packages will never switch.
Fortunately these can still be used in a workflow based on `sf` objects, by converting them to the `Spatial` class used in **sp**: 


```r
library(sp)
world_sp = as(world, Class = "Spatial")
# sp functions ...
```

`Spatial` objects can be converted back to `sf` in the same way or with `st_as_sf()`:


```r
world_sf = st_as_sf(world_sp, "sf")
```


### Basic map making {#basic-map}

You can quickly create basic maps in **sf** with the base `plot()` function. By default, **sf** creates a multi-panel plot (like **sp**'s `spplot()`), one sub-plot for each variable (see left-hand image in Figure \@ref(fig:sfplot)). 


```r
plot(world[3:4])
plot(world["pop"])
```

<div class="figure" style="text-align: center">
<img src="figures/sfplot-1.png" alt="Plotting with sf, with multiple variables (left) and a single variable (right)." width="49%" /><img src="figures/sfplot-2.png" alt="Plotting with sf, with multiple variables (left) and a single variable (right)." width="49%" />
<p class="caption">(\#fig:sfplot)Plotting with sf, with multiple variables (left) and a single variable (right).</p>
</div>

As with **sp**, you can add further layers to your maps using the `add = TRUE`-argument of the `plot()` function .^[In
fact, when you `plot()` an **sf** object, R is calling `sf:::plot.sf()` behind the scenes.
`plot()` is a generic method that behaves differently depending on the class of object being plotted.]
To illustrate this, and prepare for content covered in chapters \@ref(attr) and \@ref(spatial-data-operations) on attribute and spatial data operations, we will subset and combine countries in the `world` object, which creates a single object representing Asia:


```r
asia = world[world$continent == "Asia", ]
asia = st_union(asia)
```

We can now plot the Asian continent over a map of the world.
Note, however, that this only works if the initial plot has only one layer:


```r
plot(world["pop"])
plot(asia, add = TRUE, col = "red")
```

<div class="figure" style="text-align: center">
<img src="figures/asia-1.png" alt="A plot of Asia added as a layer on top of countries worldwide." width="50%" />
<p class="caption">(\#fig:asia)A plot of Asia added as a layer on top of countries worldwide.</p>
</div>

This can be very useful for quickly checking the geographic correspondence between two or more layers: 
the `plot()` function is fast to execute and requires few lines of code, but does not create interactive maps with a wide range of options.
For more advanced map making we recommend using a dedicated visualization package such as **tmap**, **ggplot2**, **mapview**, or **leaflet**.
<!-- TODO: cross reference advanced mapping chapter -->

<!-- 
- plot() function 
- map export 
-->

<!-- Maybe show also somewhere that `world[0]` produces only a plot of the geometry which is rather useful if you do not want to plot a specific attribute. This way, you can for example dismiss the col = "white"-argument in your Nigeria example.
Sorry for commenting on this again but just to clarify africa[0] selects zero columns but since the geometry column is sticky it won't be dismissed. Neverthess, to be more explicit one should probably use plot(st_geometry(africa))-->



### Base plot arguments {#base-args}

**sf** simplifies spatial data objects compared with **sp** and provides a near-direct interface to GDAL and GEOS C++ functions.
In theory this should make **sf** faster than **sp**/**rgdal**/**rgeos**, something that is tested in Chapter 5 for data I/O.
This section introduces **sf** classes in preparation for subsequent chapters which deal with vector data (in particular Chapter \@ref(spatial-data-operations)).

As a final exercise, we will see one way of how to do a spatial overlay in **sf**.
First, we convert the countries of the world into centroids, and then subset those in Asia. Finally, the `summary`-command tells us how many centroids (countries) are part of Asia (43) and how many are not (134).


```r
world_centroids = st_centroid(world)
#> Warning in st_centroid.sfc(st_geometry(x), of_largest_polygon =
#> of_largest_polygon): st_centroid does not give correct centroids for
#> longitude/latitude data
sel_asia = st_intersects(world_centroids, asia, sparse = FALSE)
#> although coordinates are longitude/latitude, st_intersects assumes that they are planar
summary(sel_asia)
#>      V1         
#>  Mode :logical  
#>  FALSE:134      
#>  TRUE :43
```

Note: `st_intersects()` uses [GEOS](https://trac.osgeo.org/geos/) in the background for the spatial overlay operation (see also Chapter \@ref(spatial-data-operations)).

Since **sf**'s `plot()` function builds on base plotting methods, you may also use its many optional arguments (see `?plot` and `?par`).
This provides a powerful but not necessarily intuitive interface.
To make the area of circles proportional to population, for example, the `cex` argument can be used as follows (see Figure \@ref(fig:contpop) created with the code below and the exercises in section \@ref(ex2)):


```r
plot(world["continent"])
plot(world_centroids, add = TRUE, cex = sqrt(world$pop) / 10000)
```

<div class="figure" style="text-align: center">
<img src="figures/contpop-1.png" alt="Country continents (represented by fill colour) and 2015 populations (represented by points, with point area proportional to population) worldwide." width="576" />
<p class="caption">(\#fig:contpop)Country continents (represented by fill colour) and 2015 populations (represented by points, with point area proportional to population) worldwide.</p>
</div>

<!-- More appropriate for subsequent chapters. -->
<!-- This shows that there are 43 countries in Asia -->
<!-- We can check if they are the same countries as follows: -->

<!-- ```{r} -->
<!-- africa_centroids2 = world_centroids[sel_africa, ] -->
<!-- identical(africa_centroids, africa_centroids2) -->
<!-- ``` -->

### Simple feature classes {#sf-classes}

To understand new data formats in depth, it often helps to build them from the ground up.
This section walks you through vector spatial classes step-by-step, from the elementary simple feature geometry to simple feature objects of class `sf` representing complex spatial data.
Before describing each geometry type that the **sf** package supports, it is worth taking a step back to understand the building blocks of `sf` objects. 
As stated in section \@ref(intro-sf), simple features are simply data frames with at least one special column that makes it spatial.
These spatial columns are often called `geom` or `geometry` and can be like non-spatial columns: `world$geom` refers to the spatial element of the `world` object described above.
These geometry columns are 'list columns' of class `sfc`: they are simple feature collections.
In turn, `sfc` objects are composed of one or more objects of class `sfg`: simple feature geometries.

To understand how the spatial components of simple features work, it is vital to understand simple feature geometries.
For this reason we cover each currently supported `sfg` type in the next subsections before moving on to describe how these can be combined to form `sfc` and eventually full `sf` objects.

#### Simple feature geometry types {#geometry}

<!-- This section demonstrates how the full range of geometry types supported by the **sf** package can be created, combined and plotted. -->
Geometries are the basic building blocks of simple features.
Simple features in R can take on one of the 17 geometry types supported by the **sf** package.
In this chapter we will focus on the seven most commonly used types: `POINT`, `LINESTRING`, `POLYGON`, `MULTIPOINT`, `MULTILINESTRING`, `MULTIPOLYGON` and `GEOMETRYCOLLECTION`.<!--FIG-->
Find the whole list of possible feature types in [the PostGIS manual ](http://postgis.net/docs/using_postgis_dbmanagement.html).

Generally, well-known binary (WKB) or well-known text (WKT) are the standard encoding for simple feature geometries.
WKB representations are usually hexadecimal strings easily readable for computers.
This is why, GIS and spatial databases use WKB to transfer and store geometry objects.
WKT, on the other hand, is a human-readable text markup description of simple features. 
Both formats are exchangeable, and if we present one, we will naturally choose the WKT representation.

The basis for each geometry type is the point. 
A point is simply a coordinate in 2D, 3D or 4D space (see `vignette("sf1")` for more information) such as:

- `POINT (5 2)`

<img src="figures/point-1.png" width="576" style="display: block; margin: auto;" />

A linestring is a sequence of points with a straight line connecting the points, for example:

- `LINESTRING (1 5, 4 4, 4 1, 2 2, 3 2)`

<img src="figures/linestring-1.png" width="576" style="display: block; margin: auto;" />

A polygon is a sequence of points that form a closed, non-intersecting ring.
Closed means that the first and the last point of a polygon have the same coordinates. 
By definition, a polygon has one exterior boundary (outer ring) and can have zero or more interior boundaries (inner rings), also known as holes.

- Polygon without a hole - `POLYGON ((1 5, 2 2, 4 1, 4 4, 1 5))`

<img src="figures/polygon-1.png" width="576" style="display: block; margin: auto;" />

- Polygon with one hole - `POLYGON ((1 5, 2 2, 4 1, 4 4, 1 5), (2 4, 3 4, 3 3, 2 3, 2 4))`

<img src="figures/polygon_hole-1.png" width="576" style="display: block; margin: auto;" />

So far we have created geometries with only one geometric entity per feature.
However, **sf** also allows multiple geometries to exist within a single feature (hence the term 'geometry collection') using "multi" version of each geometry type:

- Multipoint - `MULTIPOINT (5 2, 1 3, 3 4, 3 2)`
- Multistring - `MULTILINESTRING ((1 5, 4 4, 4 1, 2 2, 3 2), (1 2, 2 4))`
- Multipolygon - `MULTIPOLYGON (((1 5, 2 2, 4 1, 4 4, 1 5), (0 2, 1 2, 1 3, 0 3, 0 2)))`

<img src="figures/multis-1.png" width="576" style="display: block; margin: auto;" />

Finally, a geometry collection might contain any combination of geometry types:

- Geometry collection - `GEOMETRYCOLLECTION (MULTIPOINT (5 2, 1 3, 3 4, 3 2), LINESTRING (1 5, 4 4, 4 1, 2 2, 3 2)))`

<img src="figures/geom_collection-1.png" width="576" style="display: block; margin: auto;" />

#### Simple feature geometry (sfg) objects {#sfg}

In R, the `sfg` class represents the different simple feature geometry types: (multi-)point, (multi-)linestring, (multi-)polygon or geometry collection.

Usually you are spared the tedious task of creating geometries on your own since you can simply import an already existing spatial file.
However, there are a set of function to create simple feature geometry objects (`sfg`) from scratch if needed.
The names of these functions are simple and consistent, as they all start with the `st_`  prefix and end with the name of the geometry type in lowercase letters:

- A point - `st_point()`
- A linestring - `st_linestring()`
- A polygon - `st_polygon()`
- A multipoint - `st_multipoint()`
- A multilinestring - `st_multilinestring()`
- A multipolygon - `st_multipolygon()`
- A geometry collection - `st_geometrycollection()`

In R, you create `sfg` objects with the help of three native data types:

1. A numeric vector - a single point
2. A matrix - a set of points, where each row contains a point - a multipoint or linestring
3. A list - any other set, e.g. a multilinestring or geometry collection

To create point objects, we use the `st_point()` function in conjunction with a numeric vector:


```r
# note that we use a numeric vector for points
st_point(c(5, 2)) # XY point
#> POINT (5 2)
st_point(c(5, 2, 3)) # XYZ point
#> POINT Z (5 2 3)
st_point(c(5, 2, 1), dim = "XYM") # XYM point
#> POINT M (5 2 1)
st_point(c(5, 2, 3, 1)) # XYZM point
#> POINT ZM (5 2 3 1)
```

<!-- is this really important? -->
XY, XYZ and XYZM types of points are automatically created based on the length of a numeric vector. 
Only the XYM type needs to be specified using a `dim` argument.

By contrast, use matrices in the case of multipoint (`st_multipoint()`) and linestring (`st_linestring()`) objects:


```r
# the rbind function simplifies the creation of matrices
## MULTIPOINT
multipoint_matrix = rbind(c(5, 2), c(1, 3), c(3, 4), c(3, 2))
st_multipoint(multipoint_matrix)
#> MULTIPOINT (5 2, 1 3, 3 4, 3 2)

## LINESTRING
linestring_matrix = rbind(c(1, 5), c(4, 4), c(4, 1), c(2, 2), c(3, 2))
st_linestring(linestring_matrix)
#> LINESTRING (1 5, 4 4, 4 1, 2 2, 3 2)
```

Finally, use lists for the creation of multilinestrings, (multi-)polygons and geometry collections:


```r
## POLYGON
polygon_list = list(rbind(c(1, 5), c(2, 2), c(4, 1), c(4, 4), c(1, 5)))
st_polygon(polygon_list)
#> POLYGON ((1 5, 2 2, 4 1, 4 4, 1 5))
```


```r
## POLYGON with a hole
polygon_border = rbind(c(1, 5), c(2, 2), c(4, 1), c(4, 4), c(1, 5))
polygon_hole = rbind(c(2, 4), c(3, 4), c(3, 3), c(2, 3), c(2, 4))
polygon_with_hole_list = list(polygon_border, polygon_hole)
st_polygon(polygon_with_hole_list)
#> POLYGON ((1 5, 2 2, 4 1, 4 4, 1 5), (2 4, 3 4, 3 3, 2 3, 2 4))
```


```r
## MULTILINESTRING
multilinestring_list = list(rbind(c(1, 5), c(4, 4), c(4, 1), c(2, 2), c(3, 2)), 
                            rbind(c(1, 2), c(2, 4)))
st_multilinestring((multilinestring_list))
#> MULTILINESTRING ((1 5, 4 4, 4 1, 2 2, 3 2), (1 2, 2 4))
```


```r
## MULTIPOLYGON
multipolygon_list = list(list(rbind(c(1, 5), c(2, 2), c(4, 1), c(4, 4), c(1, 5))),
                         list(rbind(c(0, 2), c(1, 2), c(1, 3), c(0, 3), c(0, 2))))
st_multipolygon(multipolygon_list)
#> MULTIPOLYGON (((1 5, 2 2, 4 1, 4 4, 1 5)), ((0 2, 1 2, 1 3, 0 3, 0 2)))
```


```r
## GEOMETRYCOLLECTION
gemetrycollection_list = list(st_multipoint(multipoint_matrix),
                              st_linestring(linestring_matrix))
st_geometrycollection(gemetrycollection_list)
#> GEOMETRYCOLLECTION (MULTIPOINT (5 2, 1 3, 3 4, 3 2), LINESTRING (1 5, 4 4, 4 1, 2 2, 3 2))
```

<!-- table -->
<!-- figure - image/fig1.jpg -->
<!-- they are interconnected - points could create mulitpoints or lines; -->
<!-- lines could create mutlilines or polygons, etc. -->
<!-- https://r-spatial.github.io/sf/articles/sf1.html -->

#### Simple feature collections {#sfc}

One `sfg` object contains only a single simple feature geometry. 
A collection of simple feature geometries (`sfc`) is a list is a list of `sfg` objects and can additionally contain information about the coordinate reference system in use.
For instance, to combine two simple features into one object with two features, we can use the `st_sfc()` function. 
This is important since this collection represents the geometry column in **sf** data frames:


```r
# sfc POINT
point1 = st_point(c(5, 2))
point2 = st_point(c(1, 3))
st_sfc(point1, point2)
#> Geometry set for 2 features 
#> geometry type:  POINT
#> dimension:      XY
#> bbox:           xmin: 1 ymin: 2 xmax: 5 ymax: 3
#> epsg (SRID):    NA
#> proj4string:    NA
#> POINT (5 2)
#> POINT (1 3)
```

In most cases, an `sfc` object contains objects of the same geometry type.
Therefore, when we convert `sfg` objects of type polygon into a simple feature collection, we would also end up with an `sfc` object of type polygon. 
Equally, a collection of multilinestrings would result in an `sfc` object of type multilinestring:


```r
# sfc POLYGON
polygon_list1 = list(rbind(c(1, 5), c(2, 2), c(4, 1), c(4, 4), c(1, 5)))
polygon1 = st_polygon(polygon_list)
polygon_list2 = list(rbind(c(0, 2), c(1, 2), c(1, 3), c(0, 3), c(0, 2)))
polygon2 = st_polygon(polygon_list2)
st_sfc(polygon1, polygon2)
#> Geometry set for 2 features 
#> geometry type:  POLYGON
#> dimension:      XY
#> bbox:           xmin: 0 ymin: 1 xmax: 4 ymax: 5
#> epsg (SRID):    NA
#> proj4string:    NA
#> POLYGON ((1 5, 2 2, 4 1, 4 4, 1 5))
#> POLYGON ((0 2, 1 2, 1 3, 0 3, 0 2))
```


```r
# sfc MULTILINESTRING
multilinestring_list1 = list(rbind(c(1, 5), c(4, 4), c(4, 1), c(2, 2), c(3, 2)), 
                            rbind(c(1, 2), c(2, 4)))
multilinestring1 = st_multilinestring((multilinestring_list1))
multilinestring_list2 = list(rbind(c(2, 9), c(7, 9), c(5, 6), c(4, 7), c(2, 7)), 
                            rbind(c(1, 7), c(3, 8)))
multilinestring2 = st_multilinestring((multilinestring_list2))
st_sfc(multilinestring1, multilinestring2)
#> Geometry set for 2 features 
#> geometry type:  MULTILINESTRING
#> dimension:      XY
#> bbox:           xmin: 1 ymin: 1 xmax: 7 ymax: 9
#> epsg (SRID):    NA
#> proj4string:    NA
#> MULTILINESTRING ((1 5, 4 4, 4 1, 2 2, 3 2), (1 ...
#> MULTILINESTRING ((2 9, 7 9, 5 6, 4 7, 2 7), (1 ...
```

It is also possible to create an `sfc` object from `sfg` objects with different geometry types:


```r
# sfc GEOMETRY
st_sfc(point1, multilinestring1)
#> Geometry set for 2 features 
#> geometry type:  GEOMETRY
#> dimension:      XY
#> bbox:           xmin: 1 ymin: 1 xmax: 5 ymax: 5
#> epsg (SRID):    NA
#> proj4string:    NA
#> POINT (5 2)
#> MULTILINESTRING ((1 5, 4 4, 4 1, 2 2, 3 2), (1 ...
```

<!-- if you want to use it - st_cast() to a proper geometry type -->
<!-- or st_is to select only one geometry type -->
<!-- http://r-spatial.org/r/2017/01/12/newssf.html -->
<!-- methods(class = "sfc") -->

As mentioned before, `sfc` objects can additionally store information on the coordinate reference systems (CRS).
<!-- What's CRS -->
To specify a certain CRS, we can use the `epsg (SRID)` or `proj4string` attributes of an `sfc` object.
The default value of `epsg (SRID)` and `proj4string` is `NA` (*Not Available*):


```r
st_sfc(point1, point2)
#> Geometry set for 2 features 
#> geometry type:  POINT
#> dimension:      XY
#> bbox:           xmin: 1 ymin: 2 xmax: 5 ymax: 3
#> epsg (SRID):    NA
#> proj4string:    NA
#> POINT (5 2)
#> POINT (1 3)
```

Of course, all geometries in an `sfc` object must have the same CRS. 

We can add coordinate reference system as a `crs` argument of `st_sfc()`. 
This argument accepts either an integer with the `epsg` code (e.g., `4326`)  or a `proj4string` character string (e.g., `"+proj=longlat +datum=WGS84 +no_defs"`) (see section \@ref(crs-intro)). 


```r
# EPSG definition
st_sfc(point1, point2, crs = 4326)
#> Geometry set for 2 features 
#> geometry type:  POINT
#> dimension:      XY
#> bbox:           xmin: 1 ymin: 2 xmax: 5 ymax: 3
#> epsg (SRID):    4326
#> proj4string:    +proj=longlat +datum=WGS84 +no_defs
#> POINT (5 2)
#> POINT (1 3)
```


```r
# PROJ4STRING definition
st_sfc(point1, point2, crs = "+proj=longlat +datum=WGS84 +no_defs")
#> Geometry set for 2 features 
#> geometry type:  POINT
#> dimension:      XY
#> bbox:           xmin: 1 ymin: 2 xmax: 5 ymax: 3
#> epsg (SRID):    4326
#> proj4string:    +proj=longlat +datum=WGS84 +no_defs
#> POINT (5 2)
#> POINT (1 3)
```

For example, we can set the UTM Zone 11N projection with `epsg` code `2955`:


```r
st_sfc(point1, point2, crs = 2955)
#> Geometry set for 2 features 
#> geometry type:  POINT
#> dimension:      XY
#> bbox:           xmin: 1 ymin: 2 xmax: 5 ymax: 3
#> epsg (SRID):    2955
#> proj4string:    +proj=utm +zone=11 +ellps=GRS80 +towgs84=0,0,0,0,0,0,0 +units=m +no_defs
#> POINT (5 2)
#> POINT (1 3)
```

As you can see above, the `proj4string` definition was automatically added.
Now we can try to set the CRS using `proj4string`:


```r
st_sfc(point1, point2, crs = "+proj=utm +zone=11 +ellps=GRS80 +towgs84=0,0,0,0,0,0,0 +units=m +no_defs")
#> Geometry set for 2 features 
#> geometry type:  POINT
#> dimension:      XY
#> bbox:           xmin: 1 ymin: 2 xmax: 5 ymax: 3
#> epsg (SRID):    NA
#> proj4string:    +proj=utm +zone=11 +ellps=GRS80 +towgs84=0,0,0,0,0,0,0 +units=m +no_defs
#> POINT (5 2)
#> POINT (1 3)
```

However, the `epsg` string of our result remained empty. 
This is because there is no general method to convert from `proj4string` to `epsg`.

<!-- precision -->
<!-- plots can be made -->

#### Simple feature objects {#sf}

So far, we have only dealt with the pure geometries.
Most of the time, however, these geometries come with a set of attributes describing them. 
These attributes could represent the name of the geometry, measured values, groups to which the geometry belongs, and many more.
For example, we measured a temperature of 25°C on Trafalgar Square in London on June 21^th^ 2017. 
Hence, we have a specific point in space (the coordinates), the name of the location (Trafalgar Square), a temperature value, the date of the measurement.
Other attributes might include a urbanity category (city or village), or a remark if the measurement was made using an automatic station.

The simple feature class, `sf`, is a combination of an attribute table (`data.frame`) and a simple feature geometry collection (`sfc`).
Simple features are created using the `st_sf()` function:


```r
# sfg objects
london_point = st_point(c(0.1, 51.5))
ruan_point = st_point(c(-9, 53))

# sfc object
our_geometry = st_sfc(london_point, ruan_point, crs = 4326)

# data.frame object
our_attributes = data.frame(name = c("London", "Ruan"),
                            temperature = c(25, 13),
                            date = c(as.Date("2017-06-21"), as.Date("2017-06-22")),
                            category = c("city", "village"),
                            automatic = c(FALSE, TRUE))

# sf object
sf_points = st_sf(our_attributes, geometry = our_geometry)
```

The above example illustrates the components of `sf` objects. 
Firstly, coordinates define the geometry of the simple feature geometry (`sfg`).
Secondly, we can combine the geometries in a simple feature collection (`sfc`) which also stores the CRS.
Subsequently, we store the attribute information on the geometries in a `data.frame`.
Finally, the `st_sf()` function combines the attribute table and the `sfc` object in an `sf` object.


```r
sf_points
#> Simple feature collection with 2 features and 5 fields
#> geometry type:  POINT
#> dimension:      XY
#> bbox:           xmin: -9 ymin: 51.5 xmax: 0.1 ymax: 53
#> epsg (SRID):    4326
#> proj4string:    +proj=longlat +datum=WGS84 +no_defs
#>     name temperature       date category automatic         geometry
#> 1 London          25 2017-06-21     city     FALSE POINT (0.1 51.5)
#> 2   Ruan          13 2017-06-22  village      TRUE    POINT (-9 53)
```


```r
class(sf_points)
#> [1] "sf"         "data.frame"
```

The result shows that `sf` objects actually have two classes, `sf` and `data.frame`.
Simple features are simply data frames (square tables), but with spatial attributes (usually stored in a special `geom` list-column in the data frame).
This duality is central to the concept of simple features:
most of the time a `sf` can be treated as and behaves like a `data.frame`.
Simple features are, in essence, data frames with a spatial extension.

<!-- methods -->
<!-- methods(class = "sf") -->
<!-- plots -->
<!-- https://r-spatial.github.io/sf/articles/sf1.html#how-attributes-relate-to-geometries -->

## Raster data

The geographic raster data model consists of a raster header and a matrix (with rows and columns) representing equally spaced cells (often also called pixels; Figure \@ref(fig:raster-intro-plot):A).
The raster header defines the coordinate reference system, the extent and the origin.
The origin (or starting point) is frequently the coordinate of the lower-left corner of the matrix (the **raster** package, however, uses the upper left corner, by default (Figure  \@ref(fig:raster-intro-plot):B)).
The header defines the extent via the number of columns, the number of rows and the cell size resolution.
Hence, starting from the origin, we can easily access and modify each single cell by either using the ID of a cell  (Figure  \@ref(fig:raster-intro-plot):B) or by explicitly specifying the rows and columns.
This matrix representation avoids storing explicitly the coordinates for the four corner points (in fact it only stores one coordinate, namely the origin) of each cell corner as would be the case for rectangular vector polygons.
This and map algebra makes raster processing much more efficient and faster than vector data processing.
However, in contrast to vector data, a raster cell can only hold a single value.
The value might be numeric or categorical (Figure  \@ref(fig:raster-intro-plot):C).

<div class="figure" style="text-align: center">
<img src="figures/02_raster_intro_plot.png" alt="Raster data: A - cell IDs; B - cell values; C - a colored raster map." width="1125" />
<p class="caption">(\#fig:raster-intro-plot)Raster data: A - cell IDs; B - cell values; C - a colored raster map.</p>
</div>

Raster maps usually represent continuous phenomena such as elevation, temperature, population density or spectral data (Figure \@ref(fig:raster-intro-plot2)).
Of course, we can represent discrete features such as soil or landcover classes also with the help of a raster data model (Figure \@ref(fig:raster-intro-plot2)).
Consequently, the discrete borders of these features become blurred, and depending on the spatial task a vector representation might be more suitable.

<div class="figure" style="text-align: center">
<img src="figures/02_raster_intro_plot2.png" alt="Examples of continuous (left) and categorical (right) raster." width="475" />
<p class="caption">(\#fig:raster-intro-plot2)Examples of continuous (left) and categorical (right) raster.</p>
</div>

### An introduction to raster

The **raster** package supports raster objects in R. 
It provides an extensive set of functions to create, read, export, manipulate and process raster datasets.
Aside from general raster data manipulation, **raster** provides many low level functions that can form the basis to develop more advanced raster functionality.
**raster** also lets you work on large raster datasets that are too large to fit into the main memory. 
In this case, **raster** provides the possibility to divide the raster into smaller chunks (rows or blocks), and processes these iteratively instead of loading the whole raster file into RAM (for more information, please refer to `vignette("functions", package = "raster")`.

For the illustration of **raster** concepts, we will use datasets from the **spDataLarge** (note these packages were loaded at the beginning of the chapter).
It consists of a few raster and one vector datasets covering an area of the Zion National Park (Utah, USA).
For example, `srtm.tif` is a digital elevation model of this area (for more details - see its documentation `?srtm`)
First of all, we would like to create a `RasterLayer` object named `new_raster`:


```r
raster_filepath = system.file("raster/srtm.tif", package = "spDataLarge")
new_raster = raster(raster_filepath)
```

Typing the name of the raster into the console, will print out the raster header (extent, dimensions, resolution, CRS) and some additional information (class, data source name, summary of the raster values): 


```r
new_raster
#> class       : RasterLayer 
#> dimensions  : 457, 465, 212505  (nrow, ncol, ncell)
#> resolution  : 0.000833, 0.000833  (x, y)
#> extent      : -113, -113, 37.1, 37.5  (xmin, xmax, ymin, ymax)
#> coord. ref. : +proj=longlat +datum=WGS84 +no_defs +ellps=WGS84 +towgs84=0,0,0 
#> data source : /home/travis/R/Library/spDataLarge/raster/srtm.tif 
#> names       : srtm 
#> values      : 1024, 2892  (min, max)
```

To access individual header information, you can use following commands:


```r
# dimensions (number of rows, number of columns, number of cells)
dim(new_raster)
#> [1] 457 465   1
```


```r
# spatial resolution
res(new_raster)
#> [1] 0.000833 0.000833
```


```r
# spatial extent
extent(new_raster)
#> class       : Extent 
#> xmin        : -113 
#> xmax        : -113 
#> ymin        : 37.1 
#> ymax        : 37.5
```


```r
# coordinate reference system
crs(new_raster)
#> CRS arguments:
#>  +proj=longlat +datum=WGS84 +no_defs +ellps=WGS84 +towgs84=0,0,0
```

<!--CRSargs(CRS("+init=epsg:4326"))-->
Note that in contrast to the **sf** package, **raster** only accepts the `proj4string` representation of the coordinate reference system.

<!--
You can also summarize and plot raster cell values in a non-spatial fashion using base R functions such as `summary()` and `hist()`.


```r
# numerical summary of the data
summary(new_raster)
#> Warning in .local(object, ...): summary is an estimate based on a sample of 1e+05 cells (47.06% of all cells)
#>         srtm
#> Min.    1024
#> 1st Qu. 1535
#> Median  1836
#> 3rd Qu. 2111
#> Max.    2892
#> NA's       0
```


```r
# histogram of the values
hist(new_raster)
#> Warning in .hist1(x, maxpixels = maxpixels, main = main, plot = plot, ...):
#> 47% of the raster cells were used. 100000 values used.
```

<img src="figures/new_raster-hist-1.png" width="576" style="display: block; margin: auto;" />

`getValues()` extracts the values of a raster as a numerical vector.
To only select specific rows, use the `row` parameter.


```r
new_raster_values = getValues(new_raster)
head(new_raster_values)
#> [1] 1728 1718 1715 1710 1703 1701
```

The new vector, `new_raster_values`, can serve as input for subsequent statistical operations.
-->

Sometimes it is important to know if all values of a raster are currently in memory or on disk.
Find out with the `inMemory()` function:


```r
inMemory(new_raster)
#> [1] FALSE
```

`help(package = "raster", topic = "raster-package")` returns a full list of all available **raster** functions.

### Basic map making

Similar to the **sf** package, **raster** also provides `plot()` methods for its own classes.


```r
plot(new_raster)
```

<img src="figures/basic-new-raster-plot-1.png" width="576" style="display: block; margin: auto;" />

<!-- Moreover, it is possible to plot a raster and overlay it with vector data. -->
<!-- For this purpose, we need to read-in a vector dataset: -->

<!-- ```{r, message=FALSE, results='hide'} -->
<!-- vector_filepath = system.file("vector/zion.gpkg", package="spDataLarge") -->
<!-- new_vector = st_read(vector_filepath) -->
<!-- ``` -->

<!-- Our new object, `new_vector`, is a polygon representing the borders of Zion National Park (`?zion`). -->
<!-- We can add the borders to the elevation map using the `add` argument of the `plot()`: -->

<!-- ```{r basic-new-raster-vector-plot} -->
<!-- plot(new_raster) -->
<!-- plot(new_vector$geom, add = TRUE) -->
<!-- ``` -->

There are several different approaches to plot raster data in R:

- You can use `spplot()` to visualize several (such as spatiotemporal) layers at once. You can also do so  with the **rasterVis** package which provides more advanced methods for plotting raster objects.
- Packages such as **tmap**, **mapview** and **leaflet** facilitate especially interactive mapping of both raster and vector objects. 
<!-- TODO: cross reference advanced mapping chapter -->

### Raster classes {#raster-classes}

The `RasterLayer` class represents the simplest form of a raster object, and consists of only one layer.
The easiest way to create a raster object in R is to read-in a raster file from disk or from a server.


```r
raster_filepath = system.file("raster/srtm.tif", package = "spDataLarge")
new_raster = raster(raster_filepath)
```

The **raster** package support numerous drivers with the help of **rgdal**.
To find out which drivers are available on your system, run `raster::writeFormats()` and `rgdal::gdalDrivers()`.

Aside from reading in a raster, you can also create one from scratch.
Running `raster()` creates an empty `RasterLayer`.
Here, however, we will create manually a very simple raster.
This should make it easy to understand how raster and related operations work.
Our raster should consist of just three rows and columns centered around the null meridian and the equator (see `xmn`, `xmx`, `ymn` and `ymx` parameters).
Additionally, we define a resolution of 0.5, which here corresponds to 0.5 degrees since the default proj4string of a raster object is WGS84.
Finally, we set the values with the `vals` argument.
Here, we just number the cells, that means we assign 1 to cell 1, 2 to cell 2, and finally 36 to cell 36.
We know that there are 36 cells by multiplying six (rows) by six (columns).
As we have seen above, setting raster values in R corresponds to a rowwise cell filling starting at the upper left corner.
Consequently, the upper first row contains the values 1 to 6, the second row 7 to 12, and the last row 31 to 36.


```r
# creation of the RasterLayer object with a given number of columns and rows, and extent
new_raster2 = raster(nrow = 6, ncol = 6, res = 0.5, 
                     xmn = -1.5, xmx = 1.5, ymn = -1.5, ymx = 1.5,
                     vals = 1:36)
```

For still further ways of creating a raster object have a look at the help file - `?raster`.
<!--
There are several ways to add new values to the `Raster*` objects.
Values for the whole object could be add with `setValues()`:


```r
# adding random values to the raster object
new_random_values = sample(seq_len(ncell(new_raster4)))
setValues(new_raster4, new_random_values)
```


It is also possible to replace cell values by specifying cell numbers, or row and column numbers:


```r
# change the value of 15th cell to 826
new_raster4[15] = 826
# change the value of the cell in the second row and forth column to 826
new_raster4[2, 4] = 826 
```
-->

Aside from `RasterLayer`, there are two additional classes: `RasterBrick` and `RasterStack`.
Both can handle multiple layers, but differ regarding the number of supported file formats, type of internal representation and processing speed.

A `RasterBrick` consists of multiple layers, which typically correspond to a single multispectral satellite file or a single multilayer object in memory. 
The `brick()` function creates a `RasterBrick` object.
Usually, you provide it with a filename to a multilayer raster file but might also use another raster object and other spatial objects (see its help page for all supported formats).


```r
multilayer_raster_filepath = system.file("raster/landsat.tif", package="spDataLarge")
r_brick = brick(multilayer_raster_filepath)
r_brick
#> class       : RasterBrick 
#> dimensions  : 1428, 1128, 1610784, 4  (nrow, ncol, ncell, nlayers)
#> resolution  : 30, 30  (x, y)
#> extent      : 301905, 335745, 4111245, 4154085  (xmin, xmax, ymin, ymax)
#> coord. ref. : +proj=utm +zone=12 +datum=WGS84 +units=m +no_defs +ellps=WGS84 +towgs84=0,0,0 
#> data source : /home/travis/R/Library/spDataLarge/raster/landsat.tif 
#> names       : landsat.1, landsat.2, landsat.3, landsat.4 
#> min values  :      7550,      6404,      5678,      5252 
#> max values  :     19071,     22051,     25780,     31961
```

The `nlayers` function retrieves the number of layers stored in a `Raster*` object:


```r
nlayers(r_brick)
#> [1] 4
```

A `RasterStack` is similar to a `RasterBrick` in the sense that it consists also of multiple layers.
However, in contrast to `RasterBrick`, `RasterStack` allows to connect several raster objects stored in different files or multiply objects in memory.
More specifically, a `RasterStack` is a list of `RasterLayer` objects with the same extent and resolution. 
Hence, one way to create it is with the help of spatial objects already existing in R's global environment. 
And again, one can simply specify a path to a file stored on disk.
<!-- The possibility to create a `RasterStack` from a file stored on disk and an object residing in R's global environment is one of the main differences compared to a `RasterBrick`. -->


```r
raster_on_disk = raster(r_brick, layer = 1)
raster_in_memory = raster(xmn = 301905, xmx = 335745, ymn = 4111245, ymx = 4154085, res = 30)
values(raster_in_memory) = sample(1:ncell(raster_in_memory))
crs(raster_in_memory) = crs(raster_on_disk)
```


```r
r_stack <- stack(raster_in_memory, raster_on_disk)
r_stack
#> class       : RasterStack 
#> dimensions  : 1428, 1128, 1610784, 2  (nrow, ncol, ncell, nlayers)
#> resolution  : 30, 30  (x, y)
#> extent      : 301905, 335745, 4111245, 4154085  (xmin, xmax, ymin, ymax)
#> coord. ref. : +proj=utm +zone=12 +datum=WGS84 +units=m +no_defs +ellps=WGS84 +towgs84=0,0,0 
#> names       :   layer, landsat.1 
#> min values  :       1,      7550 
#> max values  : 1610784,     19071
```

Another difference is that the processing time for `RasterBrick` objects is usually shorter than for `RasterStack` objects.

Decision on which `Raster*` class should be used depends mostly on a character of input data. 
Processing of a single mulitilayer file or object is the most effective with `RasterBrick`, while `RasterStack` allows calculations based on many files, many `Raster*` objects, or both.

\BeginKnitrBlock{rmdnote}<div class="rmdnote">Operations on `RasterBrick` and `RasterStack` objects will typically return a `RasterBrick`.</div>\EndKnitrBlock{rmdnote}

## Coordinate Reference Systems {#crs-intro}

Vector and raster spatial data types share concepts intrinsic to spatial data.
Perhaps the most fundamental of these is the Coordinate Reference System (CRS), which defines how the spatial elements of the data relate to the surface of the Earth (or other bodies).
<!-- Coordinates are meaningles without a CRS, as we don't know theirs units (meters, feets, degrees) or what's the origin -->
<!-- (-12579102, 4439107) = (-113, 37) -->
Coordinate system could be either geographic or projected (Figures \@ref(fig:vector-crs) and \@ref(fig:raster-crs)).

### Geographic coordinate systems

Geographic coordinate systems identify any location on the Earth's surface using two values - longitude and latitude. 
The first one is an angle from the prime meridian plan and the second one is an angle from the equatorial plane to this location.
Therefore, units of geographic coordinate systems are degrees.
<!-- for example Los Angeles, Melbourne -->

The surface of the Earth in geographic coordinate systems is represented by a spherical or ellipsoidal surface.
Spherical models represent the shape of the Earth of a specific radius, assuming that the Earth is a perfect sphere. 
While it simplifies calculations and works well for small scale maps, it could not be sufficient for the work at a larger scale.
More accurate measurements can be done with an ellipsoidal model.
The shape of an ellipse is defined by either the equatorial radius (a) and the polar radius (b), or by a and the inverse flattening (rf), where:
$$rf = 1/((a-b)/a)$$
<!--fig?-->
<!-- WGS84   a=6378137.0     rf=298.2572 -->
<!-- 1/((a-b)/a) -->
<!-- a - 1/rf * a = b -->
Since the Earth is flattened at the poles, an equatorial radius is slightly longer than a polar axis.
For example, the difference of the equatorial radius and polar radius in the WGS 84 ellipsoid is about 21.385 km.
You can access a list of available ellipses and theirs properties using the `st_proj_info(type = "ellps")` function.
<!-- ellipsoid example -->

Additionally, a position and orientation of the spheroid relative to the center of the Earth needs to be defined using a datum.
The Earth’s surface is irregular due to gravitational and surface feature variations.
Therefore, datums were created to account for the local variations in establishing a coordinate system.
There are two types of datums - local and geocentric.
In local datums, the ellipsoid surface aligns closely to the Earth surface at a particular location.
For example, NAD27 (North American Datum of 1927) is a local datum created for the United States area.
Geocentric datums are aligned to the center of the Earth
It includes WGS84 (World Geodetic System 1984) Datum.
A list of datums supported in R could be obtain with `st_proj_info(type = "datum")`.
<!-- plots? -->
<!-- plus maybe table (few examples) -->

### Projected coordinate systems 

Projected coordinate systems are based on Cartesian coordinates (X, Y) and represent any area on a flat surface. 
A projected coordinate system has an origin, x and y axes, and a linear unit of measure.
All projected coordinate systems are based on geographic coordinate systems.
Maps projections are mathematical models for conversion of three-dimensional surface into a two-dimensional representation on a map.
This transition cannot be done without adding some distortion.
Therefore, some properties of the Earth's surface are distorted in this process, such as area, direction, distance, and shape.
A projected coordinate system can preserve only one or two of those properties.
Projections are often named based on a property they preserve: equal-area preserves area, azimuthal preserve direction, equidistant preserve distance, and conformal preserve local shape.

There are three main groups of projection types - conic, cylindrical, and planar.
In a conic projection the Earth surface is projected onto a cone along a single line of tangency or two lines of tangency. 
Distortions are minimized along the tangency lines and rise with the distance from those lines in this projection.
Therefore, it is the best suited for maps of mid-latitude areas.
A cylindrical projection maps the surface onto a cylinder.
This projection also could be created by touching the Earth's surface along a single line of tangency or two lines of tangency. 
Cylindrical projections are the most often used in mapping of the entire world.
A planar projection projects data onto a flat surface touching the globe at a point or along a line of tangency. 
It is typically used in mapping polar regions.
<!-- other projections? -->
<!-- https://en.wikipedia.org/wiki/List_of_map_projections -->
<!-- plus maybe table (few examples) -->
<!-- add good reference to projections -->
`st_proj_info(type = "proj")` gives a list of the available projections supported by the PROJ.4 library.

<!-- maybe a new section - how to pick the best projection? -->
<!-- https://source.opennews.org/articles/choosing-right-map-projection/ -->

### CRS in R

Two main ways to describe CRS in R are an `epsg` code or a `proj4string` definition.
Both of these approaches have advantages and disadvantages. 
An `epsg` code is usually shorter, and therefore easier to remember. 
The code also refers to only one, well-defined coordinate reference system. 
On the other hand, a `proj4string` definition allows you more flexibility when it comes to specifying different parameters such as the projection type, the datum and the ellipsoid.^[Complete list of the `proj4string` parameters can be found at http://proj4.org/parameters.html#parameter-list.] 
This way you can specify many different projections, and modify existing ones.
This makes the `proj4string` approach also more complicated.
<!-- ^[In the background, `sf` and `raster` use the [PROJ.4](http://proj4.org/) software, which enables transformations between different projections]. -->
`epsg` points to exactly one particular CRS.

Spatial R packages support a wide range of CRSs they use long-establish [proj4](http://proj4.org/) library.
Other than searching for EPSG codes on-line, another quick way to find-out about available CRSs is via the `rgdal::make_EPSG()` function, which outputs a data frame of available projections.
Before going into more detail into these, it's worth learning how to view and filter them inside R, as this could save time trawling the internet.
The following code will show available CRSs interactively, allowing filtering of ones of interest (try filtering for the OSGB CRSs for example):


```r
crs_data = rgdal::make_EPSG()
View(crs_data)
```

In **sf** the CRS of an object can be retrieved using `st_crs()`.
For this purpose, we need to read-in a vector dataset:


```r
vector_filepath = system.file("vector/zion.gpkg", package="spDataLarge")
new_vector = st_read(vector_filepath)
```

Our new object, `new_vector`, is a polygon representing the borders of Zion National Park (`?zion`).


```r
st_crs(new_vector) # get CRS
#> Coordinate Reference System:
#>   No EPSG code
#>   proj4string: "+proj=utm +zone=12 +ellps=GRS80 +towgs84=0,0,0,0,0,0,0 +units=m +no_defs"
```

In cases when a coordinate reference system (CRS) is missing or the wrong CRS is set, the `st_set_crs()` function can be used:


```r
new_vector = st_set_crs(new_vector, 26912) # set CRS
```

The warning message informs that the `st_set_crs()` function do not transform data from one CRS to another.

<div class="figure" style="text-align: center">
<img src="figures/02_vector_crs.png" alt="Examples of geographic (WGS 84; left) and projected (NAD83 / UTM zone 12N; right) and coordinate systems for a vector data type." width="765" />
<p class="caption">(\#fig:vector-crs)Examples of geographic (WGS 84; left) and projected (NAD83 / UTM zone 12N; right) and coordinate systems for a vector data type.</p>
</div>

The `projection()` function can be use to access a CRS information from the `Raster*` object: 


```r
projection(new_raster) # get CRS
#> [1] "+proj=longlat +datum=WGS84 +no_defs +ellps=WGS84 +towgs84=0,0,0"
```

The same function, `projection()`, is used to set a CRS for raster objects.
The main difference, comparing to vector data, is that raster objects accepts only `proj4` definitions:


```r
projection(new_raster) = "+proj=utm +zone=12 +ellps=GRS80 +towgs84=0,0,0,0,0,0,0 +units=m +no_defs" # set CRS
```

<div class="figure" style="text-align: center">
<img src="figures/02_raster_crs.png" alt="Examples of geographic (WGS 84; left) and projected (NAD83 / UTM zone 12N; right) and coordinate systems for a raster data type" width="475" />
<p class="caption">(\#fig:raster-crs)Examples of geographic (WGS 84; left) and projected (NAD83 / UTM zone 12N; right) and coordinate systems for a raster data type</p>
</div>

More information on CRS and spatial tranformation is in chapter \@ref(transform).
<!-- comparing projections? == -->
<!-- - st_as_sf(x, coords = c("x","y")) -->
<!-- - st_bbox -->

## Units

<!-- https://cran.r-project.org/web/packages/units/vignettes/measurement_units_in_R.html -->
An important feature of CRSs is that they contain information about spatial units.
Clearly it is vital to know whether a house's measurements are in feet or meters, and the same applies to maps.
It is good cartographic practice to add a *scale bar* onto maps to demonstrate the relationship between distances on the page or screen and distances on the ground.
Likewise, it is important to formally specify the units in which the geometry data or pixels are measured to provide context, and ensure that subsequent calculations are done in context.

A novel feature of geometry data in `sf` objects is that they have *native support* for units.
This means that distance, area and other geometric calculations in **sf** return values that come with a `units` attribute, defined by the **units** package [@pebesma_measurement_2016].
This is advantageous because it prevents confusion caused by the fact that different CRSs use different units (most use meters, some use feet).
Furthermore, it also provides information on dimensionality, as illustrated by the following calculation which reports the area of Nigeria:


```r
nigeria = world[world$name_long == "Nigeria", ]
```


```r
st_area(nigeria)
#> 9.05e+11 m^2
```

The result is in units of square meters (m^2^), showing a) that the result represents two-dimensional space and b) and that Nigeria is a large country!
This information, stored as an attribute (which interested readers can discover with `attributes(st_area(nigeria))`) is advantageous for many reasons, for example it could feed into subsequent calculations such as population density.
Reporting units prevents confusion.
To take the Nigeria example, if the units remained unspecified, one could incorrectly assume that the units were in km^2^.
To translate the huge number into a more digestible size, it is tempting to divide the results by a million (the number of square meters in a square kilometer):


```r
st_area(nigeria) / 1e6
#> 905072 m^2
```

However, the result is incorrectly given again as square meters.
The solution is to set the correct units with the **units** package:


```r
units::set_units(st_area(nigeria), km^2)
#> 905072 km^2
```

<!-- Is that right? I mean, the units DESCRIPTION says "Support for measurement units in R vectors, matrices and arrays". Since raster datasets are just matrices, units might be easily used with them?-->
Units are of equal importance in the case of raster data.
However, so far **sf** is the only spatial package that supports units, meaning that people working on raster data should approach changes in the units of analysis (e.g., converting pixel widths from imperial to decimal units) with care.
The `new_raster` object (see above) uses a UTM projection with meters as units.
Consequently, its resolution is also given in meters but you have to know it, since the `res()` function simply returns a numeric vector.


```r
res(new_raster)
#> [1] 0.000833 0.000833
```

If we used the WGS84 projection, the units would change.


```r
repr = projectRaster(new_raster, crs = "+init=epsg:4326")
res(repr)
#> [1] 7.47e-09 7.52e-09
```

Again, the `res()` command gives back a numeric vector without any unit, forcing us to know that the unit of the WGS84 projection is decimal degrees.

<!-- Something about when units are not set: -->
<!-- ```{r} -->
<!-- st_distance(sf_point1, sf_point2) -->
<!-- ``` -->

<!-- ## Precision -->

## Exercises {#ex2}

<!-- vector exercises -->
1. What does the summary of the `geometry` column tell us about the `world` dataset, in terms of:
    - The geometry type?
    - How many countries there are?
    - The coordinate reference system (CRS)?

2. Using **sf**'s `plot()` command, create a map of Nigeria in context, building on the code that creates and plots Asia above (see Figure \@ref(fig:asia) for an example of what this could look like). 
    - Hint: this used the `lwd`, `main` and `col` arguments of `plot()`. 
    - Bonus: make the country boundaries a dotted grey line.
    - Hint: `border` is an additional argument of `plot()` for **sf**  objects.

3. What does the `cex` argument do in the `plot()` function that generates Figure \@ref(fig:contpop)?
    - Why was `cex` passed the `sqrt(world$pop) / 10000` instead of just the population directly?
    - Bonus: what equivalent arguments to `cex` exist in the dedicated vizualisation package **tmap**?
    
4. Re-run the code that 'generated' Figure \@ref(fig:contpop) at the end of \@ref(base-args) and find 3 similarities and 3 differences between the plot produced on your computer and that in the book.
    - What is similar?
    - What has changed?
    - Bonus: play around with and research base plotting arguments to make your version of Figure \@ref(fig:contpop) more attractive. Which arguments were most useful.
    - Advanced: try to reproduce the map presented in Figure \@ref(base-args). Copy-and-pasting is prohibited!

<!-- raster exercises -->
5. Read the `raster/nlcd2011.tif` file from the **spDataLarge** package. 
What kind of information can you get about the properties of this file?
<!-- (crs, ncols, nrow, ncells, bbox, navalues) -->
6. Create an empty `RasterLayer` object called `my_raster` with 10 columns and 10 rows, and resolution of 10 units.
Assign random values between 0 and 10 to the new raster and plot it.
<!-- crs exercises -->
<!-- 1. pros and cons of the projection types -->
<!-- 1. pros and cons of epsg/proj4 -->
<!-- units exercises -->
<!-- 1. ?? -->

<!--chapter:end:02-spatial-data.Rmd-->


# Attribute data operations {#attr}

## Prerequisites {-}

- This chapter requires the packages **tidyverse**, **sf** and **raster**:


```r
library(sf)
library(raster)
library(tidyverse)
```

- It also relies on **spData**, which loads `world`, `worldbank_df` and `us_states` datasets:


```r
library(spData)
```

## Introduction

Attribute data is non-spatial information associated with geographic (geometry) data.
A bus stop provides a simple example.
In a spatial vector object its position would typically be represented by latitude and longitude coordinates (geometry data), in addition to its name.
The name is an *attribute* of the feature (to use Simple Features terminology) that bears no relation to its geometry.
<!-- idea: add an example of a bus stop (or modify a previous example so it represents a bus stop) in the previous chapter  -->

Another example is the elevation value (attribute) for a specific grid cell in raster data.
Unlike vector data, the raster data model stores the coordinate of the grid cell only indirectly:
There is a less clear distinction between attribute and spatial information in raster data.
Say, we are in the 3^rd^ row and the 4^th^ column of a raster matrix.
To derive the corresponding coordinate, we have to move from the origin three cells in x-direction and four cells in y-direction with the cell resolution defining the distance for each x- and y-step.
The raster header gives the matrix a spatial dimension which we need when plotting the raster or when we want to combine two rasters, think, for instance, of adding the values of one raster to another (see also next Chapter).
<!-- should we somewhere add a table comparing advantages/disadvantages of using the vector or raster data model, would fit nicely into chapter 2 -->

This chapter focuses on non-geographic operations on vector and raster data.
For vector data, we will introduce subsetting, aggregating and joining attribute data in the next section.
Note that the corresponding functions also have a geographic equivalent.
Sometimes you can even use the same functions for attribute and spatial operations.
This is the case for subsetting as base R's `[` and tidyverse's `filter()` let you also subset spatial data based on the spatial extent of another spatial object (see Chapter \@ref(spatial-data-operations)).
Therefore the skills you learn here are cross-transferable which is also why this chapter lays the foundation for the next chapter (Chapter \@ref(spatial-data-operations)) which extends the here presented methods to the spatial world.

Raster attribute data operations are covered in Section \@ref(manipulating-raster-objects), which covers the creating continuous and categorical raster layers and extracting cell values from one layer and multiple layers (raster subsetting). 
Section \@ref(summarizing-raster-objects) provides an overview of 'global' raster operations which can be used to characterize entire raster datasets.

## Vector attribute manipulation

Geographic vector data in R are well-support by `sf`, a class which extends the `data.frame`.
Thus `sf` objects have one column per attribute variable (such as 'name') and one row per observation, or *feature* (e.g. per bus station).
`sf` objects also have a special column to contain geometry data, usually named `geometry`.
The `geometry` column is special because it is a *list-colum*, which can contain multiple geographic entities (points, lines, polygons) per row.
In Chapter \@ref(spatial-class) we saw how to perform *generic methods* such as `plot()` and `summary()` on `sf` objects.
**sf** also provides methods that allow `sf` objects to behave like regular data frames:


```r
methods(class = "sf") # methods for sf objects, first 12 shown
```


```r
#>  [1] aggregate             cbind                 coerce               
#>  [4] initialize            merge                 plot                 
#>  [7] print                 rbind                 [                    
#> [10] [[<-                  $<-                   show                 
```




Many of these functions, including `rbind()` (for binding rows of data together) and `$<-` (for creating new columns) were developed for data frames.
A key feature of `sf` objects is that they store spatial and non-spatial data in the same way, as columns in a `data.frame` (the geometry column is typically called `geometry`).

\BeginKnitrBlock{rmdnote}<div class="rmdnote">The geometry column of `sf` objects is typically called `geometry` but any name can be used.
The following command, for example, creates a geometry column named g:
  
`st_sf(data.frame(n = world$name_long), g = world$geom)`

This enables geometries imported from spatial databases to have a variety of names such as `wkb_geometry` and `the_geom`.</div>\EndKnitrBlock{rmdnote}

`sf` objects also support `tibble` and `tbl` classes used in the tidyverse, allowing 'tidy' data analysis workflows for spatial data.
Thus **sf** enables the full power of R's data analysis capabilities to be unleashed on geographic data.
Before using these capabilities it's worth re-capping how to discover the basic properties of vector data objects.
Let's start by using base R functions for to get a measure of the `world` dataset:


```r
dim(world) # it is a 2 dimensional object, with rows and columns
#> [1] 177  11
nrow(world) # how many rows?
#> [1] 177
ncol(world) # how many columns?
#> [1] 11
```

Our dataset contains ten non-geographic columns (and one geometry list-column) with almost 200 rows representing the world's countries.

Extracting the attribute data of an `sf` object is the same as removing its geometry:


```r
world_df = st_set_geometry(world, NULL)
class(world_df)
#> [1] "data.frame"
```

This can be useful if the geometry column causes problems, e.g., by occupying large amounts of RAM, or to focus the attention on the attribute data.
For most cases, however, there is no harm in keeping the geometry column because non-spatial data operations on `sf` objects only change an object's geometry when appropriate (e.g. by dissolving borders between adjacent polygons following aggregation).
This means that proficiency with attribute data in `sf` objects equates to proficiency with data frames in R.
For many applications, the tidyverse package **dplyr** offers the most effective and intuitive approach of working with data frames, hence the focus on this approach in this section.^[
Unlike objects of class `Spatial` of the **sp** package, `sf` objects are also compatible with the **tidyverse** packages **dplyr** and **ggplot2**.
The former provides fast and powerful functions for data manipulation (see [Section 6.7](https://csgillespie.github.io/efficientR/data-carpentry.html#data-processing-with-data.table) of @gillespie_efficient_2016), and the latter provides powerful plotting capabilities.
]

###  Vector attribute subsetting

Base R subsetting functions include `[`, `subset()` and  `$`.
**dplyr** subsetting functions include `select()`, `filter()`, and `pull()`.
Both sets of functions preserve the spatial components of attribute data in `sf` objects.

The `[` operator can subset both rows and columns. 
You use indices to specify the elements you wish to extract from an object, e.g., `object[i, j]`, with `i` and `j` typically being numbers or logical vectors --- `TRUE`s and `FALSE`s --- representing rows and columns (they can also be character strings, indicating row or column names).
<!-- you can also use `[`(world, 1:6, 1) -->
Leaving `i` or `j` empty returns all rows or columns, so `world[1:5, ]` returns the first five rows and all columns.
The examples below demonstrate subsetting with base R.
The results are not shown; check the results on your own computer:


```r
world[1:6, ] # subset rows by position
```


```r
world[, 1:3] # subset columns by position
```


```r
world[, c("name_long", "lifeExp")] # subset columns by name
```

A demonstration of the utility of using `logical` vectors for subsetting is shown in the code chunk below.
This creates a new object, `small_countries`, containing nations whose surface area is smaller than 10,000 km^2^:


```r
sel_area = world$area_km2 < 10000
summary(sel_area) # a logical vector
#>    Mode   FALSE    TRUE 
#> logical     170       7
small_countries = world[sel_area, ]
```

The intermediary `sel_object` is a logical vector that shows that only seven countries match the query.
A more concise command, that omits the intermediary object, generates the same result:


```r
small_countries = world[world$area_km2 < 10000, ]
```

Another the base R function `subset()` provides yet another way to achieve the same result:


```r
small_countries = subset(world, area_km2 < 10000)
```

You can use the `$` operator to select a specific variable by its name. The result is a vector:


```r
world$name_long
```

<!-- , after the package has been loaded: [or - it is a part of tidyverse] -->
Base R functions are mature and widely used.
However, the more recent **dplyr** approach has several advantages.
It enables intuitive workflows.
It's fast, due to its C++ backend and database integration, important when working with big data.
The main **dplyr** subsetting functions are `select()`, `slice()`, `filter()` and `pull()`.

<div class="rmdnote">
<p><strong>raster</strong> and <strong>dplyr</strong> packages have a function called <code>select()</code>. If both packages are loaded, this can generate error messages containing the text: <code>unable to find an inherited method for function ‘select’ for signature ‘&quot;sf&quot;’</code>. To avoid this error message, and prevent ambiguity, we use the long-form function name, prefixed by the package name and two colons (usually omitted from R scripts for concise code): <code>dplyr::select()</code>.</p>
</div>

`select()` selects columns by name or position.
For example, you could select only two columns, `name_long` and `pop`, with the following command (note the `geom` column remains):


```r
world1 = dplyr::select(world, name_long, pop)
names(world1)
#> [1] "name_long" "pop"       "geom"
```

`select()` also allows subsetting of a range of columns with the help of the `:` operator: 


```r
# all columns between name_long and pop (inclusive)
world2 = dplyr::select(world, name_long:pop)
```

Omit specific columns with the `-` operator:


```r
# all columns except subregion and area_km2 (inclusive)
world3 = dplyr::select(world, -subregion, -area_km2)
```

Conveniently, `select()` lets you subset and rename columns at the same time, for example:


```r
world4 = dplyr::select(world, name_long, population = pop)
names(world4)
#> [1] "name_long"  "population" "geom"
```

This is more concise than the base R equivalent:


```r
world5 = world[, c("name_long", "pop")] # subset columns by name
names(world5)[2] = "population" # rename column manually
```

`select()` also works with 'helper functions' for advanced subsetting operations, including `contains()`, `starts_with()` and `num_range()` (see the help page with `?select` for details).

`slice()` is the row-equivalent of `select()`.
The following code chunk, for example, selects the 3^rd^ to 5^th^ rows:


```r
slice(world, 3:5)
```

`filter()` is **dplyr**'s equivalent of base R's `subset()` function.
It keeps only rows matching given criteria, e.g., only countries with a very high average of life expectancy:


```r
# Countries with a life expectancy longer than 82 years
world6 = filter(world, lifeExp > 82)
```

The standard set of comparison operators can be used in the `filter()` function, as illustrated in Table \@ref(tab:operators): 


Table: (\#tab:operators)Table of comparison operators that result in boolean (TRUE/FALSE) outputs.

Symbol      Name                            
----------  --------------------------------
`==`        Equal to                        
`!=`        Not equal to                    
`>, <`      Greater/Less than               
`>=, <=`    Greater/Less than or equal      
`&, |, !`   Logical operators: And, Or, Not 

<!-- describe these: ==, !=, >, >=, <, <=, &, | -->
<!-- add warning about = vs == -->
<!-- add info about combination of &, |, ! -->

A benefit of **dplyr** is its compatibility with the *pipe* operator ` %>% `.
This 'R pipe', which takes its name from the Unix pipe `|` and is part of the **magrittr** package, enables expressive code by 'piping' the output of a previous command into the first argument of the next function.
This allows *chaining* data analysis commands, with the data frame being passed from one function to the next.

\BeginKnitrBlock{rmdnote}<div class="rmdnote">The **dplyr** function `pull()` extracts a single variable as a vector.</div>\EndKnitrBlock{rmdnote}

This is illustrate below, in which the `world` dataset is subset by columns (`name_long` and `continent`) and the first five rows (result not shown).


```r
world7 = world %>%
  dplyr::select(name_long, continent) %>%
  slice(1:5)
```

The above chunk shows how the pipe operator allows commands to be written in a clear order:
the above run from top to bottom (line-by-line) and left to right.
Without `%>%` one would be forced to create intermediary objects or use nested function calls, e.g.:


```r
world8 = dplyr::select(
  slice(world, 1:5),
  name_long, continent)
```

This generates the same result --- verify this with `identical(world7, world8)` --- in the same number of lines of code, but in a much more confusing way, starting with the function that is called last!

There are additional advantages of pipes from a communication perspective: they encourage adding comments to self-contained functions and allow single lines *commented-out* without breaking the code.

### Vector attribute aggregation

Aggregation operations summarize datasets by a grouping variable, which can be either another attribute column or a spatial object.
Imagine we would like to calculate the number of people per continent. 
Fortunately, our `world` dataset has the necessary ingredients, with the `pop` column containing the population per country and the grouping variable `continent`.
In base R this can be done with `aggregate()` as follows:


```r
aggregate(pop ~ continent, FUN = sum, data = world, na.rm = TRUE)
```

The result is a non-spatial data frame with six rows, one per continent, and two columns (see Table \@ref(tab:continents) with results for the top 3 most populous continents).

`summarize()` is the **dplyr** equivalent of `aggregate()`, which uses the function `group_by()` to create the grouping variable.
The tidy equivalent of the `aggregate()` method is as follows:


```r
group_by(world, continent) %>%
  summarize(pop = sum(pop, na.rm = TRUE))
```

This approach is flexible, allowing the resulting columns to be named.
Further, omitting the grouping variable puts everything on in one group.
This means `summarize()` can be used to calculate Earth's total population (~7 billion) and number of countries:


```r
world %>% 
  summarize(pop = sum(pop, na.rm = TRUE), n_countries = n())
```


```
#>        pop n_countries
#> 1 7.21e+09         177
```

The result is a spatial data frame of class `sf` (only the non-spatial results are shown): the aggregation procedure dissolves boundaries within continental land masses.
In the previous code chunk `pop` and `n_countries` are column names in the result.
`sum()` and `n()` were the aggregating functions.

Let's combine what we've learned so far about **dplyr** by chaining together functions to find the world's 3 most populous continents (with `dplyr::n()` ) and the number of countries they contain.
The output of the following code is presented in Table \@ref(tab:continents)):


```r
world %>% 
  dplyr::select(pop, continent) %>% 
  group_by(continent) %>% 
  summarize(pop = sum(pop, na.rm = TRUE), n_countries = n()) %>% 
  top_n(n = 3, wt = pop) %>%
  st_set_geometry(value = NULL) 
```



Table: (\#tab:continents)The top 3 most populous continents, and the number of countries in each.

continent         pop   n_countries
----------  ---------  ------------
Africa       1.15e+09            51
Asia         4.31e+09            47
Europe       7.39e+08            39

<!-- `sf` objects are well-integrated with the **tidyverse**, as illustrated by the fact that the aggregated objects preserve the geometry of the original `world` object. -->
<!-- Here, we even had to make some efforts to prevent a spatial operation. -->
<!-- When `aggregate()`ing the population we have just used the population vector.  -->
<!-- Had we used the spatial object (world[, "population"]), `aggregate()` would have done a spatial aggregation of the polygon data.  -->
<!-- The same would have happened, had we not dismissed the geometry prior to using the `summarize()` function. -->
<!-- We will explain this so-called 'dissolving polygons' in more detail in the the next chapter. -->

<!-- Todo (optional): add exercise exploring similarities/differences with `world_continents`? -->

<!-- should it stay or should it go (?) aka should we present the arrange function?: -->
<!-- Jannes: I would suggest to leave the arrange function as an exercise to the reader. -->

<!-- ```{r} -->
<!-- # sort variables -->
<!-- ## by name -->
<!-- world_continents %>%  -->
<!--   arrange(continent) -->
<!-- ## by population (in descending order) -->
<!-- world_continents %>%  -->
<!--   arrange(-pop) -->
<!-- ``` -->

###  Vector attribute joining

<!-- https://github.com/dgrtwo/fuzzyjoin -->
<!-- http://r4ds.had.co.nz/relational-data.html -->
<!-- non-unique keys -->

Combining data from different sources is a common task in data preparation. 
Joins do this by combining tables based on a shared 'key' variable.
**dplyr** has powerful functions for joining: `left_join()`, `right_join()`,  `inner_join()`, `full_join`, `semi_join()` and `anti_join()`.
These function names follow conventions used in the database language [SQL](http://r4ds.had.co.nz/relational-data.html) [@grolemund_r_2016, Chapter 13].
Using them with `sf` objects is the focus of this section.
**dplyr** join functions work the same on data frames and `sf` objects, the only important difference being the `geometry` list column.
The result of data joins can be either an `sf` or `data.frame` object.

Most joins involving spatial data will have an `sf` object as the first argument and a `data.frame` object as the second argument, resulting in a new `sf` object (the reverse order is also possible and will return a `data.frame`).
We will focus on the commonly used left and inner joins, which use the same syntax as the other join types [see @grolemund_r_2016 for more join types].

The easiest way to understand the concept of joins is to show how they work with a smaller dataset. 
We will use an `sf` object `north_america` with country codes (`iso_a2`), names and geometries, as well as a `data.frame` object `wb_north_america` containing information about urban population and unemployment for three countries.
Note that `north_america` contains data about Canada, Greenland and the United States but the World Bank dataset (`wb_north_america`) contains information about Canada, Mexico and the United States:


```r
north_america = world %>%
  filter(subregion == "Northern America") %>%
  dplyr::select(iso_a2, name_long)
north_america$name_long
#> [1] "Canada"        "Greenland"     "United States"
```



```r
wb_north_america = worldbank_df %>% 
  filter(name %in% c("Canada", "Mexico", "United States")) %>%
  dplyr::select(name, iso_a2, urban_pop, unemploy = unemployment)
```

We will use a left join to combine the two datasets.
Left joins are the most commonly used operation for adding attributes to spatial data, as they return all observations from the left object (`north_america`) and the matched observations from the right object (`wb_north_america`) in new columns.
Rows in the left object without matches in the right (`Greenland` in this case) result in `NA` values.

To join two objects we need to specify a key.
This is a variable (or a set of variables) that uniquely identifies each observation (row). 
The `by` argument of **dplyr**'s join functions lets you identify the key variable. 
In simple cases, a single, unique variable exist in both objects like the `iso_a2` column in our example (you may need to rename columns with identifying information for this to work):


```r
left_join1 = north_america %>% 
  left_join(wb_north_america, by = "iso_a2")
```

This has created a spatial dataset with the new variables added.
The utility of this is shown in Figure \@ref(fig:unemploy), which shows the unemployment rate (a World Bank variable) across the countries of North America.

<div class="figure" style="text-align: center">
<img src="figures/unemploy-1.png" alt="The unemployment rate (taken from World Bank statistics) in Canada and the United States to illustrate the utility of joining attribute data on to spatial datasets." width="576" />
<p class="caption">(\#fig:unemploy)The unemployment rate (taken from World Bank statistics) in Canada and the United States to illustrate the utility of joining attribute data on to spatial datasets.</p>
</div>

It is also possible to join objects by different variables.
Both of the datasets have variables with names of countries, but they are named differently.
The `north_america` has a `name_long` column and the `wb_north_america` has a `name` column.
In these cases a named vector, such as `c("name_long" = "name")`, can specify the connection:


```r
left_join2 = north_america %>% 
  left_join(wb_north_america, by = c("name_long" = "name"))
names(left_join2)
#> [1] "iso_a2.x"  "name_long" "iso_a2.y"  "urban_pop" "unemploy"  "geom"
```

Note that the result contains two duplicated variables - `iso_a2.x` and `iso_a2.y` because both `x` and `y` objects have the column `iso_a2`.
This can be solved by specifying all the keys:


```r
left_join3 = north_america %>% 
  left_join(wb_north_america, by = c("iso_a2", "name_long" = "name"))
```

Joins also work when a data frame is the first argument.
This keeps the geometry column but drops the `sf` class, returning a `data.frame` object.


```r
# keeps the geom column, but drops the sf class
left_join4 = wb_north_america %>%
  left_join(north_america, by = c("iso_a2"))
class(left_join4)
#> [1] "data.frame"
```

\BeginKnitrBlock{rmdnote}<div class="rmdnote">In most cases the geometry column is only useful in an `sf` object.
The geometry column can only be used for creating maps and spatial operations if R 'knows' it is a spatial object, defined by a spatial package such as **sf**.
Fortunately non-spatial data frames with a geometry list column (like `left_join4`) can be coerced into an `sf` object as follows: `st_as_sf(left_join4)`. </div>\EndKnitrBlock{rmdnote}

<!-- On the other hand, it is also possible to remove the geometry column of `left_join4` using base R functions or `dplyr`. -->
<!-- Here, this is this simple because the geometry column is just another `data.frame` column and no longer the sticky geometry column of an `sf` object (see also Chapter \@ref(spatial-class)): -->

<!-- ```{r} -->
<!-- # base R -->
<!-- left_join4_df = subset(left_join4, select = -geom) -->
<!-- # or dplyr -->
<!-- left_join4_df = left_join4 %>% dplyr::select(-geom) -->
<!-- left_join4_df -->
<!-- class(left_join4_df) -->
<!-- ``` -->

In contrast to `left_join()`, `inner_join()` keeps only observations from the left object (`north_america`) where there are matching observations in the right object (`wb_north_america`). 
All columns from the left and right object are still kept:


```r
inner_join1 = north_america %>% 
  inner_join(wb_north_america, by = c("iso_a2", "name_long" = "name"))
inner_join1$name_long
#> [1] "Canada"        "United States"
```

### Creating attributes and removing spatial information
<!-- lubridate? -->

Often, we would like to create a new column based on already existing columns.
For example, we want to calculate population density for each country.
For this we need to divide a population column, here `pop`, by an area column , here `area_km2` with unit area in square km.
Using base R, we can type:


```r
world_new = world # do not overwrite our original data
world_new$pop_dens = world_new$pop / world_new$area_km2
```

Alternatively, we can use one of **dplyr** functions - `mutate()` or `transmute()`.
`mutate()` adds new columns at the penultimate position in the `sf` object (the last one is reserved for the geometry):


```r
world %>% 
  mutate(pop_dens = pop / area_km2)
```

The difference between `mutate()` and `transmute()` is that the latter skips all other existing columns (except for the sticky geometry column):


```r
world %>% 
  transmute(pop_dens = pop / area_km2)
```

Existing columns could be also paste together using `unite()`. 
For example, we want to stick together `continent` and `region_un` columns into a new `con_reg` column.
We could specify a separator to use between values and if input columns should be removed:

<!-- todo: set eval = TRUE when travis issue resolved -->


```r
world_unite = world %>%
  unite("con_reg", continent:region_un, sep = ":", remove = TRUE)
```

The `separate()` function is the complement of the `unite()` function.
Its role is to split one column into multiple columns using either a regular expression or character position.


```r
world_separate = world_unite %>% 
  separate(con_reg, c("continent", "region_un"), sep = ":")
```



Two helper functions, `rename()` and `set_names` can be used to change columns names.
The first one, `rename()` replace an old name with a new one.
For example, we want to change a name of column from `name_long` to `name`:


```r
world %>% 
  rename(name = name_long)
```

`set_names` can be used to change names of many columns. 
In this function, we do not need to provide old names: 


```r
new_names = c("ISO_A2", "Name", "Continent", "Region", "Subregion", 
              "Country_type", "Area_in_km2", "Population", "Life_Expectancy",
              "GDP_per_capita", "geom")
world %>% 
  set_names(new_names)
```

It is important to note that the attribute data operations preserve the geometry of the simple features.
As mentioned at the outset of the chapter, however, it can be useful to remove the geometry.
Do do this, you have to explicitly remove it because `sf` explicitly makes the geometry column sticky.
This behavior ensures that data frame operations do not accidentally remove the geometry column.
Hence, an approach such as `select(world, -geom)` will be unsuccessful instead use `st_set_geometry()`^[Note that
`st_geometry(world_st) = NULL`
also works to remove the geometry from `world` but overwrites the original object.
].


```r
world_data = world %>% st_set_geometry(NULL)
class(world_data)
#> [1] "data.frame"
```

\BeginKnitrBlock{rmdnote}<div class="rmdnote">More details are provided in the help pages (which can be accessed via `?summarize` and `vignette(package = "dplyr")` and Chapter 5 of [R for Data Science](http://r4ds.had.co.nz/transform.html#grouped-summaries-with-summarize). </div>\EndKnitrBlock{rmdnote}

## Manipulating raster objects

In contrast to the vector data model underlying simple features (which represents points, lines and polygons as discrete entities in space), raster data represent continuous surfaces.
This section shows how raster objects work, by creating them *from scratch*, building on section \@ref(an-introduction-to-raster).
Because of their unique structure, subsetting and other operations on raster datasets work in a different way, as demonstrated in section \@ref(raster-subsetting).

The following code recreates the raster dataset used in section \@ref(raster-classes), the result of which is illustrated in Figure \@ref(fig:cont-cate-rasters).
This demonstrates how the `raster()` function works to create an example raster named `elev` (representing elevations).


```r
elev = raster(nrow = 6, ncol = 6, res = 0.5,
              xmn = -1.5, xmx = 1.5, ymn = -1.5, ymx = 1.5,
              vals = 1:36)
```

The result is a raster object with 6 rows and 6 columns (specified by the `nrow` and `ncol` arguments), and minimum and a minimum and maximum spatial extent (specified by `xmn`, `xmx` and equivalent arguments for the y axis).
The `vals` argument sets the values that each cell contains: numeric data ranging from 1 to 36 in this case.
Raster objects can also contain categorical values of class `logical` or `factor` variables in R.
The following code creates a raster representing grain sizes (Figure \@ref(fig:cont-cate-rasters)):


```r
grain_order = c("clay", "silt", "sand")
grain_char = sample(grain_order, 36, replace = TRUE)
grain_fact = factor(grain_char, levels = grain_order)
grain = raster(nrow = 6, ncol = 6, res = 0.5, 
               xmn = -1.5, xmx = 1.5, ymn = -1.5, ymx = 1.5,
               vals = grain_fact)
```

\BeginKnitrBlock{rmdnote}<div class="rmdnote">`raster` objects can contain values of class `numeric`, `integer`, `logical` or `factor`, but not `character`.
To use character values they must first be converted into an appropriate class, for example using the function `factor()`. 
The `levels` argument was used in the preceding code chunk to create an ordered factor:
clay < silt < sand in terms of grain size.
See the [Data structures](http://adv-r.had.co.nz/Data-structures.html) chapter of [@wickham_advanced_2014] for further details on classes.</div>\EndKnitrBlock{rmdnote}

`raster` objects represent categorical variables as integers, so `grain[1, 1]` returns a number that represents a unique identifiers, rather than "clay", "silt" or "sand". 
The raster object stores the corresponding look-up table or "Raster Attribute Table" (RAT) as a data frame in a new slot named `attributes`, which can be viewed with `ratify(grain)` (see `?ratify()` for more information).
Use the function `levels()` to retrieve the attribute table and add additional factor values:


```r
levels(grain)[[1]] = cbind(levels(grain)[[1]], wetness = c("wet", "moist", "dry"))
levels(grain)
#> [[1]]
#>   ID VALUE wetness
#> 1  1  clay     wet
#> 2  2  silt   moist
#> 3  3  sand     dry
```

This behavior demonstrates that raster cells can only possess one value, an identifier which can be used to look up the attributes in the corresponding attribute table (stored in a slot named `attributes`).
This is illustrated in command below, which returns the grain size and wetness of cell IDs 1, 12 and 36, we can run:


```r
factorValues(grain, grain[c(1, 12, 36)])
#>   VALUE wetness
#> 1  sand     dry
#> 2  clay     wet
#> 3  silt   moist
```


<div class="figure" style="text-align: center">
<img src="figures/03_cont_categ_rasters.png" alt="Raster with numberic values (left) and a raster with categorical values (right)." width="765" />
<p class="caption">(\#fig:cont-cate-rasters)Raster with numberic values (left) and a raster with categorical values (right).</p>
</div>

### Raster subsetting

Raster subsetting is done with the base R operator `[`, which accepts a variety of inputs:

- row-column indexing
- cell IDs
- coordinates
- another raster object

The latter two represent spatial subsetting (see the next chapter).
The first two subsetting options are demonstrated in the commands below ---
both return the value of the top left pixel in the raster object `elev` (results not shown):


```r
# row 1, column 1
elev[1, 1]
# cell ID 1
elev[1]
```

To extract all values or complete rows, you can use `values()` and `getValues()`.
For multi-layered raster objects `stack` or `brick`, this will return the cell value(s) for each layer.
For example, `stack(elev, grain)[1]` returns a matrix with one row and two columns --- one for each layer.
<!-- In this example we have used cell ID subsetting, of course, you can also use row-column or coordinate indexing. -->
For multi-layer raster objects another way to subset is with `raster::subset()`, which extracts layers from a raster stack or brick. The `[[` and `$` operators can also be used:


```r
r_stack = stack(elev, grain)
names(r_stack) = c("elev", "grain")
# three ways to extract a layer of a stack
raster::subset(r_stack, "elev")
r_stack[["elev"]]
r_stack$elev
```

Cell values can be modified by overwriting existing values in conjunction with a subsetting operation.
The following code chunk, for example, sets the upper left cell of `elev` to 0:


```r
elev[1, 1] = 0
elev[]
#>  [1]  0  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23
#> [24] 24 25 26 27 28 29 30 31 32 33 34 35 36
```

Leaving the square brackets empty is a shortcut version of `values()` for retrieving all values of a raster.
Multiple cells can also be modified in this way:


```r
elev[1, 1:2] = 0
```

### Summarizing raster objects

**raster** contains functions for extracting descriptive statistics for entire rasters.
Printing a raster object to the console by default, by typing its name, returns minimum and maximum values of a raster.
`summary()` provides common descriptive statistics (minimum, maximum, interquartile range and number of `NA`s).
Further summary operations such as the standard deviation (see below) or custom summary statistics can be calculated with `cellStats()`. 


```r
cellStats(elev, sd)
```

\BeginKnitrBlock{rmdnote}<div class="rmdnote">If you provide the `summary()` and `cellStats()` functions with a raster stack or brick object, they will summarize each layer separately, as can be illustrated by running `summary(brick(elev, grain))`.</div>\EndKnitrBlock{rmdnote}

Raster value statistics can be visualized in a variety of ways.
Raster values, e.g. returned by `values()` or `getValues()`, can be plotted in a variety of ways, including with `boxplot()`, `density()`, `hist()` and `pairs()`, which work for raster objects, as demonstrated in the histogram created with the command below (not shown):


```r
hist(elev)
```

Descriptive raster statistics belong to the so-called global raster operations.
These and other typical raster processing operations are part of the map algebra scheme which are covered in the next chapter.

<div class="rmdnote">
<p>Some function names clash between packages (e.g., <code>select</code>, as discussed in a previous note). In addition to not loading packages by referring to functions verbosely (e.g., <code>dplyr::select()</code>) another way to prevent function names clashes is by unloading the offending package with <code>detach()</code>. The following command, for example, unloads the <strong>raster</strong> package (this can also be done in the <em>package</em> tab in the right-bottom pane in RStudio): <code>detach(&quot;package:raster&quot;, unload = TRUE, force = TRUE)</code>. The <code>force</code> argument makes sure that the package will be detached even if other packages depend on it. This, however, may lead to a restricted usability of packages depending on the detached package, and is therefore not recommended.</p>
</div>

## Exercises

For these exercises we will use the `us_states` and `us_states_df` datasets from the **spData** package:


```r
library(spData)
data(us_states)
data(us_states_df)
```

`us_states` is a spatial object (of class `sf`), containing geometry and a few attributes (including name, region, area, and population) of states within the contiguous United States.
`us_states_df` is a data frame (of class `data.frame`) containing the name and additional variables (including median income and poverty level, for years 2010 and 2015) of US states, including Alaska, Hawaii and Puerto Rico.
The data comes from the US Census Bureau, and is documented in `?us_states` and `?us_states_df`.

<!-- Attribute subsetting -->
1. Create a new object called `us_states_name` that contains only the `NAME` column from the `us_states` object. 
What is the class of the new object? <!--why there is a "sf" part? -->
2. Select columns from the `us_states` object which contain population data.
Obtain the same result using a different command (bonus: try to find three ways of obtaining the same result).
Hint: try to use helper functions, such as `contains` or `starts_with` from **dplyr** (see `?contains`).
3. Find all states with the following characteristics (bonus find *and* plot them):
    - Belong to the Midwest region.
    - Belong to the West region, have an area below 250,000 km^2^ *and* in 2015 a population greater than 5,000,000 residents (hint: you may need to use the function `units::set_units()` or `as.numeric()`).
    - Belong to the South region, had an area larger than 150,000 km^2^ or a total population in 2015 larger than 7,000,000 residents.
<!-- Attribute aggregation -->
4. What was the total population in 2015 in the `us_states` dataset?
What was the minimum and maximum total population in 2015?
5. How many states are there in each region?
6. What was the minimum and maximum total population in 2015 in each region?
What was the total population in 2015 in each region?
<!-- Attribute joining -->
7. Add variables from `us_states_df` to `us_states`, and create a new object called `us_states_stats`.
What function did you use and why?
Which variable is the key in both datasets?
What is the class of the new object?
8. `us_states_df` has two more variables than `us_states`.
How you can find them? (hint: try to use the `dplyr::anti_join` function)
<!-- Attribute creation -->
9. What was the population density in 2015 in each state?
What was the population density in 2010 in each state?
10. How much has population density changed between 2010 and 2015 in each state?
Calculate the change in percentages and map them.
11. Change the columns names in `us_states` to lowercase. (Hint: helper functions - `tolower()` and `colnames()` may help).
<!-- Mixed exercises -->
<!-- combination of use of select, mutate, group_by, summarize, etc  -->
12. Using `us_states` and `us_states_df` create a new object called `us_states_sel`.
The new object should have only two variables - `median_income_15` and `geometry`.
Change the name of the `median_income_15` column to `Income`.
13. Calculate the change in median income between 2010 and 2015 for each state.
Bonus: what was the minimum, average and maximum median income in 2015 for each region?
What is the region with the largest increase of the median income?
<!-- Raster exercises -->
14. Create a raster from scratch with nine rows and columns and a resolution of 0.5 decimal degrees (WGS84).
Fill it with random numbers.
Extract the values of the four corner cells. 
15. What is the most common class of our example raster `grain` (hint: `modal()`)?
16. Plot the histogram and the boxplot of the `data(dem, package = "RQGIS")` raster. 
17. Now attach also `data(ndvi, package = "RQGIS")`. 
Create a raster stack using `dem` and `ndvi`, and make a `pairs()` plot

<!--chapter:end:03-attribute-operations.Rmd-->


# Spatial data operations

## Prerequisites {-}

- This chapter requires the packages **tidyverse**, **sf** and **raster**. 


```r
library(sf)
library(tidyverse)
library(raster)
```

- It also relies on **spData**, which loads datasets used in examples in the chapter:


```r
library(spData)
```

## Introduction

Spatial operations are a vital part of geocomputation.
This chapter shows how spatial objects can be modified in a multitude of ways based on their location and shape.
The content builds on the previous chapter because many spatial operations have a non-spatial (attribute) equivalent.
Spatial operations on *vector* objects include spatial subsetting (covered in section \@ref(spatial-subsetting)) and spatial joining (section \@ref(spatial-joining)).
This content builds on section \@ref(vector-attribute-manipulation) in the previous chapter.
Spatial operations on *rasters* include merging and subsetting, covered in section \@ref(spatial-operations-on-raster-data).

The chapter also introduces new concepts that are unique to spatial data.
A variety of *topological relations* can be used to subset/join vector geometries (by default **sf** uses the catch-all *intersects* but other relations such as *within* can be very useful), a topic that is explored in section \@ref(topological-relations).
Spatial operations on raster datasets involve *map algebra* (covered in sections \@ref(map-algebra) to \@ref(global-operations-and-distances)) and raster merging (covered in sections \@ref(merging-rasters)).

Another unique aspect of spatial objects is distance.
All spatial objects are related through space and distance calculations can be used to find the strength of this relationship between spatial entities.
Distance operations are covered in sections \@ref(distance-relations) and \@ref(global-operations-and-distances) for vector and raster datasets respectively.

\BeginKnitrBlock{rmdnote}<div class="rmdnote">It is important to note that spatial operations that use two spatial objects rely on both objects having the same coordinate reference system, a topic that was introduced in \@ref(crs-intro) and which will be covered in more depth in Chapter 6.</div>\EndKnitrBlock{rmdnote}

## Spatial operations on vector data

This section provides an overview of spatial operations on vector geographic data represented as simple features in the **sf** package before section \@ref(spatial-operations-on-raster-data), which presents spatial methods using the **raster** package.

### Spatial subsetting

Spatial subsetting is the process of selecting features of a spatial object based on whether or not they in some way *relate* in space to another object.
It is analogous to *attribute subsetting* (covered in section \@ref(vector-attribute-subsetting)) and can be done with the base R square bracket (`[`) operator or with the `filter()` function from the **tidyverse**.

An example of spatial subsetting is provided by the `nz` and `nz_height` datasets in **spData**.
These contain projected data on the 16 main regions and 101 highest points in New Zealand respectively (Figure \@ref(fig:nz-subset)).
The following code chunk first creates an object representing Canterbury, then uses spatial subsetting to return all high points in the region:


```r
canterbury = nz %>% filter(REGC2017_NAME == "Canterbury Region")
canterbury_height = nz_height[canterbury, ]
```

<div class="figure" style="text-align: center">
<img src="figures/nz-subset-1.png" alt="Illustration of spatial subsetting with red triangles representing height points in New Zealand. The right-hand map contains only points in the Canterbury region (highlighted in grey). The points were subset with `nz_height[canterbury, ]`." width="576" />
<p class="caption">(\#fig:nz-subset)Illustration of spatial subsetting with red triangles representing height points in New Zealand. The right-hand map contains only points in the Canterbury region (highlighted in grey). The points were subset with `nz_height[canterbury, ]`.</p>
</div>

Like attribute subsetting `x[y, ]` subsets features of *target* object `x` using the contents of a *source* object `y`.
Instead of `y` being of class `logical` or `integer` --- a vector of `TRUE` and `FALSE` values or whole numbers --- for spatial subsetting it is another spatial (`sf`) object.

Various *topological relations* can be used for spatial subsetting.
These determine the type of spatial relationship that features in the target object must have with the subsetting object to be selected, including *touches*, *crosses* or *within* (see section \@ref(topological-relations)). 
*Intersects* is the default spatial subsetting operator, a default that returns `TRUE` for many types of spatial relations, including *touches*, *crosses* and *is within*.
These alternative spatial operators can be specified with the `op =` argument, as illustrated below (try plotting the result or skip to section \@ref(topological-relations) to find out what this does):


```r
nz_height[canterbury, , op = st_disjoint]
```

\BeginKnitrBlock{rmdnote}<div class="rmdnote">Interested readers can see this default value of `op` set in the first line of the function call by entering its long-form name into the console `` sf:::`[.sf` ``.
The `?sf` help page documents this also.</div>\EndKnitrBlock{rmdnote}

Another way of doing spatial subsetting relies on the ability of *topological operators* to return `logical` objects by setting the `sparse` argument to `FALSE`:


```r
sel = st_intersects(x = nz_height, y = canterbury, sparse = FALSE)
canterbury_height2 = nz_height[sel, ]
```

The preceding code chunk created an intermediary object named `sel`, short for selection, containing only `TRUE` and `FALSE` values.
This 'selection object' also works with `filter()`, introduced in section \@ref(vector-attribute-subsetting):


```r
canterbury_height3 = nz_height %>% filter(sel)
```

For many applications this is all you'll need to know about spatial subsetting and if this is the case, you can safely skip to the next section (\@ref(topological-relations)).
If you're interested in the details --- specifically the differences between `canterbury_height3` and the other `canterbury_height` objects, and the nature of `sel` --- read-on.

At this point there are three versions of `canterbury_height`, one created with spatial subsetting directly and the other two via the intermediary object `sel`.
We can test whether they are identical as follows:


```r
identical(x = canterbury_height, y = canterbury_height2)
#> [1] TRUE
identical(x = canterbury_height, y = canterbury_height3)
#> [1] FALSE
```

What is different about `canterbury_height3`?
The only difference is that `filter()` changed the row names:


```r
row.names(canterbury_height)[1:3]
#> [1] "5" "6" "7"
row.names(canterbury_height3)[1:3]
#> [1] "1" "2" "3"
```

If the row names are re-set, the objects become identical:


```r
attr(canterbury_height3, "row.names") = attr(x = canterbury_height, "row.names")
identical(canterbury_height, canterbury_height3)
#> [1] TRUE
```

<div class="rmdnote">
<p>This discarding of row names is not something that is specific to spatial data, as illustrated in the code chunk below. <strong>dplyr</strong> discards row names by design. For further discussion of this decision, and some controversy, see the (closed) issue <a href="https://github.com/tidyverse/dplyr/issues/366">#366</a> in the package's issue tracker.</p>
</div>

But what is `sel`?
It is not, as one might imagine, a `logical` vector.
It is a `logical` two-dimensional object, a *matrix*.
`sel` has one row per feature in the target object (`nz_height`) and a column per feature in the subsetting object (`canterbury`).
Cell `sel[i, j]` is `TRUE` if the i^th^ feature in the target object intersects with the j^th^ feature in the subsetting object.
If there is more than 1 feature in `y` the resulting selection `matrix` must be converted into a `vector` before it is used for subsetting, as illustrated below:


```r
co = nz %>% filter(grepl("Cant|Otag", REGC2017_NAME))
sel_matrix = st_intersects(nz_height, co, sparse = FALSE)
sel_vector = rowSums(sel_matrix) > 0
heights_co = nz_height[sel_vector, ]
```

The above code chunk results in an object, `heights_co`, that represent the high points that intersect with either Canterbury *or* Otago region (hence the object name `co`).
It did this in four stages:

1. Subset the regions of `nz` containing "Cant" or "Otago" in their names. This was done using the pattern matching function `grepl()` in combination with the `|` character, which means 'or', resulting in the subsetting object `co`.
2. Create a selection matrix representing which features of `nz_height` intersect with the regions in `co`.
3. Convert the selection matrix into a `logical` 'selection vector' by using `rowSums()` to find which features matched *any* features in `co`.
4. Use the result to subset `nz_heights`, creating a new object `heights_co`. 

The nature of `sel_matrix` is verified below:


```r
class(sel_matrix)
#> [1] "matrix"
typeof(sel_matrix)
#> [1] "logical"
dim(sel_matrix)
#> [1] 101   2
```


### Topological relations

<!-- http://lin-ear-th-inking.blogspot.com/2007/06/subtleties-of-ogc-covers-spatial.html -->
<!-- https://edzer.github.io/sfr/articles/sf3.html -->
<!-- https://github.com/edzer/sfr/wiki/migrating#relevant-commands-exported-by-rgeos -->
<!-- Relations and inverse relations -->
<!-- http://desktop.arcgis.com/en/arcmap/latest/extensions/data-reviewer/types-of-spatial-relationships-that-can-be-validated.htm -->
<!-- Topological relations: + difference between datatypes -->
<!-- ?geos_binary_pred -->
<!-- Distance relations -->
<!-- Subset (1) points in polygons <-> (2) -->
Topological relations define the spatial relationships between objects.
To understand them, it helps to have some simple test data to work with.
Figure \@ref(fig:relation-objects) contains a polygon (`a`), a line (`l`) and some points (`p`), which are created in the code below.


```r
a_poly = st_polygon(list(rbind(c(-1, -1), c(1, -1), c(1, 1), c(-1, -1))))
a = st_sfc(a_poly)

l_line = st_linestring(x = matrix(c(-1, -1, -0.5, 1), , 2))
l = st_sfc(l_line)

p_matrix = matrix(c(0.5, 1, -1, 0, 0, 1, 0.5, 1), ncol = 2)
p_multi = st_multipoint(x = p_matrix)
p = st_sf(st_cast(st_sfc(p_multi), "POINT"))
```

<div class="figure" style="text-align: center">
<img src="figures/relation-objects-1.png" alt="Points (p 1 to 4), line and polygon objects arranged to demonstrate spatial relations." width="576" />
<p class="caption">(\#fig:relation-objects)Points (p 1 to 4), line and polygon objects arranged to demonstrate spatial relations.</p>
</div>

A simple query is: which of the points in `p` intersect in some way with polygon `a`?
The question can be answered by inspection (points 1 and 2 are over or touch the triangle).
It can also be answered by using the topological relation *intersects*, implemented in **sf** as follows:


```r
st_intersects(p, a)
#> Sparse geometry binary predicate list of length 4, where the predicate was `intersects'
#>  1: 1
#>  2: 1
#>  3: (empty)
#>  4: (empty)
```

The contents of the result should be as you expected:
the function returns a positive (`1`) result for the first two points, and a negative result (represented by an empty vector) for the last two.
What may be unexpected is that the result comes in the form of a list of vectors.
This *sparse matrix* output only registers a relation if one exists, reducing the memory requirements of topological operations on multi-feature objects.
As we saw in the previous section a *dense matrix* consisting of `TRUE` or `FALSE` values for each combination of features can also be returned when `sparse = FALSE`:


```r
st_intersects(p, a, sparse = FALSE)
#>       [,1]
#> [1,]  TRUE
#> [2,]  TRUE
#> [3,] FALSE
#> [4,] FALSE
```

The output is a matrix in which each row represents a feature in the target object and each column represents a feature in in the selecting object.
In this case only the first two features in `p` intersect with `a` and there is only one feature in `a` so the result has only one column.
The result can be used for subsetting as we saw in section \@ref(spatial-subsetting).

Note that `st_intersects()` returns `TRUE` for the second feature in the object `p` even though it just touches the polygon `a`: *intersects* is a 'catch-all' topological operation which identifies many types of spatial relation.

The opposite of `st_intersects()` is `st_disjoint()`, which returns only objects that do not spatially relate in any way to the selecting object (`[, 1]` ensures the output is a vector consuming one rather than four lines when printed):


```r
st_disjoint(p, a, sparse = FALSE)[, 1]
#> [1] FALSE FALSE  TRUE  TRUE
```

`st_within()` returns `TRUE` only for objects that are completely within the selecting object.
This applies only to the second object, which is inside the triangular polygon, as illustrated below:


```r
st_within(p, a, sparse = FALSE)[, 1]
#> [1]  TRUE FALSE FALSE FALSE
```

Note that although the first point is *within* the triangle, it does not *touch* any part of its border.
For this reason `st_touches()` only returns `TRUE` for the second point:


```r
st_touches(p, a, sparse = FALSE)[, 1]
#> [1] FALSE  TRUE FALSE FALSE
```

What about features that do not touch, but *almost touch* the selection object?
These can be selected using `st_is_within_distance()`, which has an additional `dist` argument.
It can be used to set how close target object need to be before they are selected.
Note that although point 4 is one unit of distance from the nearest node of `a` (at point 2 in Figure \@ref(fig:relation-objects)), it is still selected when the distance is set to 0.9.
This is illustrated in the code chunk below, the second line of which converts the lengthy list output into a `logical` object:


```r
sel = st_is_within_distance(p, a, dist = 0.9) # can only return a sparse matrix
lengths(sel) > 0
#> [1]  TRUE  TRUE FALSE  TRUE
```










<!-- Equals: -->
<!-- https://postgis.net/docs/ST_Equals.html -->

<!-- ```{r, eval=FALSE} -->
<!-- st_equals(a, b, sparse = FALSE) -->
<!-- ``` -->

<!-- Contains: -->
<!-- https://postgis.net/docs/ST_Contains.html -->
<!-- https://postgis.net/docs/ST_ContainsProperly.html -->

<!-- ```{r, eval=FALSE} -->
<!-- st_contains(a, b, sparse = FALSE) -->
<!-- st_contains_properly(a, b, sparse = FALSE) -->
<!-- ``` -->

<!-- Covers: -->
<!-- https://postgis.net/docs/ST_Covers.html -->
<!-- https://postgis.net/docs/ST_CoveredBy.html -->

<!-- ```{r, eval=FALSE} -->
<!-- st_covers(a, b, sparse = FALSE) -->
<!-- st_covered_by(a, b, sparse = FALSE) -->
<!-- ``` -->

<!-- Within: -->
<!-- https://postgis.net/docs/ST_Within.html -->

<!-- ```{r, eval=FALSE} -->
<!-- st_within(a, b, sparse = FALSE) -->
<!-- ``` -->

<!-- Overlaps: -->
<!-- https://postgis.net/docs/ST_Overlaps.html -->

<!-- ```{r, eval=FALSE} -->
<!-- st_overlaps(a, b, sparse = FALSE) -->
<!-- ``` -->

<!-- Intersects: -->
<!-- https://postgis.net/docs/ST_Intersects.html -->

<!-- ```{r, eval=FALSE} -->
<!-- st_intersects(a, b, sparse = FALSE) -->
<!-- ``` -->

<!-- Disjoint: -->
<!-- https://postgis.net/docs/ST_Disjoint.html -->

<!-- ```{r, eval=FALSE} -->
<!-- st_disjoint(a, b, sparse = FALSE) -->
<!-- ``` -->

<!-- Touches: -->
<!-- https://postgis.net/docs/ST_Touches.html -->

<!-- ```{r, eval=FALSE} -->
<!-- st_touches(a, b, sparse = FALSE) -->
<!-- ``` -->

<!-- Crosses: -->
<!-- https://postgis.net/docs/ST_Crosses.html -->

<!-- ```{r, eval=FALSE} -->
<!-- st_crosses(a, b, sparse = FALSE) -->
<!-- ``` -->

<!-- DE9-IM - https://en.wikipedia.org/wiki/DE-9IM -->
<!-- https://edzer.github.io/sfr/reference/st_relate.html -->

<!-- ```{r, eval=FALSE} -->
<!-- st_relate(a, b, sparse = FALSE) -->
<!-- ``` -->

<!-- examples (points/polygons) -->
<!-- examples (points/lines) -->
<!-- examples (lines/polygons) -->

<!-- TODO? create a series of polygons distributed evenly over the surface of the Earth and clip them. -->

<!-- ```{r} -->
<!-- set.seed(2018) -->
<!-- blob_points = st_sample(x = world, size = 2) -->
<!-- blobs = st_buffer(x = blob_points, dist = 1) -->
<!-- plot(blobs) -->


### Spatial joining 

Joining two non-spatial datasets relies on a shared 'key' variable, as described in section \@ref(vector-attribute-joining).
Spatial data joining applies the same concept, but instead relies on shared areas of geographic space.
As with attribute data joining adds a new column to the target object (the argument `x` in joining functions) from a source object (`y`).

The process is illustrated in Figure \@ref(fig:spatial-join), which shows a target object (the `asia` dataset, left) being joined to a source dataset (the three most populous cities of the world), resulting in a new attribute being added to the `joined` dataset (right).
<!-- Idea: use random points over Earth's surface to allocate data to world countries. -->
<!-- I'm not sure this is a good starting example to show how st_join works - thoughts? -->


```r
asia = world %>% 
  filter(continent == "Asia")
urb = urban_agglomerations %>% 
  filter(year == 2020) %>% 
  top_n(n = 3, wt = population_millions)
```


```r
joined = st_join(x = asia, y = urb) %>% 
  na.omit()
```


<div class="figure" style="text-align: center">
<img src="figures/spatial-join-1.png" alt="Illustration of a spatial join: the populations of the world's 3 largest agglomerations joined onto their respective countries." width="576" />
<p class="caption">(\#fig:spatial-join)Illustration of a spatial join: the populations of the world's 3 largest agglomerations joined onto their respective countries.</p>
</div>

This operation is also know as spatial overlay.
By default, `st_join()` performs a left join (see section \@ref(vector-attribute-joining)), but it can also do inner joins by setting the argument `left = FALSE`.
Like spatial subsetting, the default topological operator used by `st_join()` is `st_intersects()`.
This can be changed with the `join` argument (see `?st_join` for details).
In the example above, we have added features of a point layer to a polygon layer but there might be multiple point matches per polygon. 
Had we chosen to select the four (instead of three) most populous cities in the world, two of them would have belonged to China (Shanghai and Beijing, give it a try yourself).
In such a case `st_join()` simply adds a new row.
In our example we would have ended up with two polygons representing China.

### Non-overlapping joins

Sometimes two geographic datasets do not touch but still have a strong geographic relationship enabling joins.
The datasets `cycle_hire` and `cycle_hire_osm`, already loaded in the **spData** package, provide a good example.
Plotting them shows that they are often closely related but they do not touch, as shown in Figure \@ref(fig:cycle-hire), a base version of which is created with the following code below:


```r
plot(cycle_hire$geometry, col = "blue")
plot(cycle_hire_osm$geometry, add = TRUE, pch = 3, col = "red")
```

We can check if any points are the same `st_intersects()` as show below:


```r
any(st_touches(cycle_hire, cycle_hire_osm, sparse = FALSE))
#> [1] FALSE
```



<div class="figure" style="text-align: center">
preservece7e6abf09c14ab8
<p class="caption">(\#fig:cycle-hire)The spatial distribution of cycle hire points in London based on official data (blue) and OpenStreetMap data (red).</p>
</div>

Imagine that we need to join the `capacity` variable in `cycle_hire_osm` onto the official 'target' data contained in `cycle_hire`.
This is when a non-overlapping join is needed.
The simplest method is to use the topological operator `st_within_distance()` shown in section \@ref(topological-relations), using a treshold distance of 20 m.
Note that before performing the relation both datasets must be transformed into a projected CRS, saved as new objects denoted by the affix `P` (for projected) below:


```r
cycle_hire_P = st_transform(cycle_hire, 27700)
cycle_hire_osm_P = st_transform(cycle_hire_osm, 27700)
sel = st_is_within_distance(cycle_hire_P, cycle_hire_osm_P, dist = 20)
summary(lengths(sel) > 0)
#>    Mode   FALSE    TRUE 
#> logical     304     438
```

This shows that there are 438 points in the target object `cycle_hire_P` within the threshold distance of `cycle_hire_osm_P`.
How to retrieve the *values* associated with the respective `cycle_hire_osm_P` points?
The solution is again with `st_join()` although the additional dist argument must be specified:


```r
z = st_join(cycle_hire_P, cycle_hire_osm_P, st_is_within_distance, dist = 20)
nrow(cycle_hire)
#> [1] 742
nrow(z)
#> [1] 762
```

Note that the number of rows in the joined result is greater than the target.
This is because some cycle hire stations in `cycle_hire_P` have multiple matches in `cycle_hire_osm_P`.
To aggregate the values for the overlapping points and return the mean, we can use the aggregation methods learned in Chapter \@ref(attr), resulting in an object with the same number of rows as the target:


```r
z = z %>% 
  group_by(id) %>% 
  summarize(capacity = mean(capacity))
nrow(z) == nrow(cycle_hire)
#> [1] TRUE
```

The capacity of nearby stations can be verified by comparing a plot of the capacity of the source `cycle_hire_osm` data with the results in this new object (plots not show):


```r
plot(cycle_hire_osm["capacity"])
plot(z["capacity"])
```

<!-- Nearest neighbour analysis -->
<!-- e.g. two point's datasets (non-overlapping) -->
<!-- e.g. two point's datasets (overlapping) -->
<!-- ? topological problems of joining lines/polygons? -->
<!-- joining different types (e.g. points + polygons = geometry) -> save as GPKG? -->
<!-- `merge()`; `st_interpolate_aw()` -->


<!--### Modifying geometry data; still need to change the corresponding cross-references-->

The result of this join has used a spatial operation to change the attribute data associated with simple features but the geometry associated with each feature has remained unchanged.
In the subsequent sections, we will present spatial operations that also act on and modify the underlying geometry, namely dissolving, aggregating and clipping operations.

### Spatial data aggregation

Like attribute data aggregation, covered in section \@ref(vector-attribute-aggregation), spatial data aggregation (also known as dissolving polygons) can be a way of *condensing* data.
Aggregated data show some statistic about a variable (typically average or total) in relation to some kind of *grouping variable*.
Section \@ref(vector-attribute-aggregation) demonstrated how `aggregate()` and `group_by() %>% summarize()` condense data based on attribute variables.
This section demonstrates how the same functions work using spatial grouping variables.

Returning to the example of New Zealand, imagine you want to find out the average height of high points in each region.
This is a good example of spatial aggregation: it is the geometry of the source (`y` or `nz` in this case) that defines how values in the target object (`x` or `nz_height`) are grouped.
This is illustrated using the base `aggregate()` function below:


```r
nz_avheight = aggregate(nz_height, nz, FUN = mean)
```

The result of the previous command is an `sf` object with the same geometry as the (spatial) aggregating object (`nz`).^[This can be verified with `identical(nz$geometry, nz_avheight$geometry)`.]
The result of the previous operation is illustrated in Figure \@ref(fig:spatial-aggregation).
The same result can also be generated using the 'tidy' functions `group_by()` and `summarize()` (used in combination with `st_join()`):

<img src="figures/spatial-aggregation-1.png" width="576" style="display: block; margin: auto;" />



```r
nz_avheight2 = st_join(nz, nz_height) %>%
  group_by(REGC2017_NAME) %>%
  summarize(elevation = mean(elevation, na.rm = TRUE))
```

The resulting `nz_avheight` objects have the same geometry as the aggregating object `nz` but with a a new column representing the mean average height of points within each region of New Zealand (other summary functions such as `median()` and `sd()` can be used in place of `mean()`).
Note that regions containing no points have an associated `elevation` value of `NA`.
For aggregating operations which also create new geometries, see section \@ref(geometry-unions-and-aggregation).

#### Spatial congruence and areal interpolation

Spatial congruence is an important concept related to spatial aggregation.
An *aggregating object* object (which we will refer to as `y`, representing the buffer object in the previous section) is *congruent* with the target object (`x`, representing the countries in the previous section) if the two objects have shared borders.
Often this is the case for administrative boundary data, whereby the larger units (e.g., Middle Layer Super Output Areas in the UK or districts in many other European countries) are composed of many smaller units (Output Areas in this case, see [ons.gov.uk](https://www.ons.gov.uk/methodology/geography/ukgeographies/censusgeography) for further details or municipalities in many other European countries).

*Incongruent* aggregating objects, by contrast, do not share common borders with the target [@qiu_development_2012].
This is problematic for spatial aggregation (and other spatial operations) illustrated in Figure \@ref(fig:areal-example).
Areal interpolation can help to alleviate this issue.
It helps to transfer data from one set of areal units to another.
A number of algorithms have been developed for areal interpolation, including area weighted and pycnophylactic interpolation methods task [@tobler_smooth_1979].

<div class="figure" style="text-align: center">
<img src="figures/04-congruence.png" alt="Illustration of congruent (left) and incongruent (right) areal units." width="100%" />
<p class="caption">(\#fig:areal-example)Illustration of congruent (left) and incongruent (right) areal units.</p>
</div>

The simplest useful method for spatial interpolation is *area weighted* spatial interpolation.
This is implemented in `st_interpolate_aw()`, as demonstrated in the code chunk below.
In this case values from the `incongruent` object are allocated to the `aggregating_zones` in proportion to the area:


```r
agg_aw = st_interpolate_aw(incongruent["value"], aggregating_zones, extensive = FALSE)
#> Warning in st_interpolate_aw(incongruent["value"], aggregating_zones,
#> extensive = FALSE): st_interpolate_aw assumes attributes are constant over
#> areas of x
```

Instead of simply taking the mean average of each area within each aggregating feature, `st_interpolate_aw` applies a weight to each value in proportion to its area in each aggregating zone (use `extensive = TRUE` for 'spatially extensive' variables such as population which should be summed rather than averaged).
For instance, if the intersection of our buffer and a country is 100 000 km^^2^^ but the country has 1 mio square kilometers and 1 mio inhabitants, our result will obtain just a tenth of total population, in this case 100 000 inhabitants.
<!-- - `aggregate.sf()` - aggregate an sf object, possibly union-ing geometries -->
<!-- - disaggregation?? `st_cast()` - https://github.com/edzer/sfr/wiki/migrating -->
<!-- - `group_by()` + `summarise()` - potential errors -->
<!-- - ? generalization **rmapsharper** - https://github.com/ateucher/rmapshaper -->
<!-- `st_union` -->


### Distance relations

While topological relations are binary --- a feature either intersects with another or does not --- distance relations are continuous.
The distance between two objects is calculated with the `st_distance()` function.
This is illustrated in the code chunk below, which finds the distance between the highest point in New Zealand and the geographic centroid of the Canterbury region, created in section \@ref(spatial-subsetting):


```r
nz_heighest = nz_height %>% top_n(n = 1, wt = elevation)
canterbury_centroid = st_centroid(canterbury)
st_distance(nz_heighest, canterbury_centroid)
#> Units: m
#>        [,1]
#> [1,] 115566
```

There are two potentially surprising things about the result: 1) it comes with a `units` attribute, so you know that it's just over 100,000 m (not 100,000 inches, or any other measure of distance!); and 2) it is returned as a matrix, even though the result only contains a single value.
This second feature hints at another useful feature of `st_distance()`, its ability to return *distance matrices* between all combinations of features in objects `x` and `y`.
This is illustrated in the command below, which finds the distances between the first three features in `nz_height` and the Otago and Canterbury regions of New Zealand represented by the object `co`.


```r
st_distance(nz_height[1:3, ], co)
#> Units: m
#>        [,1]  [,2]
#> [1,] 123537 15498
#> [2,]  94283     0
#> [3,]  93019     0
```

Note that the distance between the second and third feature in `nz_height` and the second feature in `co` is zero.
This demonstrates the fact that distances between points and polygons refer to the distance to *any part of the polygon*:
The second and third points in `nz_height` are *in* Otago, which can be verified by plotting them (result not shown):


```r
plot(co$geometry[2])
plot(nz_height$geometry[2:3], add = TRUE)
```


## Spatial operations on raster data

This section builds on \@ref(manipulating-raster-objects), which highlights various basic methods for manipulating raster datasets, to demonstrate more advanced and explicitly spatial raster operations,
and uses the same object `elev` and `grain`.



### Spatial subsetting {#raster-subsetting}

In the previous chapter (section \@ref(manipulating-raster-objects)) we have already learned how to subset raster datasets using cell IDs and matrix indexing.
Naturally, we can subset rasters also with the help of coordinates and spatial objects.
To use coordinates for subsetting, we have to 'translate' them into the corresponding cell ID(s) or by using the `extract()` command.
This operation is also known as extracting values/attributes to points.


```r
# point within the top left pixel
elev[cellFromXY(elev, xy = c(-1.5, 1.5))]
# the same as
extract(elev, data.frame(x = -1.5, y = 1.5))
```

The `cellFromXY()` and the `extract()` command accept also a `SpatialPoints` or `SpatialPointsDataFrame` object (though not an **sf** object).
We can also use a raster object to subset another raster object (Figure \@ref(fig:raster-subset) left panel).


```r
clip = raster(nrow = 3, ncol = 3, res = 0.3, xmn = 0.9, xmx = 1.8, 
              ymn = -0.45, ymx = 0.45, vals = rep(1, 9))
elev[clip]
#> [1] 18 24
# we can also use extract
# extract(elev, extent(clip))
```

Basically, this amounts to retrieving the values of the first raster (here: `elev`) falling within the extent of a second raster (here: `clip`).
To retrieve a spatial output, we can tell R to keep the matrix structure.
This will return the two output values as a raster object.


```r
elev[clip, drop = FALSE]
#> class       : RasterLayer 
#> dimensions  : 2, 1, 2  (nrow, ncol, ncell)
#> resolution  : 0.5, 0.5  (x, y)
#> extent      : 1, 1.5, -0.5, 0.5  (xmin, xmax, ymin, ymax)
#> coord. ref. : +proj=longlat +datum=WGS84 +ellps=WGS84 +towgs84=0,0,0 
#> data source : in memory
#> names       : layer 
#> values      : 18, 24  (min, max)
```

For the same operation we can also use the `intersect()` and `crop()` command.

<div class="figure" style="text-align: center">
<img src="figures/04_raster_subset.png" alt="Subsetting raster values with the help of another raster (left). Raster mask (middle). Output of masking a raster." width="1125" />
<p class="caption">(\#fig:raster-subset)Subsetting raster values with the help of another raster (left). Raster mask (middle). Output of masking a raster.</p>
</div>

Frequently, however, we have two rasters with the same extent and resolution where one raster object serves as a mask (Figure \@ref(fig:raster-subset) middle and right panel).
In these cases `intersect()` and `crop()` are of little use.
Instead we can use the `[` again or the `mask()` and `overlay()` commands:


```r
rmask = raster(nrow = 6, ncol = 6, res = 0.5, 
               xmn = -1.5, xmx = 1.5, ymn = -1.5, ymx = 1.5,
               vals = sample(c(FALSE, TRUE), 36, replace = TRUE))
elev[rmask, drop = FALSE]
# using the mask command
mask(elev, rmask, maskvalue = TRUE)
# using overlay
# first we replace FALSE by NA
rmask[rmask == FALSE] = NA
# then we retrieve the maximum values
overlay(elev, rmask, fun = "max")
```

In the code chunk above, we have created a mask object called `rmask` randomly setting its values to `FALSE` and `TRUE`.
Next we only want to keep those values of `elev` which are `TRUE` in `rmask`, or expressed differently, we want to mask `elev` with `rmask`.
These operations are in fact Boolean local operations since we compare cell-wise two rasters.
The next subsection explores these and related operations in more detail.

### Map algebra

Map algebra makes raster processing really fast.
This is because raster datasets only implicitly store coordinates.
To derive the coordinate of a specific cell, we have to calculate it using its matrix position and the raster resolution and origin.
For the processing, however, the geographic position of a cell is barely relevant as long as we make sure that the cell position is still the same after the processing (one-to-one locational correspondence).
Additionally, if two or more raster datasets share the same extent, projection and the resolution, one could treat them as matrices for the processing.
This is exactly what map algebra is doing.
First, it checks the headers of the rasters on which to perform any algebraic operation, and only if they correspondent to each other, the processing goes on.
And secondly, map algebra retains the so-called one-to-one locational correspondence.
This is where it substantially differs from matrix algebra which changes positions when for example multiplying or dividing matrices.

Map algebra (or cartographic modeling) divides raster operations into four subclasses [@tomlin_geographic_1990], with each of them either working on one or several grids simultaneously:

1. *Local* or per-cell operations.
2. *Focal* or neighborhood operations.
Most often the output cell value is the result of a 3 x 3 input cell block.
3. *Zonal* operations are similar to focal operations but instead of a predefined neighborhood, classes, which can take on any, i.e., also an irregular size and shape, are the basis for calculations.
4. *Global* or per-raster operations, that means the output cell derives its value potentially from one or several entire rasters.

This classification scheme uses basically the number of cells involved in a processing step as distinguishing feature.
Raster operations can also be classified by discipline, for example terrain, hydrological analysis or image classifications.
The following sections explain how each type of map algebra operations can be used, with reference to worked examples (also see `vignette("Raster")` for a technical description of map algebra).

### Local operations

**Local** operations comprise all cell-by-cell operations in one or several layers.
A good example is the classification of intervals of numeric values into groups such as grouping a digital elevation model into low (class 1), middle (class 2) and high elevations (class 3).
Using the `reclassify()` command, we need first to construct a reclassification matrix, where the first column corresponds to the lower and the second column to the upper end of the class.
The third column represents the new value for the specified ranges in column one and two.
Here, we assign the raster values in the ranges 0--12, 12--24 and 24--36 are *reclassified* to take values 1, 2 and 3, respectively.


```r
rcl = matrix(c(0, 12, 1, 12, 24, 2, 24, 36, 3), ncol = 3, byrow = TRUE)
recl = reclassify(elev, rcl = rcl)
```

Raster algebra is another classical use case of local operations.
This includes adding, subtracting and squaring two rasters.
Raster algebra also allows logical operations such as finding all raster cells that are greater than a specific value (5 in our example below).
The **raster** package supports all these operations and more, as described in `vignette("Raster")` and demonstrated below (results not show):


```r
elev + elev
elev^2
log(elev)
elev > 5
```

Instead of arithmetic operators, one can also use the `calc()` and `overlay()` functions.
These functions are more efficient, hence, they are preferable in the presence of large raster datasets. 
Additionally, they allow to directly store an output file.

The calculation of the normalized difference vegetation index (NDVI) is one of the most famous local, i.e. pixel-by-pixel, raster operations.
It ranges between - 1 and 1 with positive values indicating the presence of living plants (mostly > 0.2).
To calculate the NDVI, one uses the red and near-infrared bands of remotely sensed imagery (e.g., Landsat or Sentinel imagery) exploiting the fact that vegetation absorbs light heavily in the visible light spectrum, and especially in the red channel, while reflecting it in the near-infrared spectrum.

$$
\begin{split}
NDVI&= \frac{\text{NIR} - \text{Red}}{\text{NIR} + \text{Red}}\\
\end{split}
$$
where NIR = near infrared channel
      Red = red channel

Predictive mapping is another interesting application of local raster operations.
The response variable correspond to measured or observed points in space, for example, species richness, the presence of landslides, tree disease or crop yield.
Consequently, we can easily retrieve space- or airborne predictor variables from various rasters (elevation, pH, precipitation, temperature, landcover, soil class, etc.).
Subsequently, we model our response as a function of our predictors using `lm`, `glm`, `gam` or a machine-learning technique. 
To make a spatial prediction, all we have to do, is to apply the estimated coefficients to the predictor rasters, and summing up the resulting output rasters (<!--Chapter ??; -->see also @muenchow_predictive_2013).
<!-- add reference to chapter ecological modeling -->

### Focal operations

While local functions operate on one cell, though possibly from multiple layers, **focal** operations take into account a central cell and its neighbors.
The neighborhood (also named kernel, filter or moving window) under consideration is typically of size 3-by-3 cells (that is the central cell and its eight surrounding neighbors) but can take on any other (not necessarily rectangular) shape as defined by the user.
A focal operation applies an aggregation function to all cells within the specified neighborhood, uses the corresponding output as the new value for the the central cell, and moves on to the next central cell (Figure \@ref(fig:focal-example)).
Other names for this operation are spatial filtering and convolution [@burrough_principles_2015].

In R, we can use the `focal()` function to perform spatial filtering. 
We define the shape of the moving window with a `matrix` whose values correspond to weights (see `w` parameter in the code chunk below).
Secondly, the `fun` parameter lets us specify the function we wish to apply to this neighborhood.
Here, we choose the minimum, but any other summary function, including `sum()`, `mean()`, or `var()` can be used.


```r
r_focal = focal(elev, w = matrix(1, nrow = 3, ncol = 3), fun = min)
```

<div class="figure" style="text-align: center">
<img src="figures/04_focal_example.png" alt="Input raster (left) and resulting output raster (right) due to a focal operation - summing up 3-by-3 windows." width="475" />
<p class="caption">(\#fig:focal-example)Input raster (left) and resulting output raster (right) due to a focal operation - summing up 3-by-3 windows.</p>
</div>

We can quickly check if the output meets our expectations.
In our example, the minimum value has to be always the upper left corner of the moving window (remember we have created the input raster by rowwise incrementing the cell values by one starting at the upper left corner).
In this example, the weighting matrix consists only of 1s, meaning each cell has the same weight on the output, but this can be changed.

Focal functions or filters play a dominant role in image processing.
Low-pass or smoothing filters use the mean function to remove extremes.
In the case of categorical data, we can replace the mean with the mode, which is the most common value.
By contrast, high-pass filters accentuate features.
The line detection Laplace and Sobel filters might serve as an example here.
Check the `focal()` help page how to use them in R.

Also, terrain processing uses heavily focal functions.
Think, for instance, of the calculation of the slope, aspect and flow directions.
The `terrain()` function lets you compute a few of these terrain characteristics but has not implemented all popular methods
For example, the Zevenbergen and Thorne method to compute the slope is missing.
Equally, many other terrain and GIS functions are **not** implemented in R such as curvatures, contributing areas, different wetness indexes, and many more.
Fortunately, desktop GIS commonly provide these algorithms.
In Chapter 13 we will learn how to access GIS functionality from within R.
<!-- Reference 13-gis chapter -->

### Zonal operations

*Zonal* operations are similar to focal operations.
The difference is that zonal filters can take on any shape instead of just a predefined window.
Our grain size raster is a good example (Figure \@ref(fig:cont-cate-rasters)) because the different grain sizes are spread in an irregular fashion throughout the raster.

To find the mean elevation for each grain size class, we can use the `zonal()` command.
This kind of operation is also known as *zonal statistics* in the GIS world. 


```r
z = zonal(elev, grain, fun = "mean") %>%
  as.data.frame
z
#>   zone mean
#> 1    1 21.4
#> 2    2 15.8
#> 3    3 18.2
```

This returns the statistics for each category, here the mean altitude for each grain size class and can be added to the attribute table of the ratified raster (see previous chapter).

### Global operations and distances

*Global* operations are a special case of zonal operations with the entire raster dataset representing a single zone.
The most common global operations are descriptive statistics for the entire raster dataset such as the minimum or maximum (see previous chapter).
Aside from that, global operations are also useful for the computation of distance and weight rasters.
In the first case, one can calculate the distance from each cell to a specific target cell.
For example, one might want to compute the distance to the nearest coast (see also `raster::distance()`).
We might also want to consider topography, that means, we are not only interested in the pure distance but would like also to avoid the crossing of mountain ranges when going to the coast.
To do so, we can weight the distance with elevation so that each additional altitudinal meter 'prolongs' the euclidean distance.
Visibility and viewshed computations also belong to the family of global operations<!--(in the exercises of Chapter ?? you will compute a viewshed raster)-->.
<!-- reference 13-gis chapter-->

Many map algebra operations have a counterpart in vector processing [@liu_essential_2009].
Computing a distance raster (zonal operation) while only considering a maximum distance (logical focal operation) is the equivalent to a vector buffer operation (section \@ref(clipping)).
Reclassifying raster data (either local or zonal function depending on the input) is equivalent to dissolving vector data (section \@ref(spatial-joining)). 
Overlaying two rasters (local operation), where one contains `NULL` or `NA` values representing a mask, is similar to vector clipping (section \@ref(clipping)).
Quite similar to spatial clipping is intersecting two layers (section \@ref(spatial-subsetting)). 
The difference is that two these two layers (vector or raster) simply share an overlapping area (see Figure \@ref(fig:venn-clip) for an example).
However, be careful with the wording.
Sometimes the same words have slightly different meanings for raster and vector data models.
Aggregating in the case of vector data refers to dissolving polygons while it means increasing the resolution in the case of raster data.
In fact, one could see dissolving or aggregating polygons as decreasing the resolution. 
However, zonal operations might be the better raster equivalent compared to changing the cell resolution. 
Zonal operations can dissolve the cells of one raster in accordance with the zones (categories) of another raster using an aggregation function (see above).

### Merging rasters
Suppose we would like to compute the NDVI (see section \@ref(local-operations)), and additionally want to compute terrain attributes from elevation data for observations within a study area.
Before such computations we would have to acquire airborne or remotely sensed information.
The corresponding imagery is often divided into scenes covering a specific spatial extent.
Frequently, a study area covers more than one scene.
In these cases we would like to merge the scenes covered by our study area. 
In the easiest case, we can just merge these scenes, that is put them side to side.
This is possible with digital elevation data (SRTM, ASTER).
In the following code chunk we first download the SRTM elevation data for Austria and Switzerland (for the country codes have a look at `ccodes()`).
In a second step, we merge the two rasters into one.


```r
aut = getData("alt", country = "AUT", mask = TRUE)
ch = getData("alt", country = "CHE", mask = TRUE)
aut_ch = merge(aut, ch)
```

**Raster**'s `merge()` command combines two images, and in case they overlap, it uses the value of the first raster.
You can do exactly the same with `gdalUtils::mosaic_rasters()` which is faster, and therefore recommended if you have to merge a multitude of large rasters stored on disk.

The merging approach is of little use when the overlapping values do not correspond to each other.
This is frequently the case when you want to combine spectral imagery from scenes that were taken on different dates.
The `merge()` command will still work but you will see a clear border in the resulting image.
The `mosaic()` command lets you define a function for the overlapping area. 
For instance, we could compute the mean value. 
This might smooth the clear border in the merged result but it will most likely not make it disappear.
To do so, we need a more advanced approach. 
Remote sensing scientist frequently apply histogram matching or use regression techniques to align the values of the first image with those of the second image.
The packages **landsat** (`histmatch()`, `relnorm()`, `PIF()`), **satellite** (`calcHistMatch()`) and **RStoolbox** (`histMatch()`, `pifMatch()`) provide the corresponding functions.

<!-- ## Spatial data creation -->

<!-- where should "area" example be? in this or the previous chapter? -->
<!-- Not here - I think this chapter should focus on geomtry data -->
<!-- `st_centroid()` -->
<!-- `st_buffer()` -->
<!-- http://r-spatial.org//r/2017/06/09/mapedit_0-2-0.html -->

<!-- Commented out - think this would be better in c3 (RL) -->
<!-- ```{r} -->
<!-- # add a new column -->
<!-- africa$area = set_units(st_area(africa), value = km^2) -->
<!-- africa$pop_density = africa$pop / africa$area -->

<!-- # OR -->
<!-- africa = africa %>% -->
<!--         mutate(area = set_units(st_area(.), value = km^2)) %>% -->
<!--         mutate(pop_density = pop / area) -->
<!-- ``` -->

<!-- Note that this has created a attributes for the area and population density variables: -->

<!-- ```{r} -->
<!-- attributes(africa$area) -->
<!-- attributes(africa$pop_density) -->
<!-- ``` -->

<!-- These can be set to `NULL` as follows: -->

<!-- ```{r} -->
<!-- attributes(africa$area) = NULL -->
<!-- attributes(africa$pop_density) = NULL -->
<!-- ``` -->

<!-- ## Spatial data transformation -->
<!-- changes classes; polygonize, etc-->

## Exercises

1. Write code that subsets points that are contained within `x` *and* `y` (illustrated by the plot in the 2^nd^ row and the 1^st^ column in Figure \@ref(fig:venn-clip)).
    - Create a randomly located point with the command `st_point()` (refer back to section \@ref(sfg) to see how to create spatial data 'from scratch').
2. Write code that uses functions `aggregate()` and `st_buffer()` to answers the following question: What proportion of the world's population lives in countries that intersect a circle with a 10 degree radius of the intersection between the equator and the [9^th^ meridian](https://en.wikipedia.org/wiki/9th_meridian_east)? (Advanced challenge: find the point with the highest number of people within a 10 degree radius.)


```
#> Warning in st_buffer.sfc(st_geometry(x), dist, nQuadSegs): st_buffer does
#> not correctly buffer longitude/latitude data
#> dist is assumed to be in decimal degrees (arc_degrees).
#> although coordinates are longitude/latitude, st_intersects assumes that they are planar
#> [1] 0.00998
```

3. Assuming that people are evenly distributed across countries, estimate the population living *within* the circle created to answer the previous question.


```
#> although coordinates are longitude/latitude, st_intersection assumes that they are planar
#> Warning in st_interpolate_aw(x = world["pop"], to = buff9, extensive =
#> TRUE): st_interpolate_aw assumes attributes are constant over areas of x
```

<!-- Raster exercises-->
4. Use `data(dem, package = "RQGIS")`, and reclassify the elevation in three classes: low, middle and high.
Secondly, compute the NDVI (`data(ndvi, package = "RQGIS")`) and the mean elevation for each altitudinal class.
5. Apply a line detection filter to `data(dem, package = "RQGIS")`.
6. Calculate the NDVI of a Landsat image. 
Use the Landsat image provided by the **spDataLarge** package (`system.file("raster/landsat.tif", package="spDataLarge")`).
7. This [post](https://stackoverflow.com/questions/35555709/global-raster-of-geographic-distances) shows how to compute distances to the nearest coastline using `raster::distance()`.
Retrieve a digital elevation model of Spain, and compute a raster which represents the distance to the coast.
(Hint: Have a look at `getData()` to retrieve a digital elevation model and administrative boundaries for Spain.)
Before, computing the distance raster, you might want to increase the resolution of the input dem raster, otherwise computing time might become too long. 
Secondly, weight the distance raster with elevation.
Every 100 altitudinal meters should increase the distance to the coast by 10 km.
Finally, compute the difference between the raster using the euclidean distance and the raster weighted by elevation.
(Note that this is a very simple weighting approach.
A more advanced approach might instead weight by flow direction, i.e. favor the steepest drop or the slightest increase in elevation.)

<!--chapter:end:04-spatial-operations.Rmd-->


# Geometric operations {#transform}

## Prerequisites {-}

- This chapter requires the packages **tidyverse**, **sf**, **raster**:


```r
library(tidyverse)
library(sf)
library(lwgeom)
library(raster)
```

- It also relies on **spData** and **spDataLarge**, which load `cycle_hire_osm` dataset and provide external files:


```r
library(spData)
library(spDataLarge)
```

## Introduction

As stated in Chapter \@ref(crs-intro), it is important to understand which CRS you are working in when undertaking spatial operations.
Many spatial operations assume that you are using a *projected* CRS (on a Euclidean grid with units of meters rather than a geographic 'lat/lon' grid with units of degrees).
The GEOS engine underlying most spatial operations in **sf**, for example, assumes your data is in a projected CRS.
For this reason **sf** contains a function for checking if geometries have a geographic or projected CRS.
This is illustrated below using the example of *London*:


```r
london = st_sf(geometry = st_sfc(st_point(c(-0.1, 51.5))))
st_is_longlat(london)
#> [1] NA
```

The results show that when geographic data is created from scratch, or is loaded from a source that has no CRS metadata, the CRS is unspecified by default.
CRS can be set with the `st_set_crs` function:^[CRS could be also added when creating the object with the following command: `st_sf(geometry = st_sfc(st_point(c(-0.1, 51.5))), crs = 4326)`]


```r
london = st_set_crs(london, 4326)
st_is_longlat(london)
#> [1] TRUE
```

Spatial operations on objects without a CRS run on the implicit assumption that they are projected, even when in reality they are not.
This can be seen by creating a buffer of one degree around the `london` point:


```r
london_buff = st_buffer(london, dist = 1)
#> Warning in st_buffer.sfc(st_geometry(x), dist, nQuadSegs): st_buffer does
#> not correctly buffer longitude/latitude data
#> dist is assumed to be in decimal degrees (arc_degrees).
```

Note the message warning users that the operation may not work correctly and because the distance is degrees (which is not really a measure of distance, unlike meters).
The small step of setting the CRS may seem inconsequential but has important consequences, illustrated in Figure \@ref(fig:crs-buf).
This shows how the buffer created in the geographic CRS is dramatically elongated in the north-south direction due to the thinning of the vertical lines of longitude towards the Earth's poles.  


```r
plot(london_buff, graticule = st_crs(4326), axes = TRUE)
plot(london, add = TRUE)
```

<div class="figure" style="text-align: center">
<img src="figures/crs-buf-1.png" alt="Buffer on data with geographic CRS." width="576" />
<p class="caption">(\#fig:crs-buf)Buffer on data with geographic CRS.</p>
</div>

This example does not mean that the CRS should not be set (it almost always should!) but that many spatial operations should be undertaken on projected geographic data.
The following command creates a version of the `london` reprojected onto the British National Grid CRS (EPSG:27700):


```r
london_proj = st_transform(london, crs = 27700)
```

This projected CRS has units in meters. 
One degree at the equator represents 111,320 meters and we can use this value to create our buffer:


```r
london_proj_buff = st_buffer(london_proj, 111320)
```

The result in Figure \@ref(fig:crs-buf-proj) shows that buffers based on a projected CRS are not distorted and we can expect the same distance from our point to every part of the buffer's border.


```r
plot(london_proj_buff, graticule = st_crs(27700), axes = TRUE)
plot(london_proj, add = TRUE)
```

<div class="figure" style="text-align: center">
<img src="figures/crs-buf-proj-1.png" alt="Buffer on data with projected CRS." width="576" />
<p class="caption">(\#fig:crs-buf-proj)Buffer on data with projected CRS.</p>
</div>

## Geometric operations on vector data

This section is about operations that in some way change the geometry of vector (`sf`) objects.
It is more advanced than the spatial data operations presented in the previous Chapter (in section \@ref(spatial-operations-on-vector-data)) because here we drill down into the geometry:
the functions discussed in this section work on objects of class `sfc` (simple feature geometry collections) in addition to objects of class `sf`.

### Reprojecting

While CRSs can be set manually, it is more common in real world applications to *transform* a known CRS into another.
CRS transformation could be vital to obtain proper results in many cases.
A typical example is when geometry data is provided in a geographic CRS but you want to do spatial operations, which require it to be in a projected CRS.
It includes distance measurements or area calculations.
CRS also represent spatial relationship between datasets.
Therefore, spatial operations on many datasets can only be correctly performed when all the data have the same CRS.
The most common reason to unify the CRS is to combine different datasets or apply methods which need at least two objects.
Let's use real-world examples to illustrate this.

Vector data on the most basic level is represented by individual points, and points create more complex objects, such as lines and polygons.
Spatial reprojection of vectors is a mathematical transformation of coordinates of these point.
Depending on projections used, reprojection could be either lossy or lossless.
For example, loss of spatial information could occur when the new CRS is only adequate for smaller area than input vector.
The precision could be also lost when transformation is between coordinate systems that have different datum - in those situations approximations are used.
However, in most cases CRS vector transformation is lossless.

The dataset `cycle_hire_osm` represents all cycle hire locations across London, taken from OpenStreetMap (OSM).
It is automatically loaded by the **spData** package, meaning we do not have to load it, and its CRS can be queried as follows:


```r
st_crs(cycle_hire_osm)
#> Coordinate Reference System:
#>   EPSG: 4326 
#>   proj4string: "+proj=longlat +datum=WGS84 +no_defs"
```

CRS in R can be described as an `epsg` code or a `proj4string` definition, as described in section \@ref(crs-in-r).
Let's create a new version of `cycle_hire_osm` in a projected CRS, using the `epsg` number of 27700:


```r
cycle_hire_osm_projected = st_transform(cycle_hire_osm, 27700)
st_crs(cycle_hire_osm_projected)
#> Coordinate Reference System:
#>   EPSG: 27700 
#>   proj4string: "+proj=tmerc +lat_0=49 +lon_0=-2 +k=0.9996012717 +x_0=400000 +y_0=-100000 +ellps=airy +towgs84=446.448,-125.157,542.06,0.15,0.247,0.842,-20.489 +units=m +no_defs"
```

Note that the result shows that the `epsg` has been updated and that `proj4string` element of the CRS now contains, among other things `+proj=tmerc` (meaning it is a projected CRS using the [tranverse Mercator](https://en.wikipedia.org/wiki/Transverse_Mercator_projection) projection) and `+units=m` (meaning the units of the coordinates are meters).
Another function, from the **rgdal** library, provides a note containing the name of the CRS:


```r
crs_codes = rgdal::make_EPSG()[1:2]
dplyr::filter(crs_codes, code == 27700)
#>    code                                note
#> 1 27700 # OSGB 1936 / British National Grid
```

The result shows that the EPSG code 27700 represents the British National Grid, a result that could have been found by searching online for "[CRS 27700](https://www.google.com/search?q=CRS+27700)".
The formula that converts a geographic point into a point on the surface of the Earth is provided by the `proj4string` element of the `crs` (see [proj4.org](http://proj4.org/) for further details):


```r
st_crs(27700)$proj4string
#> [1] "+proj=tmerc +lat_0=49 +lon_0=-2 +k=0.9996012717 +x_0=400000 +y_0=-100000 +ellps=airy +towgs84=446.448,-125.157,542.06,0.15,0.247,0.842,-20.489 +units=m +no_defs"
```

\BeginKnitrBlock{rmdnote}<div class="rmdnote">The EPSG code can be found inside the `crs` attribute of the object's geometry.
It is hidden from view for most of the time except when the object is printed but can be can identified and set using the `st_crs` function, for example `st_crs(cycle_hire_osm)$epsg`.</div>\EndKnitrBlock{rmdnote}

Existing CRS are well suited for most purposes.
<!-- examples -->
In the same time, `proj4string` definitions are highly modifiable and allow for CRS customization.
<!-- as we mentioned in section \@ref(crs-in-r). -->
We can present that using selected world projections.
The Mollweide projection is recommended when it is important to preserve areas [@jenny_guide_2017] (Figure \@ref(fig:mollproj)).
To use this projection, we need to specify it using the `proj4string` element, `"+proj=moll"`, in the `st_transform` function:


```r
world_mollweide = st_transform(world, crs = "+proj=moll")
```
<!-- plot(world_mollweide$geom) -->
<!-- plot(world_mollweide$geom, graticule = TRUE) -->

<div class="figure" style="text-align: center">
<img src="figures/mollproj-1.png" alt="Mollweide projection of the world" width="576" />
<p class="caption">(\#fig:mollproj)Mollweide projection of the world</p>
</div>

On the other hand, the goal for many visualization purposes is to have a map with minimized area, direction, and distance distortions.
One of the most popular projection to achieve that is Winkel tripel (Figure \@ref(fig:wintriproj)).^[This projection is used, among others, by the National Geographic Society.]
The `st_transform_proj` function allows for coordinates transformations to the Winkel tripel projection: 


```r
world_wintri = st_transform_proj(world, crs = "+proj=wintri")
```
<!-- plot(world_wintri$geom) -->
<!-- plot(world_wintri$geom, graticule = TRUE) -->

<div class="figure" style="text-align: center">
<img src="figures/wintriproj-1.png" alt="Winkel tripel projection of the world" width="576" />
<p class="caption">(\#fig:wintriproj)Winkel tripel projection of the world</p>
</div>

\BeginKnitrBlock{rmdnote}<div class="rmdnote">Two main functions for transformation of simple features coordinates are `sf::st_transform()` and `lwgeom::st_transform_proj()`. 
The `st_transform` function uses the GDAL interface to PROJ.4, while `st_transform_proj()` uses the PROJ.4 API directly.
The first one is appropriate in most situations, and provides a set of the most often used parameters and well defined transformations.
The second one allows for a greater customization of a projection, which includes cases when some of the PROJ.4 parameters (e.g. `+over`) or projection (`+proj=wintri`) is not available in `st_transform()`.</div>\EndKnitrBlock{rmdnote}

Moreover, PROJ.4 parameters can be modified in most CRS definitions.
The below code transforms the coordinates to the Lambert azimuthal equal-area projection centered on longitude and latitude of `0` (Figure \@ref(fig:laeaproj1)).


```r
world_laea1 = st_transform(world, crs = "+proj=laea +x_0=0 +y_0=0 +lon_0=0 +lat_0=0")
```
<!-- plot(world_laea1$geom) -->
<!-- plot(world_laea1$geom, graticule = TRUE) -->

<div class="figure" style="text-align: center">
<img src="figures/laeaproj1-1.png" alt="Lambert azimuthal equal-area projection of the world centered on longitude and latitude of 0" width="576" />
<p class="caption">(\#fig:laeaproj1)Lambert azimuthal equal-area projection of the world centered on longitude and latitude of 0</p>
</div>

We can change the PROJ.4 parameters, for example the center of the projection using the `+lon_0` and `+lat_0` parameters. 
The code below gives the map centered on New York City (Figure \@ref(fig:laeaproj2)).


```r
world_laea2 = st_transform(world, crs = "+proj=laea +x_0=0 +y_0=0 +lon_0=-74 +lat_0=40")
```
<!-- plot(world_laea2$geom) -->
<!-- plot(world_laea2$geom, graticule = TRUE) -->

<div class="figure" style="text-align: center">
<img src="figures/laeaproj2-1.png" alt="Lambert azimuthal equal-area projection of the world centered on New York City" width="576" />
<p class="caption">(\#fig:laeaproj2)Lambert azimuthal equal-area projection of the world centered on New York City</p>
</div>

More information about CRS modification can be found in the [Using PROJ.4](http://proj4.org/usage/index.html) documentation.

<!-- https://github.com/r-spatial/lwgeom/issues/6 -->
<!-- ```{r} -->
<!-- # devtools::install_github("r-spatial/lwgeom") -->
<!-- library(lwgeom) -->
<!-- world_3 = st_transform_proj(world, crs = "+proj=wintri") -->
<!-- plot(world_3$geom) -->
<!-- ``` -->
<!-- http://bl.ocks.org/vlandham/raw/9216751/ -->

### Geometry unions and aggregation

Spatial aggregation can also be done in the **tidyverse**, using **dplyr** functions as follows:


```r
group_by(us_states, REGION) %>%
  summarize(sum(pop = total_pop_15, na.rm = TRUE))
```

For attribute data aggregation the grouping variable is another variable, typically one with few unique values relative to the number of rows (see section \@ref(vector-attribute-aggregation)).
What we did not cover in that section was that attribute data aggregation dissolves the geometries of touching polygons.
The `REGION` variable in the `us_states` dataset is a good example:
there are 49 states (excluding Hawaii and Alaska) which can be aggregated into four regions.
This is demonstrated in the code chunk below, the results of which are illustrated in Figure \@ref(fig:us-regions):


```r
regions = aggregate(x = us_states[, "total_pop_15"], by = list(us_states$REGION),
                    FUN = sum, na.rm = TRUE)
```
<!--
show also tidyverse way, so what you are doing is basically a spatial join and a subsequent aggregation without a grouping variable. Didactically, it might be better to present a grouping variable.
-->



<div class="figure" style="text-align: center">
<img src="figures/us-regions-1.png" alt="Spatial aggregation on contiguous polygons, illustrated by aggregating the population of US states into regions, with population represented by color. Note the operation automatically dissolves boundaries between states." width="100%" />
<p class="caption">(\#fig:us-regions)Spatial aggregation on contiguous polygons, illustrated by aggregating the population of US states into regions, with population represented by color. Note the operation automatically dissolves boundaries between states.</p>
</div>

The equivalent result can be achieved using **tidyverse** functions as follows (result not shown):


```r
regions2 = us_states %>% 
  group_by(REGION) %>%
  summarize(sum(pop = total_pop_15, na.rm = TRUE))
```

### Clipping 

Spatial clipping is a form of spatial subsetting that involves changes to the `geometry` columns of at least some of the affected features.

Clipping can only apply to features more complex than points: 
lines, polygons and their 'multi' equivalents.
To illustrate the concept we will start with a simple example:
two overlapping circles with a center point one unit away from each other and radius of one:


```r
b = st_sfc(st_point(c(0, 1)), st_point(c(1, 1))) # create 2 points
b = st_buffer(b, dist = 1) # convert points to circles
l = c("x", "y")
plot(b)
text(x = c(-0.5, 1.5), y = 1, labels = l) # add text
```

<div class="figure" style="text-align: center">
<img src="figures/points-1.png" alt="Overlapping circles." width="576" />
<p class="caption">(\#fig:points)Overlapping circles.</p>
</div>

Imagine you want to select not one circle or the other, but the space covered by both `x` *and* `y`.
This can be done using the function `st_intersection()`, illustrated using objects named `x` and `y` which represent the left and right-hand circles:


```r
x = b[1]
y = b[2]
x_and_y = st_intersection(x, y)
plot(b)
plot(x_and_y, col = "lightgrey", add = TRUE) # color intersecting area
```

<img src="figures/unnamed-chunk-23-1.png" width="576" style="display: block; margin: auto;" />

The subsequent code chunk demonstrate how this works for all combinations of the 'Venn' diagram representing `x` and `y`, inspired by [Figure 5.1](http://r4ds.had.co.nz/transform.html#logical-operators) of the book R for Data Science [@grolemund_r_2016].
<!-- Todo: reference r4ds -->

<div class="figure" style="text-align: center">
<img src="figures/venn-clip-1.png" alt="Spatial equivalents of logical operators." width="576" />
<p class="caption">(\#fig:venn-clip)Spatial equivalents of logical operators.</p>
</div>

To illustrate the relationship between subsetting and clipping spatial data, we will subset points that cover the bounding box of the circles `x` and `y` in Figure \@ref(fig:venn-clip).
Some points will be inside just one circle, some will be inside both and some will be inside neither.

There are two different ways to subset points that fit into combinations of the circles: via clipping and logical operators.
But first we must generate some points.
We will use the *simple random* sampling strategy to sample from a box representing the extent of `x` and `y`.
To generate this points will use a function not yet covered in this book, `st_sample()`.
Next we will generate the situation plotted in Figure \@ref(fig:venn-subset):


```r
bb = st_bbox(st_union(x, y))
pmat = matrix(c(bb[c(1, 2, 3, 2, 3, 4, 1, 4, 1, 2)]), ncol = 2, byrow = TRUE)
box = st_polygon(list(pmat))
set.seed(2017)
p = st_sample(x = box, size = 10)
plot(box)
plot(x, add = TRUE)
plot(y, add = TRUE)
plot(p, add = TRUE)
text(x = c(-0.5, 1.5), y = 1, labels = l)
```

<div class="figure" style="text-align: center">
<img src="figures/venn-subset-1.png" alt="Randomly distributed points within the bounding box enclosing circles x and y." width="576" />
<p class="caption">(\#fig:venn-subset)Randomly distributed points within the bounding box enclosing circles x and y.</p>
</div>



### Centroids
<!-- st_point_on_surface -->
<!-- st_centroid -->
<!-- st_polygonize -->


```r
nz_centroid = st_centroid(nz)
```


```r
nz_pos = st_point_on_surface(nz)
```

<img src="figures/unnamed-chunk-27-1.png" width="576" style="display: block; margin: auto;" />

### Buffers

### Affine transformations

### Type transformation

Geometry casting is powerful operation which enable transformation of the geometry type <!--while the fundamental data remains unchanged-->.
<!-- This could be done for one of two purposes, either simplification  -->
<!-- (also called type transformation) is  -->

<!-- a/ points -> lines -> polygons  -->

<!-- b/ multi ->  single -->

<!-- or Geometry cast -->
<!-- Changing the geometry type while the fundamental data remains unchanged ('casting') -->
<!-- - st_cast -->
<!-- two groups of examples: -->
<!-- - top down (MULTIPOLYGON -> the rest) -->
<!-- - bottom up (POINT -> the rest) -->
<!-- and in the same time, two (?) groups of purposes: -->
<!-- - split/join geometries (e.g one mutlipoint -> many points) -->
<!-- - transform type (e.g one mutlipoint -> one line -> one polygon) -->


```r
nz_points = st_cast(nz, "MULTIPOINT")
```

<img src="figures/unnamed-chunk-30-1.png" width="576" style="display: block; margin: auto;" />

<!-- ### Class conversion -->
<!-- placeholder for: -->
<!-- sf -> sp -->
<!-- sp -> sf -->
<!-- stars; https://github.com/r-spatial/stars/blob/master/vignettes/blog1.Rmd -->

### Simplification
<!-- - simplifications -->
<!-- st_simplify -->
<!-- line example -->
<!-- rmapshaper -->
<!-- polygon example -->

### Rasterization
<!-- - vector to raster -->

## Geometric operations on raster data

### Reprojecting

The basic concepts of CRS apply to both vector and raster data model.
However, there are important differences in reprojection of vectors and rasters.
Transformation of CRS in vector data changes coordinates of each vertex. 
This do not apply to raster data.
Rasters are are composed of rectangular cells of the same size (expressed by map units, such as degrees or meters).
To preserve this property, it is impossible to transform coordinates of cells separately.
This entails that a new raster could have a different number of columns and rows, and therefore different number of cells that the original one.
Therefore, values of these new cells need to be estimated after a geometric operation is completed.
The `projectRaster()` function's role is to reproject `Raster*` objects into a new object with another coordinate reference system. 
Compared to `st_tranform()`, `projectRaster()` only accepts the `proj4string` definitions.

\BeginKnitrBlock{rmdnote}<div class="rmdnote">It is possible to use a EPSG code in a `proj4string` definition with `"+init=epsg:MY_NUMBER"`.
For example, one can use the `"+init=epsg:4326"` definition to set CRS to WGS84 (EPSG code of 4326).
The PROJ.4 library automaticaly adds the rest of parameters and converts it into `"+init=epsg:4326 +proj=longlat +datum=WGS84 +no_defs +ellps=WGS84 +towgs84=0,0,0"`,</div>\EndKnitrBlock{rmdnote}

Let's take a look at two examples of raster transformation - using categorical and continuous data.
Land cover data are usually represented by categorical maps.
The `nlcd2011.tif` file provides information for a small area in Utah, USA obtained from [National Land Cover Database 2011](https://www.mrlc.gov/nlcd2011.php) in the NAD83 / UTM zone 12N CRS.


```r
cat_raster = raster(system.file("raster/nlcd2011.tif", package = "spDataLarge"))
cat_raster
#> class       : RasterLayer 
#> dimensions  : 1359, 1073, 1458207  (nrow, ncol, ncell)
#> resolution  : 31.5, 31.5  (x, y)
#> extent      : 301903, 335735, 4111244, 4154086  (xmin, xmax, ymin, ymax)
#> coord. ref. : +proj=utm +zone=12 +ellps=GRS80 +towgs84=0,0,0,0,0,0,0 +units=m +no_defs 
#> data source : /home/travis/R/Library/spDataLarge/raster/nlcd2011.tif 
#> names       : nlcd2011 
#> values      : 11, 95  (min, max)
```

In this region, 14 land cover classes were distinguished^[Full list of NLCD2011 land cover classes can be found at https://www.mrlc.gov/nlcd11_leg.php]:


```r
unique(cat_raster)
#>  [1] 11 21 22 23 31 41 42 43 52 71 81 82 90 95
```

When reprojecting categorical raster, we need to ensure that our new estimated values would still have values of our original classes.
This could be done using the nearest neighbor method (`ngb`).
In this method, value of the output cell is calculated based on the nearest cell center of the input raster.

For example, we want to change the CRS to WGS 84.  
It can be desired when we want to visualize a raster data on top of a web basemaps, such as the Google or OpenStreetMap map tiles.
The first step is to obtain the proj4 definition of this CRS, which can be done using the [http://spatialreference.org](http://spatialreference.org/ref/epsg/wgs-84/) webpage. 
The second and last step is to define the reprojection method in the `projectRaster()` function, which in case of categorical data is the nearest neighbor method (`ngb`):


```r
wgs84 = "+proj=longlat +ellps=WGS84 +datum=WGS84 +no_defs"
cat_raster_wgs84 = projectRaster(cat_raster, crs = wgs84, method = "ngb")
cat_raster_wgs84
#> class       : RasterLayer 
#> dimensions  : 1394, 1111, 1548734  (nrow, ncol, ncell)
#> resolution  : 0.000356, 0.000284  (x, y)
#> extent      : -113, -113, 37.1, 37.5  (xmin, xmax, ymin, ymax)
#> coord. ref. : +proj=longlat +ellps=WGS84 +datum=WGS84 +no_defs +towgs84=0,0,0 
#> data source : in memory
#> names       : nlcd2011 
#> values      : 11, 95  (min, max)
```

Many properties of the new object differs from the previous one, which include the number of columns and rows (and therefore number of cells), resolution (transformed from meters into degrees), and extent.
In the same time, it keeps the same land cover classes - `unique(cat_raster_wgs84)`.
<!-- freq(cat_raster_wgs84) -->
<!-- freq(cat_raster) -->

This process of reprojection is almost identical for continuous data.
The `srtm.tif` file contains digital elevation model for the same area in Utah from [the Shuttle Radar Topography Mission (SRTM)](https://www2.jpl.nasa.gov/srtm/).
Each value in this raster represents elevation measured in meters.


```r
con_raster = raster(system.file("raster/srtm.tif", package = "spDataLarge"))
con_raster
#> class       : RasterLayer 
#> dimensions  : 457, 465, 212505  (nrow, ncol, ncell)
#> resolution  : 0.000833, 0.000833  (x, y)
#> extent      : -113, -113, 37.1, 37.5  (xmin, xmax, ymin, ymax)
#> coord. ref. : +proj=longlat +datum=WGS84 +no_defs +ellps=WGS84 +towgs84=0,0,0 
#> data source : /home/travis/R/Library/spDataLarge/raster/srtm.tif 
#> names       : srtm 
#> values      : 1024, 2892  (min, max)
```

The nearest neighbor method should not be used for continuous raster data, as we want to preserve gradual changes in values.
Alternatively, continuous data could be reprojected in the **raster** package using the bilinear method. 
In this technique, value of the output cell is calculated based on four nearest cells in the original raster. 
The new value is a weighted average of values from these four cells, adjusted for their distance from the center of the output cell. 
This dataset has geographic CRS and we want to transform it into projected CRS.

\BeginKnitrBlock{rmdnote}<div class="rmdnote">All the grid cells in equal-area projections have the same size.
Therefore, these projections are recommended when performing many raster operations, such as distance calculations.</div>\EndKnitrBlock{rmdnote}

In the fist step we need to obtain the proj4 definition of the existing projected CRS appropriate for this area or create a new one using the [Projection Wizard](http://projectionwizard.org/) online tool [@savric_projection_2016].
For this example, we used the Oblique Lambert azimuthal equal-area projection.
The second step is to define the `bilinear` reprojection method:


```r
equalarea = "+proj=laea +lat_0=37.32 +lon_0=-113.04"
con_raster_ea = projectRaster(con_raster, crs = equalarea, method = "bilinear")
con_raster_ea
#> class       : RasterLayer 
#> dimensions  : 467, 478, 223226  (nrow, ncol, ncell)
#> resolution  : 73.9, 92.5  (x, y)
#> extent      : -18178, 17146, -21306, 21892  (xmin, xmax, ymin, ymax)
#> coord. ref. : +proj=laea +lat_0=37.32 +lon_0=-113.04 +ellps=WGS84 
#> data source : in memory
#> names       : srtm 
#> values      : 1027, 2891  (min, max)
```

Reprojection of continuous rasters also changes spatial properties, such as the number of cells, resolution, and extent.
Moreover, it slightly modifies values in the new raster, which can be seen by comparing the outputs of the `summary()` function between `con_raster` and `con_raster_ea`.


```r
summary(con_raster)
summary(con_raster_ea)
```

<!-- why new na? -->

<!-- res option in projectRaster? -->
<!-- note1: in most of the cases reproject vector, not raster-->
<!-- note2: equal area projections are the best for raster calculations -->
<!-- q: should we mentioned gdal_transform? -->

### Raster alignment



When merging or performing map algebra on rasters, their resolution, projection, origin and/or extent has to match.
Otherwise, how should we add the values of one raster with a resolution of 0.2 decimal degrees to a second with a resolution of 1 decimal degree?
The same problem arises when we would like to merge satellite imagery from different sensors with different projections and resolutions.
We can deal with such mismatches by aligning the rasters.

This section uses the `elev` object from \@ref(manipulating-raster-objects).
The `projectRaster()` function reprojects one raster to a desired projection, say from UTM to WGS84.
Equally, map algebra operations require the same extent.
Following code adds one row and two columns to each side of the raster while setting all new values to an elevation of 1000 meters (\@ref(fig:extend-example)).


```r
elev_2 = extend(elev, c(1, 2), value = 1000)
plot(elev_2)
```

<div class="figure" style="text-align: center">
<img src="figures/extend-example-1.png" alt="Original raster extended by 1 one row on each side (top, bottom) and two columns on each side (right, left)." width="576" />
<p class="caption">(\#fig:extend-example)Original raster extended by 1 one row on each side (top, bottom) and two columns on each side (right, left).</p>
</div>

Performing an algebraic operation on two objects with differing extents in R, the **raster** package returns the result for the intersection, and says so in a warning.


```r
elev_3 = elev + elev_2
#> Warning in elev + elev_2: Raster objects have different extents. Result for
#> their intersection is returned
```

However, we can also align the extent of two rasters with the `extend()` command.
Here, we extend the `elev` object to the extend of `elev_2`. 
The newly added rows and column receive the default value of the `value` parameter, i.e., `NA`.


```r
elev_4 = extend(elev, elev_2)
```

The `aggregate()` and `disaggregate()` functions help to change the cell size resolution of a raster.
For instance, let us aggregate `elev` from a resolution of 0.5 to a resolution of 1, that means we aggregate by a factor of 2 (Fig. \@ref(fig:aggregate-example)).
Additionally, the output cell value should correspond to the mean of the input cells (but  one could use other functions as well such as `median()`, `sum()`, etc.):


```r
elev_agg = aggregate(elev, fact = 2, fun = mean)
par(mfrow = c(1, 2))
plot(elev)
plot(elev_agg)
```

<div class="figure" style="text-align: center">
<img src="figures/aggregate-example-1.png" alt="Original raster (left). Aggregated raster (right)." width="576" />
<p class="caption">(\#fig:aggregate-example)Original raster (left). Aggregated raster (right).</p>
</div>

Note that the origin of `elev_agg` has changed, too.


```r
origin(elev)
#> [1] 0 0
origin(elev_agg)
#> [1] 0.5 0.5
```

The origin is the point closest to (0, 0) if you moved towards it in steps of x and y resolution.
If two rasters have different origins, their cells do not overlap completely which would make map algebra impossible.
To change the origin , use `origin()`.^[If the origins of two raster datasets are just marginally apart, it sometimes is sufficient to simply increase the `tolerance` argument  of `raster::rasterOptions()`.]
Looking at figure \@ref(fig:origin-example) reveals the effect of changing the origin.


```r
# plot the aggregated raster
plot(elev_agg)
# change the origin
origin(elev_agg) = c(0, 0)
# plot it again
plot(elev_agg, add = TRUE)
```

<div class="figure" style="text-align: center">
<img src="figures/origin-example-1.png" alt="Plotting rasters with the same values but different origins." width="576" />
<p class="caption">(\#fig:origin-example)Plotting rasters with the same values but different origins.</p>
</div>

The `resample()` command lets you align several raster properties in one go, namely origin, extent and resolution.
Let us resample an extended `elev_agg` to the properties of `elev` again.


```r
# add 2 rows and columns, i.e. change the extent
elev_agg = extend(elev_agg, 2)
elev_disagg = resample(elev_agg, elev)
```

Though our disaggregated `elev_disagg` retrieved back its original resolution, cell size and extent, its values differ. 
However, this is to be expected, disaggregating **cannot** predict values at a finer resolution, it simply uses an interpolation algorithm.
It is important to keep in mind that disaggregating results in a finer resolution, the corresponding values, however, are only as accurate as their lower resolution source.

Finally, if you want to align many (possibly hundreds or thousands of) images stored on disk, you might want to checkout the `gdalUtils::align_rasters()` function.
Nevertheless, you may also use **raster** with very large datasets. 
This is because **raster**:

1. lets you work with raster datasets that are too large to fit into the main memory (RAM) by only processing chunks of it.
2. tries to facilitate parallel processing.
For more information have a look at the help pages of `beginCluster()` and `clusteR()`.
Additionally, check out the *Multi-core functions* section in `vignette("functions", package = "raster")`.

### Aggregation

### Vectorization

## Exercises

<!-- CRS CONVERSION -->
<!-- 1. vector reprojection exercise (e.g. modification of proj4) -->
1. Transform the `world` dataset to the transverse Mercator projection (`"+proj=tmerc"`) and plot the result.
What has changed and why?
Try to transform it back into WGS 84 and plot the new object.
Why the new object differs from the original one?
<!-- https://github.com/r-spatial/sf/issues/509 -->
<!-- ```{r} -->
<!-- world_tmerc = st_transform(world, "+proj=tmerc") -->
<!-- plot(world_tmerc$geom) -->
<!--  world_4326 = st_transform(world_tmerc, 4326) -->
<!-- plot(world_4326$geom) -->
<!-- ``` -->
1. Try to transform the categorical raster (`cat_raster`) into WGS 84 using the bilinear interpolation method. 
What has changed?
How it influences the results?
<!-- ```{r} -->
<!-- wgs84 = "+proj=longlat +ellps=WGS84 +datum=WGS84 +no_defs" -->
<!-- cat_raster_wgs84 = projectRaster(cat_raster, crs = wgs84, method = "bilinear") -->
<!-- cat_raster_wgs84 -->
<!-- ``` -->
1. Try to transform the continuous raster (`cat_raster`) into WGS 84 using the nearest neighbor interpolation method. 
What has changed?
How it influences the results?
<!-- ```{r} -->
<!-- con_raster = raster(system.file("raster/srtm.tif", package="spDataLarge")) -->
<!-- con_raster_wgs84 = projectRaster(con_raster, crs = wgs84, method = "ngb") -->
<!-- con_raster_wgs84 -->
<!-- ``` -->
<!-- GEOMETRY TRANSFORMATION -->

<!--chapter:end:05-transform.Rmd-->


# Geographic data I/O {#read-write}

## Prerequisites {-}

- This chapter requires the packages **tidyverse**, **sf**, **spData** and **raster**. 


```r
library(tidyverse)
library(sf)
library(spData)
library(raster)
```

## Introduction

This chapter is about reading and writing geographic data.
Geographic data *import* is an essential part of geocomputational software because without data real-world applications are impossible.
The skills taught in this book will enable you to *add value* to data meaning that, for others to benefit from the results, data *output* is also vital.
These two processes go hand-in-hand and are referred to as I/O --- short for input/output --- in Computer Science [@gillespie_efficient_2016].
Hence the title of this chapter.

Geographic data I/O is almost always part of a wider process.
It depends on knowing which datasets are *available*, where they can be *found* and how to *retrieve* them, topics covered in section \@ref(retrieving-data).
This section demonstrates how to access open access *geoportals* which collectively contain many terrabytes of data.
There is a wide range of geographic file formats, each of which has pros and cons.
These are described in section \@ref(file-formats).
The process of actually reading and writing such file formats efficiently is not covered until sections \@ref(data-input) and \@ref(data-output) respectively.
The final section (\@ref(visual-outputs)) demonstrates methods for saving visual outputs (maps), in preparation for a subsequent chapter dedicated to visualization.
<!-- Todo: Add reference to vis chapter (RL) -->

## Retrieving open data {#retrieving-data}

Nowadays, a vast amount of spatial data is available on the internet.
Best of all, much of it is freely available.
You just have to know where to look.
While we cannot provide a comprehensive guide to all available geodata, we point to a few of the most important sources.
Various 'geoportals' (web services providing geographic data such as the geospatial datasets in [Data.gov](https://catalog.data.gov/dataset?metadata_type=geospatial)) are a good place to start, providing a wide range of geographic data.
Geoportals are a very useful data source but often only contain data for a specific locations (see the [Wikipedia page on geoportals](https://en.wikipedia.org/wiki/Geoportal) for a list of geoportals covering many areas of the world).

To overcome this limitation some global geoportals have been developed.
The [GEOSS portal](http://www.geoportal.org/), for example, provides global remote sensing data.
Additional geoportals with global coverage and an emphasis on raster data include the [EarthExplorer](https://earthexplorer.usgs.gov/) and the [Copernicus Open Access Hub](https://scihub.copernicus.eu/).
A wealth of European data is available from the [INSPIRE geoportal](http://inspire-geoportal.ec.europa.eu/).

Typically, geoportals provide an interface that lets you query interactively the existing data (spatial and temporal extent, and product).
However, in this book we encourage you to create reproducible workflows.
In many cases data downloads can be scripted via download calls to static URLs or APIs (see the [Sentinel API](https://scihub.copernicus.eu/twiki/do/view/SciHubWebPortal/APIHubDescription) for example), saving time, and enabling others to repeat and update the unglamorous data download process. 

Traditionally, files have been stored on servers.
<!-- that's probably not the best example - replace it with something better -->
<!-- btw naturalearth website has some problems today - the link will probably change in the future -->
You can easily download such files with the `download.file()` command.
For example, to download National Park Service units in the United States, run:


```r
url = file.path("http://www.naturalearthdata.com/http//www.naturalearthdata.com",
                "download/10m/cultural/ne_10m_parks_and_protected_lands.zip")
download.file(url = url,
              destfile = "USA_parks.zip")
unzip(zipfile = "USA_parks.zip")
usa_parks = st_read("ne_10m_parks_and_protected_lands_area.shp")
```

Specific R packages providing an interface to spatial libraries or geoportals are even more user-friendly (Table \@ref(tab:datapackages)).

<!-- add sentinel2 package as soon as it is published on CRAN https://github.com/IVFL-BOKU/sentinel2-->

Table: (\#tab:datapackages)Selected R packages for spatial data retrieval

Package name    Description                                                                                                  
--------------  -------------------------------------------------------------------------------------------------------------
osmdata         Download and import of OpenStreetMap data.                                                                   
raster          The `getData()` function downloads and imports administrative country, SRTM/ASTER elevation, WorldClim data. 
rnaturalearth   Functions to download Natural Earth vector and raster data, including world country borders.                 
rnoaa           An R interface to National Oceanic and Atmospheric Administration (NOAA) climate data.                       
rWBclimate      An access to the World Bank climate data.                                                                    

<!-- https://cdn.rawgit.com/Nowosad/Intro_to_spatial_analysis/05676e29/Intro_to_spatial_analysis.html#39 -->
<!-- Maybe add a section to Data I/O on where and how to retrieve data (with a focus on free data): osmdata (OpenStreetMap; maybe mention TomTom, HERE), Landsat (wrspathrow), Sentinel (mention Python API), AVHRR, RapidEye rgbif, letsR, etc. Of course, point to Transforming science through open data project (https://www.ropensci.org) -->
<!-- https://github.com/ropensci/GSODR -->
<!-- https://github.com/lbusett/MODIStsp -->
<!-- https://github.com/walkerke/tigris -->
<!-- https://github.com/ropensci/hddtools/ -->

For example, you can get the borders of any country with the `ne_countries()` function from the **rnaturalearth** package:

```r
library(rnaturalearth)
usa = ne_countries(country = "United States of America") # United States borders
class(usa)
#> [1] "SpatialPolygonsDataFrame"
#> attr(,"package")
#> [1] "sp"
# you can do the same with raster::getData()
# getData("GADM", country = "USA", level = 0)
```

As a default, **rnaturalearth** returns the output as a `Spatial*` class. 
You can easily convert it to the `sf` class with `st_as_sf()`:


```r
usa_sf = st_as_sf(usa)
```

As a second example, we will download a raster dataset.
The code below downloads a series of rasters that contains global monthly precipitation sums.
The spatial resoultion is ten minutes.
The result is a multilayer object of class `RasterStack`.


```r
library(raster)
worldclim_prec = getData(name = "worldclim", var = "prec", res = 10)
class(worldclim_prec)
#> [1] "RasterStack"
#> attr(,"package")
#> [1] "raster"
```

A third example uses the recently developed package **osmdata** [@R-osmdata] to find parks from the OpenStreetMap (OSM) database.
As illustrated in the code-chunk below, queries begin with the function `opq()` (short for OpenStreetMap query), the first argument of which is bounding box, or text string representing a bounding box (the city of Leeds in this case).
The result is passed to a function for selecting which OSM elements we're interested in (parks in this case), represented by *key-value pairs*, which in turn is passed to the function `osmdata_sf()` which does the work of downloading the data and converting it into a list of `sf` objects (see `vignette('osmdata')` for further details):


```r
library(osmdata)
parks = opq(bbox = "leeds uk") %>% 
  add_osm_feature(key = "leisure", value = "park") %>% 
  osmdata_sf()
```

OpenStreetMap is a vast global database of crowd-sourced data and it is growing by the minute.
Although the quality is not as spatially consistent as many official datasets, OSM data have many advantages: they are globally available free of charge and using crowd-source data can encourage 'citizen science' and contributions back to the digital commons.
Have a look at sections \@ref(location) and \@ref(gis) for further examples of how to use **osmdata** in applied research.

Finally, R packages might contain or just consist of spatial data (e.g., package **spData**).
You can access such data with the `data()` function.
For example, you can get a list of dataset in a package, `data(package = "spData")`.
To attach the dataset to the global environment specify the name of a dataset (`data("cycle_hire", package = "spData")`).
Sometimes, packages come also with the original files.^[Data loaded with `data()` often is a R dataset (`.Rdata` ord `.rda`)].
To load such a file from the package, you need to specify the package name and the relative path to the dataset, for example:


```r
world_raw_filepath = system.file("shapes/world.gpkg", package = "spData")
world_raw = st_read(world_raw_filepath)
#> Reading layer `wrld.gpkg' from data source `/home/travis/R/Library/spData/shapes/world.gpkg' using driver `GPKG'
#> Simple feature collection with 177 features and 10 fields
#> geometry type:  MULTIPOLYGON
#> dimension:      XY
#> bbox:           xmin: -180 ymin: -90 xmax: 180 ymax: 83.64513
#> epsg (SRID):    4326
#> proj4string:    +proj=longlat +datum=WGS84 +no_defs
```

Find more information on getting data using R packages in [section 5.5](https://csgillespie.github.io/efficientR/input-output.html#download) and [section 5.6](https://csgillespie.github.io/efficientR/input-output.html#accessing-data-stored-in-packages) of @gillespie_efficient_2016.

## File formats

Spatial data is usually stored as files or in spatial databases. 
File-based data formats can contain either vector or raster data, while spatial databases could store both.
Historically, GIS file formats were developed by mapping agencies and software companies. <!--examples-->
Exchanging spatial data between different software packages each coming with its own format was troublesome in the beginning.

GDAL^[prounounce "goo-dal", with the double o making a reference to object-orientation] put an end to these troubles by enabling reading and writing many raster and vector data formats.
Subsequently, many open and proprietary GIS software (e.g., GRASS, QGIS, ArcGIS, ENVI) were quick to incorporate it.
<!-- GDAL (it's great - you can read, convert, and very often (though not always) write) -->
<!-- GDAL info "it is possible to have smaller number of supported formats than there are on the GDAL webpage; you may need to recompile..." -->

Another change for spatial data formats came with the foundation of the Open Geospatial Consortium (OGC)^[http://www.opengeospatial.org].
This organization collaborates on the development and implementation of open standards for geospatial content including file formats such as the KML and GeoPackage formats as well as the simple feature standard. 
Developing and maintaining spatial file formats in an open model provides several benefits over the proprietary formats <!-- such as??-->, and eases interoperability.

Nowadays, more than a hundred spatial data formats exist.
<!-- In the same time, they could differ in many ways. -->
<!-- Spatial data could be stored as a single file (e.g. GeoPackage), multiple files (e.g. ESRI Shapefile), or folders (ESRI ArcInfo Coverages). -->
<!-- way of storage (single file, multiple files, folders) -->
Table \@ref(tab:formats) presents some basic information about selected, often used spatial file formats.

<!-- simple features are missing from this table-->

Table: (\#tab:formats)Selected spatial file formats.

Name                Extension              Info                                                                                                                                                                                                                                                                                     Type                Model          
------------------  ---------------------  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------  ------------------  ---------------
ESRI Shapefile      .shp (the main file)   One of the most popular vector file format. Consists of at least three files. The main files size cannot exceed 2 GB. It lacks support for mixed type. Columns names are limited to 10 characters, and number of columns are limited at 255. It has poor support for Unicode standard.   Vector              Partially open 
GeoJSON             .geojson               Extends the JSON exchange format by including a subset of the simple feature representation.                                                                                                                                                                                             Vector              Open           
KML                 .kml                   XML-based format for spatial visualization, developed for use with Google Earth. Zipped KML file forms the KMZ format.                                                                                                                                                                   Vector              Open           
GPX                 .gpx                   XML schema created for exchange of GPS data.                                                                                                                                                                                                                                             Vector              Open           
GeoTIFF             .tiff                  GeoTIFF is one of the most popular raster formats. Its structure is similar to the regular `.tif` format, however, additionally stores  the raster header.                                                                                                                               Raster              Open           
Arc ASCII           .asc                   Text format where the first six lines represent the raster header, followed by the raster cell values arranged in rows and columns.                                                                                                                                                      Raster              Open           
R-raster            .gri, .grd             Native raster format of the R-package raster.                                                                                                                                                                                                                                            Raster              Open           
SQLite/SpatiaLite   .sqlite                SQLite is a standalone, relational database management system. It is used as a default database driver in GRASS GIS 7. SpatiaLite is the spatial extension of SQLite providing support for simple features.                                                                              Vector and raster   Open           
ESRI FileGDB        .gdb                   Collection of spatial and nonspatial objects created in the ArcGIS software. It allows to store multiple feature classes and enables use of topological definitions. Limited access to this format is provided by GDAL with the use of the OpenFileGDB and FileGDB drivers.              Vector and raster   Proprietary    
GeoPackage          .gpkg                  Lightweight database container based on SQLite allowing an easy and platform-independent exchange of geodata                                                                                                                                                                             Vector and raster   Open           

<!-- http://switchfromshapefile.org/ -->
<!-- 3. JPEG - (possibly mention SAGA's sdat, Erdas Imagine) -->
<!-- 1. SQLite/SpatialLite + mention GRASS (uses SQLite) -->
<!-- 3. WKT/WKB for transfering and storing geometry data on databases. PostGIS (has even its own raster WKT (https://trac.osgeo.org/postgis/wiki/WKTRasterTutorial01); WKT also supported by Spatiallite, Oracle, MySQL, etc. (https://en.wikipedia.org/wiki/Well-known_text#RDBMS_Engines_that_provide_support) -->
<!-- 4. ESRI geodatabase, Oracle spatial database (mention + gdal support?) -->

## Data Input (I) {#data-input}

Executing commands such as `sf::st_read()` (the main function we use for loading vector data) or `raster::raster()` (the main function used for loading raster data) silently sets off a chain of events that reads data from files.
<!-- transition is unclear, not sure what you would like to say -->
Moreover, there are many R packages containing a wide range of spatial data or providing simple access to different data sources.
All of them load the data into R or, more precisely, assign objects to your workspace, stored in RAM accessible from the `.GlobalEnv`^[See http://adv-r.had.co.nz/Environments.html for more information on the environment] of your current R session.

### Vector data

Spatial vector data comes in a wide variety of file formats, most of which can be read-in via the **sf** function `st_read()`.
Behind the scenes this calls GDAL.
To find out which data formats **sf** supports, run `st_drivers()`. 
Here, we show only the first five drivers (see Table \@ref(tab:drivers)):


```r
sf_drivers = st_drivers()
head(sf_drivers, n = 5)
```


Table: (\#tab:drivers)Sample of available drivers for reading/writing vector data (it could vary between different GDAL versions).

name             long_name                       write   copy    is_raster   is_vector 
---------------  ------------------------------  ------  ------  ----------  ----------
ESRI Shapefile   ESRI Shapefile                  TRUE    FALSE   FALSE       TRUE      
GPX              GPX                             TRUE    FALSE   FALSE       TRUE      
KML              Keyhole Markup Language (KML)   TRUE    FALSE   FALSE       TRUE      
GeoJSON          GeoJSON                         TRUE    FALSE   FALSE       TRUE      
GPKG             GeoPackage                      TRUE    TRUE    TRUE        TRUE      

<!-- One of the major advantages of **sf** is that it is fast. -->
<!-- reference to the vignette -->
The first argument of `st_read()` is `dsn`, which should be a text string or an object containing a single text string.
The content of a text string could vary between different drivers.
In most cases, as with the ESRI Shapefile (`.shp`) or the `GeoPackage` format (`.gpkg`), the `dsn` would be a file name.
`st_read()` guesses the driver based on the file extension, as illustrated for a `.gpkg` file below:


```r
vector_filepath = system.file("shapes/world.gpkg", package = "spData")
world = st_read(vector_filepath)
#> Reading layer `wrld.gpkg' from data source `/home/travis/R/Library/spData/shapes/world.gpkg' using driver `GPKG'
#> Simple feature collection with 177 features and 10 fields
#> geometry type:  MULTIPOLYGON
#> dimension:      XY
#> bbox:           xmin: -180 ymin: -90 xmax: 180 ymax: 83.64513
#> epsg (SRID):    4326
#> proj4string:    +proj=longlat +datum=WGS84 +no_defs
```

For some drivers, `dsn` could be provided as a folder name, access credentials for a database, or a GeoJSON string representation (see the examples of the `st_read()` help page for more details).

Some vector driver formats can store multiple data layers.
By default, `st_read` automatically reads the first layer of the file specified in `dsn`, however, using the `layer` argument you can specify any other layer.

Naturally, some options are specific to certain drivers[^1]. 
For example, think of coordinates stored in a spreadsheet format (`.csv`).
To read in such files as spatial objects, we naturally have to specify the names of the columns (`X` and `Y` in our example below) representing the coordinates.
We can do this with the help of the `options` parameter.
To find out about possible options, please refer to the 'Open Options' section of the corresponding GDAL driver description.
For the comma-separated value (csv) format, visit http://www.gdal.org/drv_csv.html.


```r
cycle_hire_txt = system.file("misc/cycle_hire_xy.csv", package = "spData")
cycle_hire_xy = st_read(cycle_hire_txt, options = c("X_POSSIBLE_NAMES=X",
                                                    "Y_POSSIBLE_NAMES=Y"))
```

Instead of columns describing xy-coordinates, a single column can also contain the geometry information.
Well-known text (WKT), well-known binary (WKB), and the GeoJSON formats are examples for this.
For instance, the `world_wkt.csv` file has a column named `WKT` representing polygons of the world's countries.
We will again use the `options` parameter to indicate this.
Here, we will use `read_sf()` which does exactly the same as `st_read()` except it does not print the driver name to the console and stores strings as characters instead of factors.


```r
world_txt = system.file("misc/world_wkt.csv", package = "spData")
world_wkt = read_sf(world_txt, options = "GEOM_POSSIBLE_NAMES=WKT")
# the same as
world_wkt = st_read(world_txt, options = "GEOM_POSSIBLE_NAMES=WKT", 
                    quiet = TRUE, stringsAsFactors = FALSE)
```

\BeginKnitrBlock{rmdnote}<div class="rmdnote">Not all of the supported vector file formats store information about their coordinate reference system.
In these situations, it is possible to add the missing information using the `st_set_crs()` function.
Please refer also to section \@ref(crs-intro) for more information.</div>\EndKnitrBlock{rmdnote}

As a final example, we will show how `st_read()` also reads KML files.
A KML file stores geographic information in XML format - a data format for the creation of web pages and the transfer of data in an application-independent way [@nolan_xml_2014].
Here, we access a KML file from the web.
This file contains more than one layer.
`st_layers()` lists all available layers.
We choose the first layer `Placemarks` and say so with the help of the `layer` parameter in `read_sf()`.


```r
url = "https://developers.google.com/kml/documentation/KML_Samples.kml"
st_layers(url)
#> Driver: LIBKML 
#> Available layers:
#>               layer_name geometry_type features fields
#> 1             Placemarks                      3     11
#> 2      Styles and Markup                      1     11
#> 3       Highlighted Icon                      1     11
#> 4        Ground Overlays                      1     11
#> 5        Screen Overlays                      0     11
#> 6                  Paths                      6     11
#> 7               Polygons                      0     11
#> 8          Google Campus                      4     11
#> 9       Extruded Polygon                      1     11
#> 10 Absolute and Relative                      4     11
kml = read_sf(url, layer = "Placemarks")
```

### Raster data

Similar to vector data, raster data comes in many file formats with some of them supporting even multilayer files.
**raster**'s `raster()` command reads in a single layer.


```r
raster_filepath = system.file("raster/srtm.tif", package = "spDataLarge")
single_layer = raster(raster_filepath)
```

In case you want to read in a single band from a multilayer file use the `band` parameter to indicate a specific layer.


```r
multilayer_filepath = system.file("raster/landsat.tif", package = "spDataLarge")
band3 = raster(multilayer_filepath, band = 3)
```

If you want to read in all bands, use `brick()` or `stack()`.


```r

multilayer_brick = brick(multilayer_filepath)
multilayer_stack = stack(multilayer_filepath)
```

Please refer to section \@ref(raster-classes) for information on the difference between raster stacks and bricks.

<!-- ### Databases -->
<!-- postgis input example -->

## Data output (O) {#data-output}

<!--maybe we can come up with an intro which is a bit more compelling-->
The ability of writing spatial data could be used for conversion between different formats and for saving newly created objects.
Depending on the data type (vector or raster), object class (e.g `multipoint` or `RasterLayer`), and type and amount of stored information (e.g. object size, range of values) - it is important to know how to store spatial files in the most efficient way.
The next two section will show how to do that.

<!-- should we add a note about recommended way to decide on a file name, for example "don't use spaces in the name", "create descriptive names" -->

### Vector data



The counterpart of `st_read()` is `st_write()`.
It allows to write **sf** objects to a wide range of geographic vector file formats, including the most common ones such as `.geojson`, `.shp` and `.gpkg`.
Based on the file name, `st_write()` decides automatically which driver to use. 
How fast the writing process is depends also on the driver.
<!-- ref to the vignette -->


```r
st_write(obj = world, dsn = "world.gpkg")
#> Writing layer `world' to data source `world.gpkg' using driver `GPKG'
#> features:       177
#> fields:         10
#> geometry type:  Multi Polygon
```

**Note**: if you try to write to the same data source again, the function will fail:


```r
st_write(obj = world, dsn = "world.gpkg")
#> Updating layer `world' to data source `/home/travis/build/Robinlovelace/geocompr/world.gpkg' using driver `GPKG'
#> Warning in CPL_write_ogr(obj, dsn, layer, driver, as.character(dataset_options), : GDAL Error 1: Layer world already exists, CreateLayer failed.
#> Use the layer creation option OVERWRITE=YES to replace it.
#> Creating layer world failed.
#> Error in CPL_write_ogr(obj, dsn, layer, driver, as.character(dataset_options), : Layer creation failed.
```

<!-- ##   GDAL Error 1: Layer world.gpkg already exists, CreateLayer failed. -->
<!-- ## Use the layer creation option OVERWRITE=YES to replace it. -->

The error message provides some information as to why the function failed.
The `GDAL Error 1` statement makes clear that the failure occurred at the GDAL level.
Additionally, the suggestion to use `OVERWRITE=YES` provides a clue how to fix the problem.
However, this is not a `st_write()` argument, it is a GDAL option.
Luckily, `st_write` provides a `layer_options` argument through which we can pass driver-dependent options:


```r
st_write(obj = world, dsn = "world.gpkg", layer_options = "OVERWRITE=YES")
```

Another solution is to use the `st_write()` argument `delete_layer`. Setting it to `TRUE` deletes already existing layers in the data source before the function attempts to write (note there is also a `delete_dsn` argument):


```r
st_write(obj = world, dsn = "world.gpkg", delete_layer = TRUE)
```

You can achieve the same with `write_sf()` since it is equivalent to (technically an *alias* for) `st_write()`, except that its defaults for `delete_layer` and `quiet` is `TRUE`.


```r
write_sf(obj = world, dsn = "world.gpkg")
```

<!-- how about saving multilayer gpkg? -->
The `layer_options` argument could be also used for many different purposes.
One of them is to write spatial data to a text file.
This can be done by specifying `GEOMETRY` inside of `layer_options`. 
It could be either `AS_XY` for simple point datasets (it creates two new columns for coordinates) or `AS_WKT` for more complex spatial data (one new column is created which contains the well-known-text representation of spatial objects).


```r
st_write(cycle_hire_xy, "cycle_hire_xy.csv", layer_options = "GEOMETRY=AS_XY")
st_write(world_wkt, "world_wkt.csv", layer_options = "GEOMETRY=AS_WKT")
```

### Raster data

The `writeRaster()` function saves `Raster*` objects to files on disk. 
The function expects input regarding output datatype, file format, but also accepts GDAL options specific to a selected file format (see `?writeRaster` for more details).

<!-- datatypes -->
The **raster** package offers nine datatypes when saving a raster: LOG1S, INT1S, INT1U, INT2S, INT2U, INT4S, INT4U, FLT4S, and FLT8S^[Using INT4U is not recommended as R does not support 32-bit unsigned integers.<!--recheck this info-->].
The datatype determines the bit representation of the raster object written to disk (\@ref(tab:datatypes)).
Which datatype to use depends on the range of the values of your raster object.
The more values a datatype can represent, the larger the file will get on disk.
Commonly, one would use LOG1S for bitmap (binary) rasters.
Unsigned integers (INT1U, INT2U, INT4U) are suitable for categorical data, while float numbers (FLT4S and FLTS8S) usually represent continuous data.
`writeRaster()` uses FLT4S as the default.
While this works in most cases, the size of the output file will be unnecessarly large if you save binary or categorical data.
Therefore, we would recommend to use the datatype that needs the least storing space but is still able to represent all values (check the range of values with the `summary()` function).


Table: (\#tab:datatypes)Datatypes supported by the raster package

Datatype   Minimum value    Maximum value 
---------  ---------------  --------------
LOG1S      FALSE (0)        TRUE (1)      
INT1S      -127             127           
INT1U      0                255           
INT2S      -32,767          32,767        
INT2U      0                65,534        
INT4S      -2,147,483,647   2,147,483,647 
INT4U      0                4,294,967,296 
FLT4S      -3.4e+38         3.4e+38       
FLT8S      -1.7e+308        1.7e+308      

The file extension determines the output file when saving a `Raster*` object to disk.
For example, the `.tif` extension will create a GeoTIFF file:


```r
writeRaster(x = single_layer,
            filename = "my_raster.tif",
            datatype = "INT2U")
```

The `raster` file format (native to the `raster` package) is used when a file extension is invalid or missing. 
Some raster file formats come with additional options.
You can use them with the `options` parameter[^2].
For example, GeoTIFF allows to compress the output raster with the `COMPRESS` option^[Find out about GeoTIFF options under http://www.gdal.org/frmt_gtiff.html.]:


```r
writeRaster(x = single_layer,
            filename = "my_raster.tif",
            datatype = "INT2U",
            options = c("COMPRESS=DEFLATE"),
            overwrite = TRUE)
```

Note that `writeFormats()` returns a list with all supported file formats on your computer.

<!-- ### Databases -->
<!-- postgis output example -->

## Visual outputs

R supports many different static and interactive graphics formats.
The most general method to save a static plot is to open a graphic device, create a plot, and close it, for example:


```r
png(filename = "lifeExp.png", width = 500, height = 350)
plot(world["lifeExp"])
dev.off()
```

Other available graphic devices include `pdf()`, `bmp()`, `jpeg()`, `png()`, and `tiff()`. 
You can specify several properties of the output plot, including width, height and resolution.

Additionally, several graphic packages provide its own function to save a graphical output.
For example, the **tmap** package has the `save_tmap()` function.
You can save a `tmap` object to different graphic formats by specifying the object name and a file path to a new graphic file.


```r
library(tmap)
tmap_obj = tm_shape(world) +
  tm_polygons(col = "lifeExp")
save_tmap(tm  = tmap_obj, filename = "lifeExp_tmap.png")
```

<!-- Note about that the `plot` function do not create an object -->
<!-- ```{r} -->
<!-- a = plot(world["lifeExp"]) -->
<!-- ``` -->

On the other hand, on can save interactive maps created in the `mapview` package as an HTML file or image using the `mapshot()` function:

<!-- example doesn't work, problem with colors I guess -->

```r
library(mapview)
mapview_obj = mapview(world, zcol = "lifeExp", legend = TRUE)
mapshot(mapview_obj, file = "my_interactive_map.html")
```

## Exercises

1. List and describe three types of vector, raster, and geodatabase formats.

1. Name at least two differences between `read_sf()` and the more well-known function `st_read()`.

1. Read the `cycle_hire_xy.csv` file from the **spData** package (Hint: it is located in the `misc\` folder).
What is a geometry type of the loaded object? 

1. Download the borders of Germany using **rnaturalearth**, and create a new object called `germany_borders`.
Write this new object to a file of the GeoPackage format.

1. Download the global monthly minimum temperature with a spatial resolution of five minutes using the **raster** package.
Extract the June values, and save them to a file named `tmin_june.tif` file (Hint: use `raster::subset()`).

1. Create a static map of Germany's borders, and save it to a PNG file.

1. Create an interactive map using data from the `cycle_hire_xy.csv` file. 
Export this map to a file called `cycle_hire.html`.

[^1]: A list of supported vector formats and theirs options can be found at http://www.gdal.org/ogr_formats.html.

[^2]: Full list of supported raster formats with theirs options can be found at http://www.gdal.org/formats_list.html

<!--chapter:end:06-read-write-plot.Rmd-->


# (PART) Basic applications {-}

# Location analysis {#location}

## Prerequisites {-}

- This chapter requires following packages: 


```r
library(classInt)
library(ggmap)
library(osmdata)
library(raster)
library(sf)
library(sp)
library(tidyverse)
```

- Required data will be downloaded in due course.

## Introduction

This chapter demonstrates how the skills learned in the previous chapters can be applied to location analysis.
Geomarketing (also called location analysis) is a broad field of research and commercial application, the aim of which is to decide the optimal location for new services.
A standard example is where to locate a new shop: there are typically hundreds of possible locations in a city and location analysis can be used to decide where the shop will attract most visitors and, ultimately, make most profit.
There are also many non-commercial applications that can use the technique for public benefit.
A good example is where to locate new health services [@tomintz_geography_2008].

Geomarketing is focused on people and where they are likely to spend their time and other resources.
However, it has several links with ecology: animals and plants have needs which can be best met in optimal locations based on variables that change over space (called gradients in the ecological literature --- see e.g., @muenchow_review_2017<!--and chapter xx-->).
<!-- add reference!! -->
Polar bears, for example, prefer northern latitudes where temperatures are lower and food (seals and sea lions) is plentiful.
Similarly, humans tend to congregate certain places, creating economic niches (and high land prices) analogous to the ecological niche of the Arctic.
The main task of geomarketing is to find out where such 'optimal locations' are for specific services, based on available data.
Typical research questions in geomarketing include:

- Where are the service users (or clients), specific target groups and competitors?
- How many people can easily reach my stores?
- Do existing services over or under-exploit the market potential?
- How big is my market share and turnovers, and are spatial differences exist?

To demonstrate how geocomputation can answer these questions, the next section creates a scenario where geomarketing is vital to make informed real-world decisions.

## Case study

Imagine your are launching a cycling company and would like to open shops across urban areas of Germany.
Imagine further that a survey you conducted indicates following target group: males between 20-40 years old who live alone or with just one person (single households, not families).
Additionally, you are in the lucky position to have sufficient capital to open a number of shops.
But where should they be placed?
Geomarketing consultancies have been developed to help people answer such questions, and they would happily charge high rates for their expertise.
<!--It is testament to the rate of technological development that these questions can now be answered by informed citizens using free and open source software.-->

The here presented analysis will demonstrate a number of geocomputational techniques learned during the first chapters of the book.
Additionally, this chapter will illustrate common steps in geomarketing to find suitable locations for a specific shop type (here: cycle stores).
The analysis includes following steps:

- The retrieval of socio-demographic data by downloading gridded German census data (section \@ref(create-census-rasters)).
- The identification of areas of high population density (metropolitan areas; section \@ref(define-metropolitan-areas)).
- The download of detailed geographic data (OSM data) for these areas (section \@ref(points-of-interest)).
- Creating input rasters comparable by means of reclassification, and using map algebra to compute a final score where higher scores indicate more favorable locations (section \@ref(identifying-suitable-locations)).

Note that although we have applied these steps to a specific case study, they could be generalized to many scenarios of store location or public service provision.

### Create census rasters

The German government provides a csv-file containing gridded census data of 2011 for Germany.
One can either download a 1 km or a 100 m resolution.
Here, we download the 1 km data, unzip it and read it into R.


```r
url = paste0("https://www.zensus2011.de/SharedDocs/Downloads/DE/", 
             "Pressemitteilung/DemografischeGrunddaten/csv_Zensusatlas_", 
             "klassierte_Werte_1km_Gitter.zip?__blob=publicationFile&v=8")
download.file(url = url, destfile = file.path(tempdir(), "census.zip"),
              method = "auto", mode = "wb")
# list the file names
nms = unzip(file.path(tempdir(), "census.zip"), list = TRUE)
# unzip only the csv file
base_name = grep(".csv$", nms$Name, value = TRUE)
unzip(file.path(tempdir(), "census.zip"), files = base_name, exdir = tempdir())
# read in the csv file
census = readr::read_csv2(file.path(tempdir(), base_name))
```





Next we select the variables we need: x and y coordinates, the number of inhabitants (population), mean age, proportion of women and the household size (Table \@ref(tab:census-desc)). 

<table>
<caption>(\#tab:census-desc)Excerpt from the data description 'Datensatzbeschreibung_klassierte_Werte_1km-Gitter.xlsx' located in the downloaded file census.zip describing the classes of the retained variables. The classes -1 and -9 refer to uninhabited areas or areas which have to be kept secret, for example due to anonymization reasons.</caption>
 <thead>
  <tr>
   <th style="text-align:center;"> class </th>
   <th style="text-align:center;"> population\
(number of people) </th>
   <th style="text-align:center;"> women\
(%) </th>
   <th style="text-align:center;"> mean age\
(years) </th>
   <th style="text-align:center;"> household size\
(number of people) </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:center;"> 1 </td>
   <td style="text-align:center;"> 3-250 </td>
   <td style="text-align:center;"> 0-40 </td>
   <td style="text-align:center;"> 0-40 </td>
   <td style="text-align:center;"> 1-2 </td>
  </tr>
  <tr>
   <td style="text-align:center;"> 2 </td>
   <td style="text-align:center;"> 250-500 </td>
   <td style="text-align:center;"> 40-47 </td>
   <td style="text-align:center;"> 40-42 </td>
   <td style="text-align:center;"> 2-2.5 </td>
  </tr>
  <tr>
   <td style="text-align:center;"> 3 </td>
   <td style="text-align:center;"> 500-2000 </td>
   <td style="text-align:center;"> 47-53 </td>
   <td style="text-align:center;"> 42-44 </td>
   <td style="text-align:center;"> 2.5-3 </td>
  </tr>
  <tr>
   <td style="text-align:center;"> 4 </td>
   <td style="text-align:center;"> 2000-4000 </td>
   <td style="text-align:center;"> 53-60 </td>
   <td style="text-align:center;"> 44-47 </td>
   <td style="text-align:center;"> 3-3.5 </td>
  </tr>
  <tr>
   <td style="text-align:center;"> 5 </td>
   <td style="text-align:center;"> 4000-8000 </td>
   <td style="text-align:center;"> &gt;60 </td>
   <td style="text-align:center;"> &gt;47 </td>
   <td style="text-align:center;"> &gt;3.5 </td>
  </tr>
  <tr>
   <td style="text-align:center;"> 6 </td>
   <td style="text-align:center;"> &gt;8000 </td>
   <td style="text-align:center;">  </td>
   <td style="text-align:center;">  </td>
   <td style="text-align:center;">  </td>
  </tr>
</tbody>
</table>

Additionally, we set the values -1 and -9 to `NA` since these values are unknown.


```r
# pop = population, hh_size = household size
input = dplyr::select(census, x = x_mp_1km, y = y_mp_1km, pop = Einwohner,
                      women = Frauen_A, mean_age = Alter_D,
                      hh_size = HHGroesse_D)
# set -1 and -9 to NA
input = mutate_all(input, funs(ifelse(. %in% c(-1, -9), NA, .)))
```
 
After the data preprocessing, we convert the table into a raster stack.
First, we use the x- and y-coordinates and the CRS to convert the `data.frame` into a spatial object.
`gridded()` converts a `SpatialPolygonsDataFrame` (but does not support `sf` objects) into a `SpatialPixelsDataFrame` which in turn can be used as an input for **raster**'s `stack()` function.
The final raster stack consists of four layers: inhabitants, mean age, portion of women and household size (Fig. \@ref(fig:census-stack)).


```r
# convert table into a raster (x and y are cell midpoints)
input = st_as_sf(input, coords = c("x", "y"))
# use the correct projection (see data description)
input = st_set_crs(input, 3035)
# convert into an sp-object
input = as(input, "Spatial")
gridded(input) = TRUE
# convert into a raster stack
input = stack(input)
```

<div class="figure" style="text-align: center">
<img src="figures/08_census_stack.png" alt="Gridded German census data of 2011. See Table \@ref(tab:census-desc) for a description of the classes." width="765" />
<p class="caption">(\#fig:census-stack)Gridded German census data of 2011. See Table \@ref(tab:census-desc) for a description of the classes.</p>
</div>

<!-- find out about new lines in headings + blank cells-->
We `reclassify()` the ordinal-scaled rasters in accordance with our survey (see section \@ref(case-study)).
In the case of the population data we convert the classes into a numeric data type using class means. 
This means we use 127 for class 1 (ranging from 3 to 250 inhabitants), 375 for class 2 (ranging from 250 to 500 inhabitants), etc. (Table \@ref(tab:census-desc)).
We arbitrarily chose 8000 inhabitants for class 6 since it represents cells where more than 8000 people live.
Of course, this is only a simple approximation of the true population number^[You can explore the introduced error in more detail in the exercises.], however, the level of detail is good enough for the purpose of delineating metropolitan areas (see next section).
By contrast, we convert the remaining input rasters into weight rasters whereas the highest weights are in correspondence with our survey.
For instance, the women class 1 (0-40%) receives a weight of 3 since our clientele is predominantly male.
Equally, the mean age class containing the youngest people receives the highest weight as well as the single households class.


```r
rcl_pop = matrix(c(1, 1, 127, 2, 2, 375, 3, 3, 1250, 
                   4, 4, 3000, 5, 5, 6000, 6, 6, 8000), 
                 ncol = 3, byrow = TRUE)
rcl_women = matrix(c(1, 1, 3, 2, 2, 2, 3, 3, 1, 4, 5, 0), 
                   ncol = 3, byrow = TRUE)
rcl_age = matrix(c(1, 1, 3, 2, 2, 0, 3, 5, 0),
                 ncol = 3, byrow = TRUE)
rcl_hh = rcl_women
rcl = list(rcl_pop, rcl_women, rcl_age, rcl_hh)
```

<!-- maybe a sentence or two of explanations could be important here -->

```r
reclass = input
for (i in seq_len(nlayers(reclass))) {
  reclass[[i]] = reclassify(reclass[[i]], rcl = rcl[[i]], right = NA) 
}
names(reclass) = names(input)
```

<!-- alternative code (more purrr) -->


### Define metropolitan areas

We arbitrarily define a pixel of 20 sq-km as metropolitan if more than half a million people lives in it.
The `aggregate()` command helps to change the resolution from 1 to 20 sq-km while each output cell represents the sum of all 1 sq-km input cells (see section \@ref(aligning-rasters)).
Next, we only keep cells with more than half a million inhabitants using a Boolean operation, and convert the resulting cells into spatial polygons of class `sf`.


```r
pop_agg = aggregate(reclass$pop, fact = 20000 / res(input)[1], fun = sum)
polys = rasterToPolygons(pop_agg[pop_agg > 500000, drop = FALSE])
polys = st_as_sf(polys)
```

Plotting these polygons reveals eight metropolitan regions (Fig. \@ref(fig:metro-areas)).
Each region consists of one ore more polygons (raster cells).
It would be nice if we could join all polygons belonging to one region.
One approach is to union the polygons (see section \@ref(spatial-data-aggregation)).


```r
polys = st_union(polys)
```

This returns one multipolygon feature with its elements corresponding to the metropolitan regions. 
To extract these polygons from the multipolygon, we can use `st_cast()`.


```r
metros = st_cast(polys, "POLYGON")
```


<!-- maybe a good if advanced exercise
This requires finding the nearest neighbors (`st_intersects()`), and some additional processing.
Do not worry too much about the following code.
There is probably a better way to do it. 
Nevertheless, it finds all pixels belonging to one region in a generic way.
We use this information to assign each polygon (pixel) to a region.
Subsequently, we can use the region information to dissolve the pixels into region polygons.


```r
# dissolve on spatial neighborhood
nbs = st_intersects(polys, polys)
# nbs = over(polys, polys, returnList = TRUE)

fun = function(x, y) {
  tmp = lapply(y, function(i) {
  if (any(x %in% i)) {
   union(x, i)
  } else {
   x
    }
  })
  Reduce(union, tmp)
}
# call function recursively
fun_2 = function(x, y) {
  out = fun(x, y)
  while (length(out) < length(fun(out, y))) {
    out = fun(out, y)
  }
  out
}

cluster = map(nbs, ~ fun_2(., nbs) %>% sort)
# just keep unique clusters
cluster = cluster[!duplicated(cluster)]
# assign the cluster classes to each pixel
for (i in seq_along(cluster)) {
  polys[cluster[[i]], "region_id"] = i
}
# dissolve pixels based on the the region id
polys = group_by(polys, region_id) %>%
  summarize(pop = sum(layer, na.rm = TRUE))
# polys_2 = aggregate(polys, list(polys$region_id), sum)
plot(polys[, "region_id"])

# Another approach, can be also be part of an excercise

coords = st_coordinates(polys_3) %>% 
  as.data.frame
ls = split(coords, f = coords$L2)
ls = lapply(ls, function(x) {
  dplyr::select(x, X, Y) %>%
    as.matrix %>%
    list %>%
    st_polygon
})
metros = do.call(st_sfc, ls)
metros = st_set_crs(metros, 3035)
metros = st_sf(data.frame(region_id = 1:9), geometry = metros)
st_intersects(metros, metros)
plot(metros[-5,])
st_centroid(metros) %>%
  st_coordinates
```
-->

However, visual inspection reveals eight metropolitan areas whereas the unioning-casting approach comes up with nine.
This is because one polygon just touches the corner of another polygon (western Germany, Cologne/Düsseldorf area; Fig. \@ref(fig:metro-areas)).

<div class="figure" style="text-align: center">
<img src="figures/08_metro_areas.png" alt="The aggregated population raster (resolution: 20 km) with the identified metropolitan areas (golden polygons) and the corresponding names." width="450" />
<p class="caption">(\#fig:metro-areas)The aggregated population raster (resolution: 20 km) with the identified metropolitan areas (golden polygons) and the corresponding names.</p>
</div>

One could assign it to the neighboring region using a dissolving procedure, however, we leave this as an exercise to the reader, and simply delete the offending polygon.


```r
# find out about the offending polygon
int = st_intersects(metros, metros)
# polygons 5 and 9 share one border, delete polygon number 5
metros_2 = metros[-5]
```

The defined metropolitan areas suitable for bike shops are still missing a name.
A reverse geocoding approach can settle this problem.
Given a coordinate, reverse geocoding finds the corresponding address.
Consequently, extracting the centroid coordinate of each metropolitan area can serve as an input for a reverse geocoding API.
The **ggmap** package makes use of the one provided by Google.^[Note that Google allows each user to access its services on a free basis for a maximum of 2500 queries a day.]
`ggmap::revgeocode()` only accepts geographical coordinates (latitude/longitude), therefore, the first requirement is to bring the metropolitan polygons into an appropriate coordinate reference system (chapter \@ref(transform)).


```r
# reverse geocoding to find out the names of the metropolitan areas
metros_wgs = st_transform(metros_2, 4326)
coords = st_centroid(metros_wgs) %>%
  st_coordinates() %>%
  round(., 4)
#> Warning in st_centroid.sfc(metros_wgs): st_centroid does not give correct
#> centroids for longitude/latitude data
```

Additionally, `ggmap::revgeocode()` only accepts one coordinate at a time, which is why we iterate over each coordinate of `coords` via a loop (`map_dfr()`).
`map_dfr()` does exactly the same as `lapply()` except for returning a `data.frame` instead of a `list`.^[To learn more about the split-apply-combine strategy for data analysis, we refer the reader to @wickham_split-apply-combine_2011.]
Sometimes, the reverse geocoding API of Google is unable to find an address returning `NA`.
Often enough trying the same coordinate again, returns an address at the second or third attempt (see `while()-loop`).
However, if three attempts have already failed, this is a good indication that the requested information is indeed unavailable.
Since it is our interest to be a good cyberspace citizen, we try not to overburden the server with too many queries within a short amount of time. 
Instead we let the loop sleep between one and four seconds after each iteration before accessing the reverse geocoding API again.


```r
metro_names = map_dfr(1:nrow(coords), function(i) {
  add = ggmap::revgeocode(coords[i, ], output = "more")
  x = 2
  while (is.na(add$address) & x > 0) {
    add = ggmap::revgeocode(coords[i, ], output = "more")
    # just try three times
    x = x - 1
  }
  # give the server a bit time
  Sys.sleep(sample(seq(1, 4, 0.1), 1))
  # return the result
  add
})
```






Choosing `more` as `revgeocode()`'s `output` option will give back a `data.frame` with several columns referring to the location including the address, locality and various administrative levels.
Overall, we are satisfied with the `locality` column serving as metropolitan names (München, Nürnberg, Stuttgart, Frankfurt, Hamburg, Berlin, Leipzig) apart from one exception, namely Velbert.
Hence, we replace Velbert with the corresponding name in the `administrative_area_level_2` column, that is Düsseldorf (Fig. \@ref(fig:metro-areas)).
Umlauts like `ü` might lead to trouble further on, for example when determining the bounding box of a metropolitan area with `opq()` (see further below), which is why we replace them.


```r
metro_names = 
  dplyr::select(metro_names, locality, administrative_area_level_2) %>%
  # replace Velbert and umlaut ü
  mutate(locality = ifelse(locality == "Velbert", administrative_area_level_2, 
                           locality),
         locality = gsub("ü", "ue", locality)) %>%
  pull(locality)
```

### Points of interest

The **osmdata** package provides a fantastic and easy-to-use interface to download OSM data (see also section \@ref(retrieving-data)).
Instead of downloading all shops for the whole of Germany, we restrict the download to the defined metropolitan areas. 
This relieves the OSM server resources, reduces download time and above all only gives back the shop locations we are interested in.
The `map()` loop, the `lapply()` equivalent of **purrr**, runs through all eight metropolitan names which subsequently define the bounding box in the `opq()` function (see section \@ref(retrieving-data)).
Alternatively, we could have provided the bounding box in the form of coordinates ourselves.
Next, we indicate that we only would like to download `shop` features (see this [page](http://wiki.openstreetmap.org/wiki/Map_Features) for a full list of OpenStreetMap map features).
`osmdata_sf()` returns a list with several spatial objects (points, lines, polygons, etc.).
Here, we will only keep the point objects.
As with Google's reverse geocode API, the OSM-download will once in a while not work at the first attempt.
The `while` loop increases the number of download trials to three. 
If then still no features can be downloaded, most likely there are none.
Or it is an indication that another error has occurred before. 
For instance, the `opq()` function might have retrieved a wrong bounding box.


```r
shop_download_osm = function(x){
  message("Downloading shops of: ", x, "\n")
  # give the server a bit time
  Sys.sleep(sample(seq(5, 10, 0.1), 1))
  query = opq(x) %>%
    add_osm_feature(key = "shop")
  points = osmdata_sf(query)
  # request the same data again if nothing has been downloaded
  iter = 2
  while (nrow(points$osm_points) == 0 & iter > 0) {
    points = osmdata_sf(query)
    iter = iter - 1
  }
  points = st_set_crs(points$osm_points, 4326)
}
shops = map(metro_names, shop_download_osm)
```

It is highly unlikely that there are no shops in any of our defined metropolitan areas.
The following `if` condition simply checks if there is at least one shop for each region.
If not, we would try to download again the shops for this/these specific region/s.


```r
# checking if we have downloaded shops for each metropolitan area
ind = map(shops, nrow) == 0
if (any(ind)) {
  message("There are/is still (a) metropolitan area/s without any features:\n",
          paste(metro_names[ind], collapse = ", "), "\nPlease fix it!")
}
```

To make sure that each list element (an `sf`- data frame) comes with the same columns, we only keep the `osm_id` and the `shop` columns with the help of another `map` loop.
This is not a given since OSM contributors are not equally meticulous when collecting data.
Finally, we `rbind` all shops into one large `sf` object.


```r
# select only specific columns and rbind all list elements
shops = map(shops, dplyr::select, osm_id, shop) %>%
  reduce(rbind)
```





It would have been easier to simply use `map_dfr()`. 
Unfortunately, so far it does not work in harmony with `sf` objects.

The only thing left to do is to convert the spatial point object into a raster.
The `rasterize()` function does exactly this.
As input it expects an `sp` of `sf` vector object (here we use the spatial point object `shops`), and a raster object (here we use the population raster whose original values have been replaced by `NA`'s).
A function defines how the values from the spatial vector object are transferred to the raster object. 
`count` simply counts the number of spatial objects falling into one raster cell, in this example the shop points, and returns this value as the output cell value.
Hence, we end up with a shop density, namely the number of shops per square kilometer.
But one has too be careful: had we used the `shop` instead of the `osm_id` column, we would have retrieved fewer shops per grid cell. 
This is because the `shop` column contains `NA` values, which the `count()` function omits when rasterizing vector objects.
Naturally, the projection of the input raster and the input vector object have to match which is why we first have to reproject our shops to the CRS of the raster object.


```r
shops = st_transform(shops, proj4string(input$pop))
# create poi raster
poi = rasterize(x = shops, y = input$pop, field = "osm_id", fun = "count")
```

As with the other rasters (population, women, mean age, household size) we would like to classify the `poi` raster into four classes (see section \@ref(create-census-rasters)). 
Defining class intervals is an arbitrary undertaking to a certain degree.
One can use equal breaks, quantile breaks, fixed values and many more.
Here, we choose the Fisher-Jenks natural breaks approach which tries to minimize the within-class variance.
Naturally, the identified breaks serve as input for the reclassification matrix.


```r
# construct reclassification matrix
int = classInt::classIntervals(values(poi), n = 3, style = "fisher")
int = round(int$brks)
rcl_poi = matrix(c(int[1], rep(int[-c(1, length(int))], each = 2), 
                   int[length(int)] + 1), ncol = 2, byrow = TRUE)
rcl_poi = cbind(rcl_poi, 0:3)  
# reclassify
poi = reclassify(poi, rcl = rcl_poi, right = NA) 
names(poi) = "poi"
```

### Identifying suitable locations

As usual in (geographic-)data science, the data retrieval and preprocessing represented the lion's share of the overall workload.
The final step, the calculation of a final score by summing up all prepared rasters, is a simple one-liner.
Before doing that, we add the POI raster to and delete the population raster from the raster stack.
The reasoning for the latter is twofold.
First of all, we already have delineated metropolitan areas, that is areas where the population density is above average compared to the rest of Germany.
Secondly, though it is advantageous to have many potential customers within a specific catchment area, the sheer number alone might not actually represent the desired target group.
For instance, residential tower blocks are areas with a high population density but not necessarily with a high purchasing power for luxurious bike components.


```r
# add poi raster
reclass = addLayer(reclass, poi)
# delete population raster
reclass = dropLayer(reclass, "pop")
# calculate the total score
result = sum(reclass)
```

The result is a score summing up the values of all input rasters.
For instance, a score greater 10 might be a suitable threshold indicating raster cells where to place a bike shop (Figure \@ref(fig:bikeshop-berlin)).

<div class="figure" style="text-align: center">
preserve3f708cd46e8f51ce
<p class="caption">(\#fig:bikeshop-berlin)Suitable areas (i.e., raster cells with a score > 10) in accordance with our hypothetical survey for bike stores in Berlin.</p>
</div>

## Discussion and next steps

The presented approach is a typical example of the normative usage of a GIS [@longley_geographic_2015].
We combined survey data with expert-based knowledge and assumptions (definition of metropolitan areas, defining class intervals, definition of a final score threshold).
It should be clear that this approach is not suitable for scientific knowledge advancement but is a very applied way of information extraction.
This is to say, we can only suspect based on common sense that we have identified areas suitable for bike shops.
However, we have no proof that this is in fact the case.

A few other things remained unconsidered but might improve the analysis:

- We used equal weights when calculating the final scores.
But is, for example, the household size as important as the portion of men or the mean age?
- We used all points of interest. 
Maybe it would be wiser to use only those which might be interesting for bike shops such as do-it-yourself, hardware, bicycle, fishing, hunting, motorcycles, outdoor, sports shops, etc. (see all the other columns of the osmdata simple features and [Map_Features#Shop](http://wiki.openstreetmap.org/wiki/Map_Features#Shop)).
- Maybe data at a better resolution changes and improves the output. For example, there is also population data at a finer resolution (100 m; see exercises).
- We have used only a limited set of variables. 
The [INSPIRE geoportal](http://inspire-geoportal.ec.europa.eu/discovery/) might contain much more data of possible interest to our analysis.
The bike paths density might be another interesting variable as well as the purchasing power or even better the retail purchasing power for bikes.
- Interactions remained unconsidered such as a possible interaction between the portion of men and single households.
However, to find out about such an interaction we would need customer data.

In short, the presented analysis is far from perfect.
Nevertheless, it should have given you a first impression and understanding of how to obtain, and deal with spatial data in R within a geomarketing context.

Finally, we have to point out that the presented analysis would be merely the first step of finding suitable locations.
So far we have identified areas, 1 by 1 km in size, potentially suitable for a bike shop in accordance with our survey.
We could continue the analysis as follows:

- Find an optimal location based on number of inhabitants within a specific catchment area.
For example, the shop should be reachable for as much people as possible within 15 minutes of traveling bike distance (catchment area routing).
Thereby, we should account for the fact that the farther away the people are from the shop, the more unlikely it becomes that they actually visit it (distance decay function).
- Also it would be a good idea to take into account competitors. 
That is, if there already is a bike shop in the vicinity of the chosen location, one has to distribute possible customers (or sales potential) between the competitors [@huff_probabilistic_1963; @wieland_market_2017].
- We need to find suitable and affordable real estate (accessible, parking spots, frequency of passers-by, big windows, etc.).

## Exercises

1. Download the csv file containing inhabitant information for a 100 m cell resolution (https://www.zensus2011.de/SharedDocs/Downloads/DE/Pressemitteilung/DemografischeGrunddaten/csv_Bevoelkerung_100m_Gitter.zip?__blob=publicationFile&v=3).
Please note that the unzipped file has a size of 1.23 GB.
To read it into R you can use `readr::read_csv`.
This takes 30 seconds on my machine (16 GB RAM)
`data.table::fread()` might be even faster, and returns an object of class `data.table()`.
Use `as.tibble()` to convert it into a tibble.
Build an inhabitant raster, aggregate it to a cell resolution of 1 km, and compare the difference with the inhabitant raster (`inh`) we have created using class mean values.
1. In the text we have deleted one polygon of the `metros` object (polygon number 5) since it only touches the border of another polygon.
Recreate the `metros` object and instead of deleting polygon number 5, make it part of the Cologne/Düsseldorf metropolitan region (hint: create a column named region_id, add polygon number 5 to the Cologne/Düsseldorf area and dissolve).
1. Suppose our bike shop predominantly sold electric bikes to older people. 
Change the age raster accordingly, repeat the remaining analyses and compare the changes with our original result.

<!--chapter:end:07-location.Rmd-->


# Transport applications

## Prerequisites {-}


```r
library(dplyr)
library(osmdata)
library(stplanr)
library(sf)
library(tmap)
```


In no other sector is geographic space more tangible than transport.
It is the effort of moving, particularly between places that are far apart, that led to the 'first law' of geography defined by Waldo Tobler in 1970 as follows [@miller_toblers_2004]: 

> Everything  is related  to  everything  else,  but  near  things  are more  related  than  distant  things

This 'law' applies to phenomena as diverse as friendship networks and ecological diversity and can be explained by the costs of transport --- in terms of time, energy and money.
These costs are known as the 'friction of distance'.
Thus transport technologies disrupt geographic relationships from the perspective of mobile humans and goods: "the purpose of transportation is to overcome space" [@rodrigue_geography_2013].

Transport is an inherently geospatial activity.
It involves traversing continuous geographic space between A and B, and infinite localities in between.
It is therefore unsurprising that transport researchers have long turned to geocomputational methods to understand movement patterns and that transport problems are a motivator of geocomputational methods.

This chapter provides an introduction to geographic analysis of transport systems.
We will explore how movement patterns can be understood at multiple geographic levels, including:

- Areal units: transport can be understood simply in terms of zonal aggregates such as the main mode and average distance of trips made people living in a particular zone.
- Nodes: these are points in the transport system that can represent common origins and destinations (e.g. with one centroid per zone) and public transport stations such as bus stops and rail stations.
- Desire lines: straight lines that represent 'origin-destination' data that records how many people travel (or could travel) between places (points or zones) in geographic space.
- Routes: these are cirquitous (non-straight) routes, typically representing the 'optimal' path along the route network between origins and destinations along the desire lines defined in the previous bullet point.
- Route networks: these represent the system of roads, paths and other linear features in an area. They can be represented as purely geographic entities or as a graph.
Their features are segments which can be assigned values representing 'flow', the number of people expected to use a particular street or path.
- Agents: these are the lowest-level but hardest to model entities in transport systems --- mobile entities like you and me.

These six levels of analysis show that transport systems are highly complex, even before accounting for the innevitable fact that all of them are constantly evolving in continuous time.
The purpose of geographic transport modelling can be interpretted as simplifying this complexity in a way that captures the essence of transport problems.

Typically models are designed to solve a particular problem.
For this reason this chapter is based around a policy scenario that asks:
how to increase walking and cycling?
We will use input data from Bristol, a coastal city in the West of England, described in the next section.

## Input data: a case study of Bristol

The case study used for this chapter is a diverse city on the west of England, 30 km east of the Welsh capital Cardiff.
As with any case study it is worth taking some time to consider the local geography of the area, e.g. as dispayed in Figure 7.0 below.
This shows the diversity of the city's transport network, with railways, motorways and cycle paths plotted.



The data used in this section was downloaded using **osmdata**.
To avoid having to request the data from OSM repeadetly, we'll use a locally saved version of the data, which contains point and line data for the case study area:


```r
ways = readRDS("extdata/ways.Rds")
summary(ways)[4:5, ]
#>            Length Class Mode
#> osm_points 54     sf    list
#> osm_lines  85     sf    list
```

The above code chunk loaded some key data and shows that way have a few dozen nodes and lines on the transport network: an easily manageable dataset size (transport datasets can get very large but it's best to learn with small ones).
Before we make use of these datasets we need to load and take a look at one more type of input data: transport zones that represent residential areas that generate trips into the city centre and elsewhere.


<div class="figure" style="text-align: center">
<img src="figures/bristol.png" alt="Overview map of the city of Bristol" width="562" />
<p class="caption">(\#fig:bristol)Overview map of the city of Bristol</p>
</div>

## Transport zones

Although transport systems are inherently based on linear features and nodes --- the nodes and edges of the transport network --- it often makes sense to start with areal data.
Three types of zone will typically be of particular interest: the study region, origin zones (typically residential areas), and destination zones (which are often the same as the origin zones).

The simplest definition of the study area is typically the first matching boundary returned by OpenStreetMap, which can be obtained using the **osmdata** package as follows:


```r
region = getbb("Bristol", format_out = "polygon")[1]
```

OSM will will often contain valid depiction of the case study city or region of interest (in this case the result is the same as the officially defined area of the Local Authority District).
However the approach is problematic because OSM data may not correspond to the most recent administrative areas over which transport planning authorities have control, meaning the analysis may be of limited interest to local transport planners.
More importantly, official administrative zones often do not relate to 'travel watersheds', areas that can are defined not by (often arbitrary) political decisions but by data on where people actually travel to.

To overcome this issue for transport data analysis in the UK, the Travel to Work Areas (TTWAs) were created.
TTWAs are contiguous zones defined roughly as areas in which 75% of the population both live and work.
Because Bristol is a major employer attracting travel from surrounding towns, its TTWA is substantially larger than its administratively defined area, as illustrated in Figure \@ref(ttwa-bristol).




```r
region = readRDS("extdata/bristol-region.Rds")
qtm(region)
#> Warning: Currect projection of shape region unknown. Long-lat (WGS84) is
#> assumed.
```

<div class="figure" style="text-align: center">
<img src="figures/ttwa-bristo-1.png" alt="Region definitions in Bristol" width="576" />
<p class="caption">(\#fig:ttwa-bristo)Region definitions in Bristol</p>
</div>



## Nodes on the transport system


```r
stations = ways$osm_points %>% 
  filter(railway == "station" | name == "Bristol Temple Meads")
```


## Desire line analysis

## Route analysis

## Route networks

## Agents in the transport system

<!--chapter:end:08-transport.Rmd-->


# References {-}

<!--chapter:end:references.Rmd-->
