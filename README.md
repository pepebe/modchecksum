# modchecksum
checksums for all modx files present after a new installation 

The idea is to create a sha256 hash for every file. 

By comparing this list against your modx installation, you can control the integrety of your installation:

The script will return a warning if one of the following things are true:

* a file is changed 
* a file is renamed
* a file is deleted

At this point a json file is returned:

<img width="988" alt="image" src="https://user-images.githubusercontent.com/667315/164215990-48deab7a-3e4d-469b-8a49-0a65f2597ee3.png">

You can use this warning to track down issues (corrupted files, hacks, etc.).

## Versions

So far the following setups are covered:

* modx2.7.0-pl.json
* modx2.7.1-pl.json
* modx2.7.2-pl.json
* modx2.7.3-pl.json
* modx2.8.0-pl.json
* modx2.8.1-pl.json
* modx2.8.2-pl.json
* modx2.8.3-pl.json

Additional setups for future version will be added from time to time. Older version if there is demand for this.

## Versioning

2022-04-20 version 0.0.1 proof of concept

The snippet it is based on will be published at a later time. The main prupose of this repo so far is to store the hash databases for each modx version 2.7.0 and up. 

MODx3 might be also covered if it makes sense.
