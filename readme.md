## NISMOD: Teaching Kit

This repository contains the teaching material developed by University of Oxford
for the course "Infrastructure and Climate Resilience" developed under the
Climate Compatible Growth project.

The course is published on [Open Learn Create](https://www.open.edu/openlearncreate/course/view.php?id=7243)
and is free to learners.

The course material is licensed under a [Creative Commons BY 4.0 License](https://creativecommons.org/licenses/by/4.0).
This license allows you to use, remix and publish the course material as long as you give correct
attribution. Please use the following citation:

    Amelie Paszkowski, Daniel Adshead, Sapphire Vital, Orlando Roman, Lena Fuldauer, Prof Jim W Hall, Raghav Pant, Sarah Gall, Olivia Becher, Aman Majid, Jasper Verschuur, Robyn Haggis, Yu Mo, & Nicholas Chow. (2021, August 6). ClimateCompatibleGrowth/nismod_teaching_kit: Initial release of lecture blocks. Zenodo. https://doi.org/10.5281/zenodo.5166742

### Creating the teaching material

The teaching material is rendered to HTML using a bash script.
A key dependency is [pandoc](https://pandoc.org/), which is used to convert the markdown lecture block files into HTML.

To generate the LaTeX files in the `_build` folder, run:

    bash scripts/create_tex.sh

Then (manually!) comment out all the preliminary style/package/directory latex stuff
leaving only the content between `\begin{document}` and `\end{document}` so
that we can include these files in `outline.tex`.

To copy all assets up to a common directory:

    mkdir -p assets
    find docs/*/assets/* -exec cp {} ./assets/ \;

To generate `outline.pdf`:

    pdflatex outline.tex
