#  Data Derivation
## Casco Bay "Integrated Report" Shapefile
The shapefile `ADB_2016_Casco_Bay` was derived from the source GIS data
in ArcGIS, by using "Select By Location" to extract stream reaches
in the Casco Bay watershed.

## CSV Files
The CSV file, `impaired_list.csv` includes all waters included in the 2016
Integrated Report located within the Casco Bay watershed.  It was derived by
exporting the attribute table of `ADB_2016_Casco_Bay`, and editing by hand to
remove uninformative identifiers.  Note that this list includes waters 
"presumed" to be in attainment of water quality standards, but for which
adequate data is not available (Categories 2 and 3).

The CSV file `impaired_list_4_5_only.csv` was created from `impaired_list.csv`
by hand-editing, by Curtis C. Bohlen.  THe file's primary purpose was to
enable data on causes of water quality impairment to be imported into GIS.
Data was copied by hand from the tabular data in DEP's 2016 Integrated Report
Lists.  Data copied included:

*  Segment_Size_miles
*  Location  (Usually as "tributary to...")
*  Class     (Official stream class)
*  Cause     (Cause(s) of impairment)

We added a "Comments" field that points out when streams fall in both
EPA Categories 4 and 5.

Finally, we added Indicator variables for five causes of impairment:
*  E_coli  (*Escherichia coli*, a bacterial indicator of pathogens)  
*  DO      (Dissolved oxygen)
*  Benth_Inverts (Benthic invertebrate community assessments)
*  Habitat       (Stream habitat assessments)
*  Periphyton    (Assessment of periphyton community composition)

Of those, Benthic Invertebrates, Habitat, and Periphyton have fairly high 
concordance, as do Dissolved oxygen and E coli.

## Impaired Waters Shapefile
The shapefile `CB_Impaired` was created by joining `ADB_2016_Casco_Bay` to 
`impaired_list_4_5_only.csv`, based on the "ADB_ID" field, exporting to the new
shapefile, and removing uninformative identifiers.

# Additional Notes
Maine uses the following categories in classifying streams for the Integrated
Report:

*  Category 1: Rivers and Streams Fully Attaining All Designated Uses  
*  Category 2: Rivers and Streams Attaining Some Designated Uses - Insufficient
  Information for Other Uses  
*  Category 3: Rivers and Streams with Insufficient Data or Information to
   Determine if Designated Uses are Attained (One or More Uses may be Impaired)  
*  Category 4-A: Rivers and Streams with Impaired Use, TMDL Completed  
*  Category 4-B: Rivers and Streams Impaired by Pollutants - Pollution Control
   Requirements Reasonably Expected to Result in Attainment   
*  Category 4-C: Rivers and Streams with Impairment not Caused by a Pollutant  
*  Category 5-A: Rivers and Streams Impaired by Pollutants Other Than Those
   Listed in 5-B Through 5-D (TMDL Required)  
*  Category 5-B: Rivers and Streams Impaired for Bacteria Only, TMDL Required  
*  Category 5-C: Waters Impaired by Atmospheric Deposition of Mercury  
*  Category 5-D: Rivers and Streams Impaired by Legacy Pollutants  

Categories 2 and 3 sometimes have related text suggesting these waters are, in
the absence of data to the contrary, "presumed"" to meet all designated uses.
For purposes of SoCB, we will focus on categories 4 and 5, where we have data
showing that streams are not meeting all water quality requirements.

