splashid2kepass
===============

convert from SplashID Safe to KeePass Password Safe

Installation
------------

stdlib's csv module does not support Unicode, so use unicodecsv from Jeremy Dunck

    git clone https://github.com/jdunck/python-unicodecsv.git
    cd python-unicodecsv
    sudo python setup.py install

Usage
-----

in SplashID for Mac :

- File / Export / CSV
- name your output file export_csv.csv
- select "all records"
- save
- mail : no

    python ./splashid_to_keepass.py -i export_csv.csv -o import.csv

open KeePass 2.x on Windows

- File / Import / Generic CSV Importer
- select import.csv
- choose the text encoding and check the preview
- in the structure tab, select
    - comma as field separator
    - " as text qualifier
    - new line as record separator
    - ignore 1st row
- in the semantic field list, define the following fields to match import.csv
    - Title
    - User Name
    - Password
    - URL
    - last mod time : yyyy'-'MM'-'dd'T'HH':'mm';'ss'
    - Notes
    - Group
- check the preview to see if the import would work as expected
- go for it

Before deleting your old SplashID database, be sure that all the records imported fine. At end of process, delete all your temporary export and import files from your disk.

bueche@netnea.com, 23.9.2013

