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

## Create a manifest file for each data set

- Columns
  1) sample name
  2) absolute file name (can put placeholder until files are moved to final folder)
  3) Run (run 1 - qc vs run 2 – full sample run)
- Create in Excel and save as a tab-delimited file, .tsv for Linux or .txt for Windows?
    - Can use .txt and upload to server from labtop through Cyberduck, works just fine
    - To convert to .tsv, save as .xls file and use online converter
- Google Chrome extension that can help check format of manifest file

