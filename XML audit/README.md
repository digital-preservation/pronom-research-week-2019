# Richard's #PRONOM2019 XML audit

## What's in this repo

Two CSVs where I've collated the XML signatures I could find: 
  - binary_xml.csv has the xml binary signatures; 
  - zip_xml.csv has the xml signatures within ZIP containers (most of the ZIP container signatures are XML).

I've also included a DOT graph (xmlgraph.txt) with all the formats that declare a relationship to XML. This is slightly larger than my sample (62).

The ZIP xml signatures are quite uniform & many ID via simple attributes like ContentType or manifest:media-type. So I didn't analyze further.

The binary xml signatures show a lot more variety and I categorised by interesting features like:
  - does the signature require an XML declaration. At what offsets?
  - does the signature match by a root or end tag. At what offsets?
  - does the signature match by xml namespace
  - other elements/attributes required (I didn't fill this in very consistently)
  - are there multiple signatures for different text encodings?

## Findings

1. I looked at ~50 binary XML signatures and ~50 ZIP XML signatures. I also included some sigs that aren't stricly xml like html sigs.

2. I found these signatures by searching for angle brackets. Often they get a "Text" label in PRONOM but otherwise aren't clearly labelled as XML. Another way to find XML signatures is to look for format relationsips to XML fmt/101 (see xmlgraph.txt in this repo)

3. About 80% of the signatures sampled require an XML declaration, generally at a 0 offset (though some had 0-3). Some of these had multiple variations of the declaration, allowing double or single quotes; others required a fixed form.

4. About 80% of the signature samples look for a root tag. These had varying offsets: a smatter are wild, many had a range up to 256, a bunch had smaller ranges.

5. Only 8 signatures look for a closing tag. Mostly this is at different offsets from the end of file, though some looked for it at a wild offset from the start of the file (e.g. SVG). The most interesting XML signature is the XSD signature which doesn't look for a root element and just looks for the closing tag instead.

6. About 20 signatures look for a default namespace or DOCTYPE

7. 3 of the signatures in the sample had multiple variants allowing for the possibility of different text encodings (UTF8 and UTF16 big endian).

## Recommendations

1. Pick a standard for allowable offsets for the opening and closing tags. No wild cards here - I'm looking at you SVG!

2. In XML 1.0 the XML declaration is optional - many of the signatures require it however. Suggest more variant signatures that start with the root tag - again, I'd like this for SVG!

3. More signatures with end tags? This may be a way to find broken XML files

4. Down the track... XML aware detection that would match on root tags, default namespace but wouldn't be dependent on vagaries of the format like text encoding, comments, whitespace, single/double quotes etc. that mess up byte matching at precise offsets! 

