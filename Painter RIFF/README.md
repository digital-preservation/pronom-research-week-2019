# Painter RIFF image file

Format Name: Painter RIFF image file
Versions: All
PUID:  x-fmt/187
Extension: RIF
MIME: Unknown
Description: Native image file to Painter software, maintians layers, transparency, etc. Developed by Fractal Design in early 1990's, now owned and used by Corel Corp.
Format Type: Image (Raster)
Vendor: Corel Corporation

The Painter RIFF format is similar enough throughout versions 1.2 (1991) through current 2020 version. Identified by the first 4 bytes, then bytes 8-12 which defines compression, then a static 4 bytes used in all versions at byte 40 "3F E6 66 66". 

This signature is a single signature for all versions, but can be split into two versions. This can be done by having the early versions identify the first 4 bytes "00 02 00 00" and the later Corel versions (2000+) with first 4 bytes "00 02 20 00".
