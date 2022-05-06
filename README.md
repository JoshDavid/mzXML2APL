# mzXML2APL
## Mass Spectrometry Data Reader

This is a lightweight, mzXML file reader. 

Simply use the *ReadFile* function against a path to an mzXML file.

```
	r ← ReadFile 'C:/Data/file.mzXML'
``` 
The result contains 2 items:

1. Info
    * This is a namespace containing information about the run. Expect info such as startTime, endTime, scanCount, etc.
2. Scans
    * This is an array of namespaces containing each scan in the file. Each scan namespace will have information about the scan (byteOrder, pairOrder, precision, etc.) The most important variable, is the peaks variable. This will contain the peaks data from the scan, decoded into a regular numeric 2-D array of 2 columns, containing the m/z-int pairs

Currently in Beta, tested against schema's 2.0 and 2.1. 

Designed to not be as strict as contemporary libraries. MATLAB's mzxml library tends to fail on several mzXML files, this will try to ingest data liberally. 

