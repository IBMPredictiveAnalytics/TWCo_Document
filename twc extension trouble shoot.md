# FAQ

## Part 0, Install R Essentials
###1. Modeler version
	New extension (mpe file) development is based on Modeler 18.0, so TWC extensions need Modeler 18.0 and higher.
###2. R
	Modeler 18.0 supports R version 3.2.0
###3. Modeler R Essentials
	Download essentials from 
	https://developer.ibm.com/predictiveanalytics/downloads/
	or
	https://github.com/IBMPredictiveAnalytics/R_Essentials_Modeler/releases?cm_mc_uid=17252922416314720076874&cm_mc_sid_50200000=1476166117

##Part 1, Installation
###1. Where can I find and download the latest extension version?
	https://github.com/IBMPredictiveAnalytics?utf8=%E2%9C%93&query=twco
###2. How to install the latest extensions?
	Download from the Extension Hub within SPSS Modeler.
	OR
	Please download *.mpe and install it from "Extensions -> Install Local Extension Bundle..."
###3. Where can I find installed extension?
	You can find installed TWCo extensions in the "Record Ops" tab
###4. How do I uninstall an extension?
	From "Extensions -> Extension Hub" dialogue, in "Installed" tab, 
	select the extension you want uninstall and click "OK".
###5. How to do I manually remove an installed extension?
	Sometimes, old TWC extensions can't be fully removed with the uninstall process. 
	In this case, please remove the extension folder(same as extension name) manually and restart Modeler.
	Win:
		C:\ProgramData\IBM\SPSS\Modeler\18.0\CDB
	Mac:
		/users/modelerqa/Library/Application Support/IBM/SPSS/Modeler/18/CDB/
###6. After an extension is installed, why are example/shared stream nodes appearing grayed out?
	Please close stream and reopen it. 
	If this doesn't work, should be a extension version conflict (stream required extension version VS installed extension version). 
	Please fetch the latest extension from #1 link or confirm with stream owner for correct version.

##Part 2, Configuration
###1. Where can I get a 30 day free trial API key for use with TWCo extensions?
	Send an email to ibmwx@us.ibm.com requesting a Demo / Trial API key for The Weather Company extensions in SPSS.
	Please include your name, role at your organization, and intended industry focus or use case with weather data.

###2. What is the difference between the general TWC API key and the TWC Gridded Historical API key that I received or will receive?
	You will receive two API keys for using The Weather Company's extensions within SPSS.
	
	The Weather Company Gridded Historical extension requires a single unique API key. 
	The remaining extensions for pulling TWCo weather data will use a separate unique API key. 
	
	Both API keys can be acquired through the email address listed above.

###3. How does my input file need to be configured to pull weather data correctly?
	Use .CSV input file format.
	Column headers must not have spaces included.
	Latitude and Longitude (if using Lat/Lon for location basis) need to be listed in separate columns.
	Latitude and Longitude could be expressed in decimal/string format. 
        Sometimes Modeler add unnecessary space for decimal format(can be check follow Part3 instruction for url link), 
        try string format for Lat/Lon.
	Postal Code format varies per TWCo Extension, please reference the specific extension's configuration for an example of the correct postal code format.

###4. Data format
	Most TWC extensions use YYYYMMDD (20161012) as the date format. Please ensure your input file is formatted correctly.

##Part 3, Troubleshooting
###1. What can I do when face "data and datamodel does not match"
	It's very common extension error, because extension didn't have a message throw out pipeline. 
	But extension has printed all necessary error logs to "console output".
	When face this error, please double click extension node, select "Console Output".

###2. How to analyze the console output log
	There are two logs in the console output log, one is the extension code, and the other part is the execute log. 
	Those two parts are divide by "*************".
	Please take a look at the log part.
	
###3. Error like "Error in FUN(newX[, i], ...) : could not find function "content""
	R function didn't found, extension required r package install failed.
	Please try re-installing r package manually in r console, TWC extension need "plyr","httr". 
	
###4. Error like "cannot open URL"
	Copy URL link in console output, and open it in browser to see what happened. 
	
###5. Error like "invalid apikey"
	You API key can't apply to this special TWC API, please send this error and link to ibmwx@us.ibm.com 
	to have your API key upgraded to include the appropriate dataset.

###6. Error like "cannot open URL" for Historical Gridded extension
	Generally, TWC Gridded Historical API key provider 
        10,000 calls/month (1 call = 7 days of historical data for 1 location). 
        Becareful that it's easy to exceed limitation if require long time range.

##Part 4, TWC extensino/API known issues
###1. Icon of node didn't show in Modeler
	It's known Modeler 18 extension, and will be fix in next Modeler release
###2. In extension dialouge, "Lon" label(under "Lat" variable selection box) didn't show.
	It's known Modeler 18 extension, and will be fix in next Modeler release
###3. In extension dialouge, "End Date" label(under "Start Date" variable selection box) didn't show.
	It's known Modeler 18 extension, and will be fix in next Modeler release	
