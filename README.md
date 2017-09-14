# assembla-export
Old website, tickets, etc from the assembla hosting

The tickets are saved in the tickets subdir. There are two main
exports in there "all" and "all-with-custom". It seems that for XML
export the explicit selection of all custom fields is not needed as
the two XML files are the same byte size. Though they do differ with
md5 and diff command.

The all.csv file contains all fields other than the custom ones.
all-with-custom also contains all the custom fields (around 4 of
them). Note that the csv files are saved mainly for completeness as
the description is multi lined and the csv files exported from
assembla lack explicit field quotes so will likely be hard to directly
use in programs.

The goal of these ticket exports is completeness. I am happy to merge
html conversions of this data into the repository at a later date.

The wiki subdirectory contains the source, complete html save
including resources, and two pdf exports for each page. The source is
in foo.md and can be HTML, markdown, or a strange mixture of both. The
complete HTML save was done in Firefox and is considered the golden
source. It is the page viewed as it the site delivered it at September
2017 from Assembla. The two pdf exports are secondary exports and are
performed by printing the page in Firefox and as a PDF export from
assembla. The Assembla pdf exports are in the wiki/pdf subdirectory.
The Firefox page prints are in foo.pdf alongside the source and html
save as foo.html.

For simple reference
foo.md    -- source
foo.html  -- complete web page save
foo_files -- assets used by foo.html
foo.pdf   -- web page print from Firefox
pdf/something-like-foo.pdf -- pdf produced by Assembla.

foo.md is the source, and foo.html is the golden rendering. The wiki
is designed to be consumed in the browser so the HTML rendering is the
primary rendering.

