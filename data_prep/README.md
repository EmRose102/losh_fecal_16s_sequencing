## Download data from Illumina

- https://login.illumina.com/platform-services-manager/?rURL=https://basespace.illumina.com&clientId=basespace&clientVars=aHR0cHM6Ly9iYXNlc3BhY2UuaWxsdW1pbmEuY29tLw&redirectMethod=GET#/
- Go to Projects tab
- Click circular file button and choose  Download  Project from drop down
- Data will contain zipped FASTQ files with two copies of data from different dates
      - One is QC run that the lab ran to ensure each sample has about the same number of reads, testing how much sample to use
      - QC run data files should be smaller than full run and are likely the earlier date
      - Both runs will be processed and combined to get total microbially diversity for each sample
-	Two copies of data within each sample file
      - Labelled R1 (forward read) and R2 (reverse read)
 
Data Info

LOSH 16S 2022 microbiome data
-	Two data sets, run 1 from 2022-5-11 and run 2 from 2022-5-20
-	Second run (from 2022-5-20) should be real run and run 1 should be QC run, even though some files seemed bigger for the first run
-	First run did not include control 2 for some reason?

## Create a manifest file for each data set

- Columns
  1) sample name
  2) absolute file name (can put placeholder until files are moved to final folder)
  3) Run (run 1 - qc vs run 2 – full sample run)
- Create in Excel and save as a tab-delimited file, .tsv for Linux or .txt for Windows?
    - Can use .txt and upload to server from labtop through Cyberduck, works just fine
    - To convert to .tsv, save as .xls file and use online converter
- Google Chrome extension that can help check format of manifest file

- Retrieving absolute file paths and rename folders in Windows Command prompt:

Example for RUN 1 of LOSH microbiome 16S sequencing data

Open window command script

#set working directory to project file locations

cd/Users/emily/Desktop/edonahue_losh16S_formatted/20220511_LOSH_16S/raw_data
#command to list all full (absolute) file path names for every file in set folder (working directory)
dir /S /B
#command >ren< is used to rename folder/file names
ren Emily001_EN01_L001-ds.0f52fa30365242789e09eeee8ae32e0b Emily001_EN01_S77
ren Emily002_EN02_L001-ds.56c270078ca6438baef8443673b5be79 Emily002_EN02_S78


