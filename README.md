# pymeta
pymeta is a Python3 rewrite of the tool PowerMeta, created by dafthack in PowerShell. It uses specifically crafted search queries to identify and download the following files (pdf, xls, xlsx, doc, docx, ppt, pptx) from a particular domain using Google and Bing. Once downloaded, metadata is extracted from these files using Phil Harvey's exiftool. This is a common place for penetration testers to find internal domain names, usernames, naming conventions, and software/version numbers.

Pymeta can also be pointed at a directory to extract metadata from files manually downloaded using the '-dir' command line argument. See the 'Usage', and 'All Options' sections for more information. 

During metadata extraction, unique 'Author', 'Creator', and 'Producer' fields will be written to the terminal. However, more verbose output can be accomplished by generating a csv report with the '-csv' command line argument. 

*pymeta is written in python3, use the setup.sh script to ensure all required libraries are installed.*

## Getting Started
In the Linux terminal run:
1. git clone https://github.com/m8r0wn/pymeta
2. sudo chmod +x pymeta/setup.sh
3. sudo ./pymeta/setup.sh

## Usage
* Search Google and Bing for files within example.com and extract metadata to terminal<br>
`python3 enumdb.py -d example.com`

* Search Google only for files within example.com and extract metadata to a csv report<br>
`python3 enumdb.py -d example.com -s google -csv`

* Extract metadata from files within the given directory and create csv report<br>
`python3 enumdb.py -dir ../Downloads/ -csv`


## All Options
    -h, --help      show help message and exit
    -d DOMAIN       Target domain
    -dir FILE_DIR   Directory of files to extract Metadata
    -s ENGINE       Search engine to use: google, bing, all (Default: all)
    -m MAX_RESULTS  Max results to collect per file type (Default: 50)
    -csv            write all metadata to CSV (Default: display in terminal)
    
## Credit
- Beau Bullock [(@dafthack)](https://twitter.com/dafthack) - [https://github.com/dafthack/PowerMeta](https://github.com/dafthack/PowerMeta)
- Phil Harvey - [https://sno.phy.queensu.ca/~phil/exiftool/](https://sno.phy.queensu.ca/~phil/exiftool/)