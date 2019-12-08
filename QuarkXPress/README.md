# QuarkXPress Desktop Publishing Files 

- Format Name: QuarkXPress Documents & Projects
- Versions: 3.1 - 15
- PUID:  See Below
- Extensions: QXD, QXT, QXP, QPT, QWD
- MIME: application/vnd.Quark.QuarkXPress
- Description: QuarkXPress is a Desktop Publishing Application which was first released in 1987. Versions 1-3 where Macintosh only, Starting in version 3.1 common signature was used.
- Format Type: Presentation?
- Vendor: Quark Software Inc.

These signatures replace signatures x-fmt/182, fmt/652, fmt/685, fmt/651

Two signature options are being suggested. A grouped signature based on version compatibility and a signature with a format for each major version.

### Grouped Signature
- Name="QuarkXPress Document" PUID="CHLdev/1" Version="3.1 - 6"
- Name="QuarkXPress Project" PUID="CHLdev/2" Version="7 - 9"
- Name="QuarkXPress Project" PUID="CHLdev/3" Version="9.1 - 15"

### Single Versions Signature
- Based on offsets from LIBQXP, notes here: http://fileformats.archiveteam.org/wiki/QuarkXPress

Decision was made to leave off the first two bytes of files, "0000" as samples were found with "FF" as first byte but QuarkXPress had no problems opening file.

Aditional samples were tested from:
- https://github.com/qxpjs/GettingStarted/
- https://www.online-convert.com/file-format/qxp
- https://github.com/yginieys/quark

Current version of these signatures leave out QuarkXPress Book (.QXB), Library (.QXL) & Article (.QCD) formats. 
