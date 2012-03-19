bpgead2pdf
==========

bpgead2pdf is a small program to transform [EAD](http://loc.gov/ead/) that complies with the [Yale University Best Practice Guidelines](http://www.library.yale.edu/facc/bpgs.html) to a PDF version using our stylesheets.

After some back of the napkin calculations, it's clear that Saxon is faster and less resource-intensive than Xalan, and that this application itself is not necessary as we can use Saxon's TransformerFactor implementation from within fop itself (see [this Gist for a shell script solution](https://gist.github.com/2076614)).

Building bpgead2pdf
-------------------

To build, you'll need Ant. All the program's other dependencies are included. Run the following to build:

    $ ant jar
    
Running bpgead2pdf
------------------

To run:

    $ java -jar bpgead2pdf.jar <inputfile.xml>

For example:

    $ java -jar bpgead2pdf.jar mssa.ms.1746.xml

The PDF file generated will be placed in the "out" subdirectory.

Known Issues
------------

The application may not resolve the required font for the stylesheet (Arial Unicode MS) on certain platforms.