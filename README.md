# Bootstrap.dat


**bootstrap.dat** allows a new LitecoinZ client (not synced) to rapidly import the initial blocks from a local file instead of slowly downloading blocks from random peers. This significantly reduces the time it takes to get a client synced with the current blockchain.

Simply having bootstrap.dat in LitecoinZ's expected data directory will make your initial block sync much faster. The import process can be even faster if you use the -dbcache=1000 command line parameter which uses an additional 1GB of RAM for the database index cache. LitecoinZ v2.0.1+ with ZHash PoW validation can make import even faster if you have SSD drives.

## Overview
Regardless of your operating system use the following steps to make use of the bootstrap.dat file:

1. Download bootstrap.dat.xz from github.
2. Verify the integrity of bootstrap.dat.xz with the checksums.
3. Decompress to obtain bootstrap.dat.
4. Put it into the LitecoinZ datadir.  This is the same folder that contains wallet.dat and the blocks folder.
5. Delete bootstrap.dat.old if you want to recover some storage space.

## Download bootstrap.dat
You can download bootstrap.dat from the following locations:

**github.com**
[bootstrap.dat.xz](https://github.com/litecoinz-project/blockchain/releases/download/v0.0.2/bootstrap.dat.xz)

## Verify integrity
- CRC-32: d649262d
- MD4: bd929356a2cb73b6b9efce96d9ec5d23
- MD5: cf2d161821efa604e746e0dfef8f2391
- SHA-1: 8bfab505c45b01dd05a8388386fa255d0ed75242
- SHA-256: a1e3c074041946e8a4fb1ad254fb1f05f0716691842e098e45f30e78887275be

## Extract bootstrap.dat
**Linux**: ```xz -d bootstrap.dat.xz```

**Mac**: You can obtain xz from MacPorts or [http://macpkg.sourceforge.net/](http://macpkg.sourceforge.net/).

**Windows**: [7Zip](http://www.7-zip.org/) is a free utility that can decompress .xz files. The latest version of [WinRAR](http://www.rarlabs.com/download.htm) also supports .xz files.

## Copy bootstrap.dat to data directory
Copy **bootstrap.dat** to your data directory. After LitecoinZ has used bootstrap.dat, the file will be renamed to bootstrap.dat.old; at this point you can choose to delete it or keep it.

**Linux**: LitecoinZ's data directory is located in ```~/.litecoinz/``` by default. You can run ```ls -a``` to see directories that start with a dot.
You can also search for the directory with the following command: ```find / -name wallet.dat -print 2>/dev/null```

**Mac**: LitecoinZ's data directory should be located in ```~/Library/Application Support/LitecoinZ/```.

**Windows**: Go to ```Start>Run``` (or press ```WinKey+R```) and run: ```explorer %APPDATA%\LitecoinZ```
LitecoinZ's data directory will open. "AppData" and "Application Data" are hidden by default in Windows.

## Data directory location
Operating system | Default data directory location | Typical path to configuration file
-----------------|---------------------------------|-----------------------------------
Linux | $HOME/.litecoinz/ | /home/\<username\>/.litecoinz/litecoinz.conf
Mac | $HOME/Library/Application Support/LitecoinZ/ | /Users/\<username\>/Library/Application Support/LitecoinZ/litecoinz.conf
Windows | %APPDATA%\\LitecoinZ\\ | C:\\Users\\\<username\>\\AppData\\Roaming\\LitecoinZ\\litecoinZ.conf

### Note
On Windows XP, typical path to configuration file is C:\\Documents and Settings\\\<username\>\\Application Data\\LitecoinZ\\litecoinz.conf
