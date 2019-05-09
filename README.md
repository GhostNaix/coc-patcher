**Warning:** With version 8.212.12, Supercell has started banning accounts for the use of third party software. I am unsure what, if any, checks are in place that might reveal the use of these patches, so continue use at your own risk.  See [here](http://supercell.com/en/safe-and-fair-play/) for more info.

# coc-patcher

_Patches and signs the Clash of Clans APK_

Run with:

    python3.5 patcher.py [--json] version-number

For example:

    python3.5 patcher.py 2.212.9

By default, `coc-patcher` will retrieve the keys, MD5s, and key and URL offsets from the [`coc-proxy` wiki](https://github.com/clugh/coc-proxy/wiki).  To provide these values for a new or unknown APK version, enter them in `config.json` and use the `--json` flag.  Enter them with the following layout:

    "versions": {
      "8.212.9": {
        "key": "469b704e7f6009ba8fc72e9b5c864c8e9285a755c5190f03f5c74852f6d9f419",
        "arm": {
          "md5": "769e2e9e1258b75d15cb7e04b2e49de3",
          "key-offset": "4280344",
          "url-offset": "3534513"
        },
        "x86": {
          "md5": "29ca23e48a5e419e83f2a7988c842d3e",
          "key-offset": "6189080",
          "url-offset": "4768816"
        }
      }
    }

## Installation

1. Install dependencies.
2. Fill in the `config.json` file.

    Note: The `keypass` and `dname` fields are only required to create a new keystore.  See [here](http://docs.oracle.com/javase/7/docs/technotes/tools/solaris/keytool.html#DName) for how to fill out the `dname` fields.

## Dependencies

~~- [Apktool](http://ibotpeaches.github.io/Apktool/)~~

- `keytool` and `jarsigner`-from the [Java JDK](http://www.oracle.com/technetwork/java/javase/downloads/index.html) (Put C:\Program Files\Java\jdk-12.0.1\bin; into your PATH variable)

- `md5sum` and `dd` from [Coreutils](http://www.gnu.org/software/coreutils/coreutils.html) (Windows binaries available in [Git for Windows](https://git-scm.com/download/win))

~~- `zipalign` from the [Android SDK]~(http://developer.android.com/sdk/index.html#Other)~~

Why ? It's included in the  directory I'm nice enough to supply it to you so you don't have to download their full packages
All tools such as apktool, zipalign belongs to their respective owners I did not make them. I'm only a repacker making this easier to use for beginners 
- [requests](http://python-requests.org/) and [requests-cache](https://github.com/reclosedev/requests-cache)

    Note: `requests` and `requests-cache` can be installed with:

        python3 -m pip install requests requests-cache
