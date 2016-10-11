# FAQ

## Part 0, Install R Essentials
###1. Modeler version
	New extension (mpe file) development base on Modeler 18.0, so TWC extension need Modeler 18.0 and high.
###2. R
	Modeler 18.0 support R 3.2.*
###3. Modeler R Essentials
	Download essentials from 
	https://developer.ibm.com/predictiveanalytics/downloads/
	https://github.com/IBMPredictiveAnalytics/R_Essentials_Modeler/releases?cm_mc_uid=17252922416314720076874&cm_mc_sid_50200000=1476166117

##Part 1, Installation
###1. Where can I found latest extension?
	https://github.com/IBMPredictiveAnalytics?utf8=%E2%9C%93&query=twco
###2. How to install latest extension?
	Currently, TWC extensions can't support auto install from extension Hub. 
	Please download *.mpe and install it from "Extensions -> Install Local Extension Bundle..."
###3. Where can I found installed extension?
	You can found installed extension in "Record Ops" tab
###4. How to uninstall extension?
	From "Extensions -> Extension Hub" dialogue, in "Installed" tab, 
	select extension you want uninstall and click "OK".
###5. How to manually remove installed extension?
	Sometimes, old TWC extension can't cleanup with uninstall process. 
	Please remove it manually and restart Modeler.
	Win:
		C:\ProgramData\IBM\SPSS\Modeler\18.0\CDB
	Mac:
		/users/modelerqa/Library/Application Support/IBM/SPSS/Modeler/18/CDB/
###6. After extension installed, why example/shared stream node always gray?
	Please close stream and reopen it. 
	If doesn't work, should be a extension version conflict(stream required extension version VS installed extension version). 
	Please fetch latest extension from #1 link or confirm with stream owner for correct version.

##Part 2, Configuration
###1. Where can I get TWC API key
	Send an email to ibmwx@us.ibm.com requesting a Demo / Trial API key for The Weather Company extensions in SPSS.

###2. Different between TWC API key and TWC cleaned historical API key
	You will receive two API keys for using The Weather Company's extensions within SPSS.
	The Gridded Historical extension requires a unique API key. The remaining extensions for pulling TWCo weather data will use a separate unique API key. Both API keys can be acquired through the email address listed above.

##Part 3, Trouble shoots
###1. What can I do when face "data and datamodel does not match"
	It's very common extension error, because extension didn't have a message throw out pipeline. 
	But extension has printed all necessary error logs to "console output".
	When face this error, please double click extension node, select "Console Output".

###2. How to analysis output log
	There is two log in console output log, one is extension code, and another one is execute log. 
	Those two part are divide by "*************".
	Please take a look log part.
	
###3. Error like "Error in FUN(newX[, i], ...) : could not find function "content""
	R function didn't found, extension required r package install failed.
	Please try re-install r package manually in r console, TWC extension need "plyr","httr". 
	
###4. Error like "cannot open URL"
	Copy URL link in console output, and open it in browser to see what happened. 
	
###5. Error like "invalid apikey"
	You API key can't apply to this special TWC API, please sent this link to Matthew, Chris. To upgrade your api key.
	
##Part 4, TWC API know issues

	
