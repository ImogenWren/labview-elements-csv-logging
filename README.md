# labview-elements-csv-logging
Example for robust and configurable UI for datalogging to CSV file
- 4 seperate VIs
  - Logfile Build Filepath - Name log file
  - Logfile CSV Data Headings - Open/Create File & Write column headings
  - Logfile Log CSV - Transform data array into timestamped datetime and log to open file
  - Close File - Standard LV sub VI


## Working Example
### Block Diagram
![image](https://github.com/ImogenWren/labview-elements-csv-logging/assets/97303986/56b313b9-5057-4dd9-8b45-bba411ff2722)
Each module has several configurable options to make this approach flexible enough to use in all kinds of projects. Individual modules (Vis) are detailed below

## Logfile Path Builder
_Allows the user to select a filepath for the log file, either manually or by selecting a folder relative to the application, or VI directory_
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

### Icon & IOs
![image](https://github.com/ImogenWren/labview-elements-csv-logging/assets/97303986/05cb285f-cd95-4ab5-a8ca-da760909ee67)

### Block Diagram
![image](https://github.com/ImogenWren/labview-elements-csv-logging/assets/97303986/d397a056-8b90-4f4c-882b-c0eaa86f9804)


## Logfile CSV Data Headings
_Opens CSV file create in previous step & Applies data labels to column headings_
#### Example Implementation
![image](https://github.com/ImogenWren/labview-elements-csv-logging/assets/97303986/4ae99e73-ad86-4aef-8411-8cdca51756b8)

### Front Panel
![image](https://github.com/ImogenWren/labview-elements-csv-logging/assets/97303986/0a94c34d-bf80-4330-b597-1b0f55f7cdc0)
#### Usage
1. Pass string with comma seperated values for column headings eg:
  - `timestamp, data1, data2, data3, data4`
2. (Optional) pass bool to _keep file open?_ input, default (true)
  - Note: If file remains open use bitstream for following modules, if file is closed pass Log File Path as reference. Best implementation depends on use case.

### Block Diagram
![image](https://github.com/ImogenWren/labview-elements-csv-logging/assets/97303986/2eb698e0-a555-4975-bb3f-06c21713b07a)


## Logfile Log CSV
_Takes data array as input and logs to CSV file, optional configurable timestamp as 1st data column_
#### Example Implementation
![image](https://github.com/ImogenWren/labview-elements-csv-logging/assets/97303986/55224fee-0fe4-4c75-865a-657b34249076)

#### Usage
1. Select timestamp options, Note: Including Milliseconds will prevent excel from displaying times correctly. If milliseconds resolution is required, reccommend parsing with python or other data processing scripts, rather than excel.

### Block Diagram
![image](https://github.com/ImogenWren/labview-elements-csv-logging/assets/97303986/338c314e-5a6d-48ab-a560-8eefd390a2fb)

