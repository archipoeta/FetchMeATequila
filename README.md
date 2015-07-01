# FetchMeATequila

## Description

This script should be run on new or existing Tequila mirrors, to keep them up to date.
Parses a fresh copy of Tequila's manifest.xml, uses random mirrors and compares sizes and hashes:
Only downloads if files differ. :)

## Installing

It uses perl's XML::Simple, which requires libexpat.  
On a 64 bit debian based system you may need to install the packages like so:

    # apt-get install lib64expat1 libxml-sax-expat-perl
    # cpan -i XML::Simple

## Usage

    Usage: fetchmeatequila [OPTIONS]
        [OPTIONS]
        -f FILE_URL    (Optional) Web path to a FILE in the format of Tequila's manifest.xml
                       Defaults to: http://dl.dropboxusercontent.com/u/37952257/Tequila/manifest.xml

        -d PATH        (Optional) Destination directory of downloaded files.
                       Defaults to: CWD

        --verbose      Slightly more verbose, without this the script tries to stay greppable.
        --help         This menu.

## Examples
A Normal Example:  
    # fetchmeatequila -d /www/sites/mirror2.yourdomain.net/files/html/icon
Using a custom manifest, (uncommon):  
    # fetchmeatequila -f http://some-other.tequila.url/manifest.xml -d /var/www/html/icon -v
