# Converting LOC-AFC provided MARC records to Mukurtu Core CSV 

This workflow requires at least three programs: 
- MarcEdit: https://marcedit.reeset.net/downloads 
- A basic text editor. Eg: Notepad, Notepad++, TextEdit, Atom
- A spreadsheet editor of your choice that properly supports UTF-8 encoded CSV files. We recommend something other than Microsoft Excel – see more information here: https://mukurtu.org/support/file-formats-character-encoding-and-spreadsheet-tools/  

## Convert MARC XML records to MARC 
- Not required if your records are already in .mrc format.
- https://www.youtube.com/watch?v=nt2RChF_hgQ

## Join multiple MARC records 
- Not required if your records are already all combined in one .mrc file.
- https://www.youtube.com/watch?v=wOIL435CxMI

## Generate a field count report 
- Not required if you already know which fields you will be mapping from MARC to Mukurtu Core. If you are not sure which fields you will be using, or otherwise want a complete listing of every field used in the MARC records, this is a useful step.
- Tools > Generate Reports > Field Count Report
     ![MarcEdit - Generate field count report](https://github.com/WSU-CDSC/MMTT/blob/7acf1d93872697b5ca65448c145897fa4e7f2f06/MARC%20%3E%20Mukurtu%20Core/Workflow%20Images/Screen%20Shot%202022-06-30%20at%202.03.53%20PM.png)
- A .txt file will be exported. See [sample field count report.txt](https://github.com/WSU-CDSC/MMTT/blob/c79d8f6973352c9774d57f31b3fc7d419d089748/MARC%20%3E%20Mukurtu%20Core/sample%20field%20count%20report.txt) for an example.

## Create a field settings list 
- If this is your first time working with MARC records from a particular repository, collection, or other source, we recommend including every field from the field count report so that none are missed. Unneeded fields can be easily removed from a Mukurtu Core spreadsheet before import.
- This can be done manually by inputting fields one by one into the MarcEdit interface (which can then be saved for future use). Alternatively you can format a .txt field and load itinto MarcEdit to save time manually inputting.
- The field record count generated earlier can be easily duplicated and formatted in a text editor to serve as a field settings list.
- If a field has multiple subfields but only some of them are required, you can include subfields to specify which subfields to include. If you do not include subfields, all subfields will be included.
- See [sample field settings 01.txt]([sample field settings 01.txt](https://github.com/WSU-CDSC/MMTT/blob/c79d8f6973352c9774d57f31b3fc7d419d089748/MARC%20%3E%20Mukurtu%20Core/sample%20field%20settings%2001.txt)) for an example with subfields and [sample field settings 02.txt]([MARC > Mukurtu Core/sample field settings 02.txt](https://github.com/WSU-CDSC/MMTT/blob/c79d8f6973352c9774d57f31b3fc7d419d089748/MARC%20%3E%20Mukurtu%20Core/sample%20field%20settings%2002.txt)) for an example without subfields.

## Export MARC to tab-delimited records 
- https://www.youtube.com/watch?v=qkzJmNOvY00
- Load the field settings list generated earlier.
- Ensure that *Delimiter* is set to comma (,) and *In-Field Delimiter* is set to semicolon (;)
     ![Tab-delimited export settings](https://github.com/WSU-CDSC/MMTT/blob/262964aa6488e6b1d5df0f8d83f22c6435417b0e/MARC%20%3E%20Mukurtu%20Core/Workflow%20Images/Screen%20Shot%202022-06-30%20at%202.07.46%20PM.png)

## Align MARC fields with Mukurtu Core
- Mukurtu requires that all field names match those specified in the importer.
  - https://mukurtu.org/support/digital-heritage-metadata-fields-2-1/  
- For fields with an obvious one-to-one match, replace the column header with the correct Mukurtu Core field name. 
  - Eg: 245 usually maps closely to Title.
- Additional manual processing may be required, depending on how closely the MARC fields align with Mukurtu Core. This generally needs to be assessed on a case by case basis. Examples include:
  - Determining title and summary.
  - Extracting dates, location descriptions, and other granular fields from more general notes fields.
  - Calculating location data for map use.
  - Correctly identifying creators and contributors.

## Include remaining required fields for Mukurtu import 
- The following fields must be included for a successful Mukurtu import.
  - See https://mukurtu.org/support/digital-heritage-metadata-fields-for-roundtrip/ for more detail.
- GUID (for new items) or NID (to update existing items): 
- Title: Likely mapped from MARC (either as is, or edited as needed).
- Community: Likely inferred from the metadata. Requires spopecific formatting.
- Protocol: 
- Item Sharing Settings: 
- Category: 
- Username: Username of the user importing the digital heritage item(s).

## Format fields for Mukurtu import 
- Certain fields require specfific formatting or values for successful import.
  - See https://mukurtu.org/support/digital-heritage-metadata-fields-2-1/ for more detail.
- Plain text 
- Multi-value taxonomy 
- Rich text 
- NID 
- SID 
- URL 
- Date 
- Location 
- Other? 
