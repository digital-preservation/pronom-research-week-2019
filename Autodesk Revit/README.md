# Autodesk Revit documents

- Format Name: Autodesk Revit Project or Family file
- Versions: 4, 2008, 2010, 2019
- PUID:
- x-fmt/443	Revit Family File rfa
- x-fmt/444	Revit Family Template rft
- x-fmt/445	Revit Template rte
- x-fmt/447	Revit Project rvt
- Extensions: RVT, RTE, RFA, RFT
- MIME: Unknown
- Description: Autodesk Revit is 3D modeling software used by architects, engineers, plumbers, etc. RTE (template) files and RVT (project) files are actual Revit projects. RFA (family) files and RFT (family template) files are family files that can either be loaded into a project or saved externally.
- Format Type: Model
- Vendor: Autodesk
 
# Format Details

- CHLdev/10 Container format to catch older versions of all Revit formats
- CHLdev/20 Container format to catch RVT & RTE formats with changes made in 2008 to include "BasicFileInfo" signature
- CHLdev/21 Container format to catch RFA & RFT formats with changes made in 2010 to include "PartAtom" XML signature
- CHLdev/22 Container format to catch RFA & RFT formats with changes made in 2008 but missing "PartAtom" XML signature
- CHLdev/30 Container format to catch RVT & RTE formats with changes made in 2019 changing syntax in "BasicFileInfo" signature
- CHLdev/31 Container format to catch RFA & RFT formats with changes made in 2019 changing syntax in "BasicFileInfo" signature

Note, most Revit files newer than 2008 have thumbnail file "RevitPreview4.0" which seems a great identifying file, but I found many samples which didn't have this file, which probably means a thumbnail wasn't generated for the file.

