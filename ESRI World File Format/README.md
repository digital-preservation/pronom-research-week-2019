# ESRI World File Format, fmt/367

The content of a World File consists of six lines of plain text, each of which
contains a (possibly negative) real number (see the [Wikipedia
entry](https://en.wikipedia.org/wiki/World_file)). If this pattern could be
described with a PRONOM regular expression it would, together with the file name
extension, make a nice signature. Using "normal", Perl-like regular expressions
this would look something like this, repeated for six lines:

    -?[0-9]+(\.[0-9]+)?\r?\n

However, as far as I can tell from the descriptions in [Digital Preservation
Technical Paper 1: Automatic Format Identification Using PRONOM and
DROID](http://www.nationalarchives.gov.uk/aboutapps/fileformat/pdf/automatic_format_identification.pdf),
page 8, the PRONOM regular expression syntax seems to be less expressive. It can
either describe zero or more arbitrary bytes from the full range of 0x00 to 0xff
(`??`, `{n}`, `{n-m}`, `*`) *or* a specific byte pattern (`(a|b)`, `[a:b]`), but
not a combination of both i.e., a quantified pattern like `[0-9]+` used in the
above expression.

*So with the current syntax a precise signature for World Files seems
impossible. Maybe this can be put on the long-term agenda in case the PRONOM
regular expressions will be revised some day?* (I guess this applies to several
other text-based formats as well.)
