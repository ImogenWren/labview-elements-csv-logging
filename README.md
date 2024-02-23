# labview-elements-csv-logging
Example for robust and configurable UI for datalogging to CSV file
- 4 seperate VIs
  - Logfile Build Filepath - Name log file
  - Logfile CSV Data Headings - Open/Create File & Write column headings
  - Logfile Log CSV - Transform data array into timestamped datetime and log to open file
  - Close File - Standard LV Option


## Working Example
### Block Diagram
![image](https://github.com/ImogenWren/labview-elements-csv-logging/assets/97303986/56b313b9-5057-4dd9-8b45-bba411ff2722)
Each module has several configurable options to make this approach flexible enough to use in all kinds of projects. Individual modules (Vis) are detailed below

## Logfile Path Builder
_Allows the user to select a filepath for the log file, either manually or by selecting a folder relative to the application, or VI directory-
#### Example Implementation
![image](https://github.com/ImogenWren/labview-elements-csv-logging/assets/97303986/652bb8cf-c8bd-4f9e-91aa-6140913db58d)

### Front Panel
![image](https://github.com/ImogenWren/labview-elements-csv-logging/assets/97303986/f6ba3fd9-2eb8-428a-8ed1-a294d38cb7da)
#### Usage:
1. Select _Log Filepath Source_ Options:
  - Application Relative (Auto)
    - Log file is created in named directory in folder containing application (project or .exe)
  - VI Relative (Auto)
    - Log file is created  in named directory in folder containing sub VI
  - Complete Path (Manual)
    - Log file path and name is selected using the manual selection dialog box
      
2. If (Auto) option selecte4d User enters _Log File Folder Name_ and _Log File Name_
   
3. Select Data/Time string options to prefix filename
  - Note, these options will still update manually selected filepath, Untick all options to save the file without datetime prefixes.

### Block Diagram
![image](https://github.com/ImogenWren/labview-elements-csv-logging/assets/97303986/d397a056-8b90-4f4c-882b-c0eaa86f9804)


