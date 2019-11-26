# Apple iWork file formats 

- Format name - Apple iWork document versions 
- Version number - 09, 2014

- PUID - fmt/646 Apple iWork Keynote 09
- added signature fmt/825	Apple iWork Numbers 09
- added signature fmt/824	Apple iWork Pages 09
- added signature CHLdev/1 Apple iWork Document 14

- Extensions - key, pages, numbers
- MIME/Media Type - application/vnd.apple.keynote, application/vnd.apple.pages, application/vnd.apple.numbers
- Description - Apple iWork is a suite of office applications for the Macintosh OS. Consists of Keynote, Pages, and Numbers. 
- Format type - Presentation, Word Processor & Spreadsheet
- Vendor - Apple

# Notes
http://justsolve.archiveteam.org/wiki/IWork

- iWork 05, 06, 08 all used a "package" format which appears as a single file on MacOS, but is a folder, with an extension. 
- iWork 09 containerized the contents into a ZIP file
- iWork 2013 reverted back to "package" format, but uses new ".iwa" files for content.  
- iWork 2014 containerized contents again into ZIP file, but with new ".iwa" files. Structure for all Keynote, Pages, Numbers formats too identical to distiguish with current container identification syntax.

- fmt/646 Apple iWork Keynote 09 already existed, used template to create signature for fmt/825	Apple iWork Numbers 09 & fmt/824	Apple iWork Pages 09

I have also included a couple samples of password protected files made through the Pages app. Signature currently does not identify them.
