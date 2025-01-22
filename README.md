Template repository for public data cleaning. Use this to start a new project to ensure the organization remains consistent across data sets.

# Data Set Name 
This is a short*ish* description of the data set. Include relevant information like years covered.

### Source

Provide information someone could use to reproduce the data pull in the future. Include where the data came from and the date the data were accessed in the table below. List out individual files where possible; if too cumbersome indicate groups of similarly named files. 


Data were downloaded from: `typically a url`


| File(s)           |   Date Accessed (YYYY-MM-DD)  | 
| :----             | :--------------------------:  | 
| PQI_07.pdf        |           2024-01-01          | 
| 2017_census/*     |           2024-01-18          | 


### Final Files
Provide a list and information on the final derived products. 

| File(s)                     |          Description          | 
| :----                       | :--------------------------:  | 
| PQI\_07\_valueset.parquet   | Avoidable Hospitilzation Hypertension Codes | 
| PQI\_08\_valueset.parquet   | Avoidable Hospitilzation Heart Failure Codes | 


### Data Processing
Document the steps involved in going from `raw/` to `final/`. 

Ideally, the data can be processed without any manual steps, but in cases where those are necessary this should be explicitly called out. If file names need to be modified (after downloading) explicitly call that out here. If someone needs to refresh a data pull or ingest another file related to the data set it should be clear how to do so. 

For example: 

1. Download technical specification .pdf files to `raw/` and manually append the year to file names. (e.g., PQI\_07\_2024.pdf)
2. Use `process_pdf_files(file_name)` method in `code/extract_valueset.py` with the filename in step 1 above. 
3. Edit `__main__.py` within `code/pipeline.py` to include `process_pdf_files(file_name)` so this step is documented. 


If parts of the processing are sufficiently manual or complicated then you can also create a walkthrough using a jupyter notebook or any equivalent which can be linked in this ReadMe.