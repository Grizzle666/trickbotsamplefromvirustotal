# trickbotsamplefromvirustotal
trickbotsamples gotten from virsustotal
https://blog.didierstevens.com/didier-stevens-suite/

Bulk File Hash Check with VirusTotal – Didier Stevens script
June 14, 2021 / Security / Forensics, Free Software, Guide, VirusTotal / Leave a Comment
Bulk File Hash Check with VirusTotal – Why Didier Stevens script
If you have a list of hashes, you can bulk file hash check with VirusTotal. You will need the VirusTotal API key. There are many tools available, but if you want to use a tool that is going to ingest API key from your account – make sure it is from reputable source. Didier Stevens is a reputable part of security community and “SANS.org” – we will cover his script.

Currently there are several official sources for the script, so you will know where to find it:
Official Didier Stevens Blog page for virustotal-search.py 1.1.4 – based on Python 2.
Official Didier Stevens Blog page for virustotal-search.py 1.1.5 – based on Python 2.
Latest Beta version on GitHub for virustotal-search.py 1.1.6 – based on Python 3. This is current Beta page, currently there is v1.1.6, but could be later version.

How to install Didier Stevens “virustotal-search.py” script
1. Download latest version of Python 3
2. Install it – check usage for PATH environment variable and for easier future updates install to the root of your C: drive. Example for Python 3.9.5:

C:\Python39\
3. Navigate to Didier Stevens virustotal-search.py Github page
4. On top of the page Right Click the [Raw] button and [Save link as]. Save the file in the place that you will find it later, for example:

C:\tools\Didier Stevens\virustotal-search\virustotal-search-1.1.6.py
5. Sign up for VirusTotal for free.
6. After you login to VT, click your profile button, then [API Key]. Copy this API key so you can use it later, maybe save to text file.
* Free VirusTotal Public API key can be used for 4 hash requests per minute and 500 hashes per day. Same goes for the script itself, it will not send more than 4 requests per minute. It was scripted that way and if you have a premium account with bigger quota, the script will still send 4 requests per minute. Keep that in mind. After your reach your daily quota of 500 requests with free account – VT will send you an email and the script will fail to send new requests until the next day.

How to use Didier Stevens “virustotal-search.py” script to bulk file hash check with VirusTotal
* This guide is for virustotal-search.py script version 1.1.6 and above, which uses python 3. If you want to use older versions for python 2 you will need also to install “poster” package with command: pip install poster.

1. Save all your file hashes to text file, example path:

C:\tools\Didier Stevens\virustotal-search\List.txt
2. Command line usage example:

virustotal-search-1.1.6.py List.txt -k <YourAPIKey> -s , -o Out.csv
Example with full paths from above:

"C:\tools\Didier Stevens\virustotal-search\virustotal-search-1.1.6.py" "C:\tools\Didier Stevens\virustotal-search\List.txt" -k <YourAPIKey> -s , -o "C:\tools\Didier Stevens\virustotal-search\Out.csv"
Command line Example if you did not select PATH variable usage and need to specify path to “python.exe”:

"C:\Python39\python.exe" "C:\tools\Didier Stevens\virustotal-search\virustotal-search-1.1.6.py" "C:\tools\Didier Stevens\virustotal-search\List.txt" -k <YourAPIKey> -s , -o "C:\tools\Didier Stevens\virustotal-search\Out.csv"
virustotal-search switches explanation
List.txt: The second argument for the script. Is any text file that holds the hash list.
-k: API key.
-s ,: Separator character between the columns. “,” (comma) is the character that is used in this case for regular CSV (comma separated values) document. The default setting without the “-s” switch is “;” (semicolon).
-o: Output csv file.

For help and more settings / switches you can use the -h switch.

Related Posts:
Extract VBA Macro from Microsoft Word and Excel - oledump
SysInternals Sigcheck VirusTotal Offline Scan on a Computer
CMTrace SCCM LOG viewer – Download, Install, Usage
Basis Technology Autopsy and Plugins Installation Guide
Basis Technology Autopsy Usage Guide - Analyzing Source
Basis Technology Autopsy Ingestion Modules Configuration
