@title[Title]

## <span class="green">SLYR</span>
### or: how I learned to stop worrying about ESRI Symbols!
<br>
<br>
<span class="byline">International User Conference 2019, A Coruña - March 6, 2019</span>

Note:
Good morning, my name is Mario Baranzini, I work for Opengis.ch, a small company
in Switzerland that deals with open-source developments mainly related to QGIS.
Today I want to talk to you about a project to which we have contributed and
which can help to making the transition from proprietary solutions, or one
in particular, to QGIS, simpler.

---
@title[Who am I?]
## Who am <span class="green">I</span>?
<span class="green">Mario Baranzini</span>  
BSc in Computer Science  
CAS in Computing (Software engineering)  
Developer, Consultant, Teacher, Student

Note:
just 2 words about me...
My name is Mario Baranzini.
I work as a developer (mostly on Python and Java), a consultant, and a teacher in the GIS field. But I also try to always improve my Software engineering skills. I come from the Italian speaking part of Switzerland (so sorry for my English...).

---
@title[OpenGIS.ch]
### <span class="green">OPENGIS.ch</span> 
Open source Geo-spatial Experts at your doorsteps
![opengis.ch](assets/images/opengis_team.png)

Note:
I work in a small distributed company called OpenGIS.ch. We are
specialized on open-source GIS and web development for small and medium
businesses.

---
@title[The Problem]
## The problem

TODO: picture of library in ARCgis

- 1203 ESRI Symbols
- Points, Lines, Polygons
- Extensive use of ESRI Fonts

Note:
It all started last year, when a client, a public administration who has
always worked with ESRI finally decided to support QGIS users and start using it
to publish their projects. But over the years they have created a library of
over 1200 symbols that are used in various places. The library includes symbols
for points, lines, and polygons and makes extensive use of ESRI fonts.

---
@title[Requirements]
## Requirements
- QGIS XML Library with all the symbols
- No proprietary fonts

Note:
The customer wanted as a result an xml library with the symbols that he can
imported and used in QGIS. He didn't want to install proprietary fonts on and so
all symbols using ESRI characters will have to be converted in some way.

---
@title[Difficulties]
## Difficulties
- No tools with the required quality

Note:
There were no tools to automatically convert symbols with the quality we
needed. There are some proprietary tools, but they can only convert very simple
symbols for which there is a exact counterpart in QGIS and do not allow to
handle more complex things such as converting characters or symbols with an
image inside or with multiple conversion steps.

---
@title[ESRI Symbols]
## ESRI Symbols

TODO: Binary dump image
- Difficult to interpret binary files
- Bad ArcGIS Python API for symbols

Note:
ESRI symbols are saved in rather complex and difficult to interpret binary
files. Unfortunately, ArcGIS' Python programming interface allows only a very
small amount of symbol information to be extracted. Unlike PyQGIS which allows
you to interact on every aspect of symbols.

---
@title[How Could We Do That?]
### How Could We Do That?
By hand?  
![factory](assets/images/chinese_factory.jpg)


Note:
The idea of converting them by hand never seemed to us to be a good idea. In
addition to the tedious and repetitive work, it would be an end in itself, which
would not produce anything useful for other users and would always require
manual intervention in case of modification to the original symbols.

But at first analysis it seemed almost impossible to create a tool capable of
correctly interpreting the binary symbols and to recreate them in QGIS.

---
@title[ESRI Style Specs]
## ESRI Style Specs
TODO: Nyall picture

Note:
We remembered that Nyall had started working on a project to try to read and
interpret the binary files of the ESRI symbols. He was at the beginning and was
only able to interpret a small part of the information we were interested
in. But it gave us hope that the project could evolve and support more
features. In any case, it would reduce the number of symbols to be converted
manually. We therefore decided to contribute with Nyall to the development of this tool
(which was renamed to SLYR).

---
@title[SLYR]
## SLYR
![factory](assets/images/slyr.png)

Note:

+++
@title[Features]
## Features
- features
  - colors
  - complete support for fill types
  - complete support for line types except picture lines
  - complete support for marker types
  - conversion on fonts to svg
  - conversion of pictures
  - conversion of color ramps
- available commands, plugins, processing toolbox

Note:

+++
@title[Limitations]
## Limitations
- missing functionality in QGIS symbology, e.g. no support for random
  pattern/line fills
- some symbol types not yet converted, e.g. gradient fills
- version dependence - the style format changes regularly and the tool needs
  to be modified to handle different versions of the file format as they are
  encountered
- only supports .style files, which currently require ArcGIS to create. No
  direct LYR/MXD to QGIS conversion without ESRI software (yet)
- requires the mdbtools library to read the .style database - it's a bit of a
pain to install on some platforms.

Note:

+++
@title[Demo]
## Demo
???
Note:

---
@title[How To Contribute]
## How To Contribute
- Use it
- TODO: Aiuta a farlo conoscere, 
- TODO: Finanzia nuovi sviluppi
Note:

---
@title[Conclusions]
## Conclusions

Note:
SLYR provides a very important tool that can greatly simplify the life of those
who decide to switch from ESRI to QGIS. In addition to providing a useful tool,
the development has also allowed a better understanding of the structure of the
different ESRI binaries and suggests that it is possible to do the same work and
automatically convert MXD projects.

---
@title[Thank you]
## Thank <span class="green">you</span>
#### for your attention
Note:
Thank you for your attention.
