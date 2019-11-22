# CSV Schema, fmt/800

First off, according to <http://digital-preservation.github.io/csv-schema/>
there are now three versions of CSV Schema (the last being a working draft), so
it might be appropriate to add version number 1.0 to the fmt/800 entry and
assign two additional PUIDs for versions 1.1 and 1.2 of CSV Schema.

The only constant, non-optional part near the beginning of a CSV Schema file
seems to be the version declaration, `version 1.0`, `version 1.1`, or `version
1.2`, which may be preceded by comments. Comments are either single line
comments (`//` until EOL) or multiple line comments (`/* ... */`). The version
declaration is followed by several optional elements that, being optional, are
not very reliable in terms of file format identification.

So one of the following three patterns should (together with the file name
extension) match a CSV Schema file in most cases:

  * The version declaration directly at BOF (`version 1.[012]`):

        76657273696F6E20312E(30|31|32)

  * The version declaration preceded by one or more single line comments (`//
    ... version 1.[012]`):

        2F2F*76657273696F6E20312E(30|31|32)

    This needs a variable-length pattern because neither the number of comments
    nor their length is known in advance.

  * The version declaration preceded by one or more multiple line comments (`/*
    ... */ ... version 1.[012]`):

        2F2A*2A2F*76657273696F6E20312E(30|31|32)

    This needs two variable-length patterns, one for the content of the comment
    and another for possible whitespace or even more (single or multi line)
    comments after the initial comment.

This does not account for whitespace preceding one of the patterns (i.e., a file
starting with something weird like "  version 1.1" -- I am not sure though
whether this is legal per the spec). So maybe it would be better to allow some
offset between the BOF and the version declaration; depending on the size of the
offset this would also render the two comment-respecting patterns unnecessary
because the comments would be eaten by the offset.
