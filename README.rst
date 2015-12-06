vCard Importer
==============

This script can be used to import a vCard file to a CardDAV server. 

Important notice
~~~~~~~~~~~~~~~~

TL;DR Use it at your own risk.

This script changes the UID of all the vCards to a v4 uuid before sending them to the CardDAV server and it will not check for duplicate entries.

Using it you may lose all of your contacts, crash your CardDAV server, call your ex-girlfriend or even worse.

As far I know, it has been tested without issues with: 

* Davical
* Baikal

And it didn't kill my neighbors (although I haven't heard from of them since...).

Requirements
~~~~~~~~~~~~

This script should work on any Unix system with bash (it probably works with cygwin too) but has only been tested on a Linux system. 

The requirements are: 

* curl
* grep
* sed
* bash (at least v4)

It is recommended to have:

* csplit (from coreutils)
* uuid (this one is really optional)

Usage
~~~~~

First, edit the script with any text editor to change the configuration variables at the beginning:

* user
* pass
* cardsCollection
* serverURL
* serverFullURL

Then just run the script and wait: 

  cardimport.sh Contacts.vcf

Bugs
~~~~

There is no check that curl uploaded the vCards properly, if you get any error message, this is probably because there is something wrong with your configuration variables (or network).

If you stop the script, a temporary folder will stay on `/tmp/` and will not be deleted, you can delete it safely.

Maybe others, and if you found them, fix and tell me :)

License
~~~~~~~

TL;DR it's under WTFPL.

You can find the full license into COPYING.

