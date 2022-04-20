# modchecksum

The idea is to create a sha256 hash for every file created during setup.

By comparing this list against a list created for your own modx installation, you can check the integrety of your MODx system.

## Versioning

2022-04-20 version 0.0.1 proof of concept

The snippet it is based on will be published at a later time. It is NOT AVAILABLE at the moment. The main purpose of this repo is to store the hash databases for each modx version 2.7.0 and up. 

MODx3 might be also covered if it makes sense.

## Background

The script creates a sha256 hash for each MODX file present in your system (standard installation). It will ignore a number of files and directories that are defined by an exclude list.

The result will look like this:

<img width="942" alt="image" src="https://user-images.githubusercontent.com/667315/164223258-7adb6e8c-44b5-46c6-ac64-b6ed01d6bdda.png">

The script will compare the results against a whitelist and return a warning if one of the following things are true:

* a file was changed 
* a file is unknown
* a file is missing

The screenshot below shows a test run:

<img width="988" alt="image" src="https://user-images.githubusercontent.com/667315/164215990-48deab7a-3e4d-469b-8a49-0a65f2597ee3.png">

In this example I have 

* added a comment to index.php (corrupted)
* added test.txt to connectors (unknown)
* renamed changelog.txt to changelogs.txt (unknown and missing)

(The modx.2.7.2-pl.json file in my root is only for testing)

You can use the results to track down issues (corrupted or missing files, hacks, etc.).

## Ignore list

The script will exclude a list of directories, files and extensions:

```
$exclude = array( // 2do...
    'paths' => array (
         'assets/'
        ,'core/cache/'
        ,'core/components/'
        ,'core/packages/'
    )
    ,'files' => array(
         'config.core.php'
        ,'ht.access'
        ,'.htaccess'
        ,'config.inc.php'
    )
    ,'extensions' => array('')
);
```

Note: If you think there is a file or directory missing in this list, please open an issue.

## MODX Versions covered so far

So far the following setups are covered:

* modx2.7.0-pl.json
* modx2.7.1-pl.json
* modx2.7.2-pl.json
* modx2.7.3-pl.json
* modx2.8.0-pl.json
* modx2.8.1-pl.json
* modx2.8.2-pl.json
* modx2.8.3-pl.json

The complete list can be found here: https://github.com/pepebe/modchecksum/tree/main/checksums

Additional setups for future version will be added from time to time. Older version if there is demand for this.

## Contribution

Is very much appreciated!
