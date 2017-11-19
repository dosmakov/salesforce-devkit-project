# salesforce-devkit-project
The repository can be used to initiate a new salesforce.com apex development project. It uses ant-salesforce and git for continuous development.

# References links:
1. [Force.com Migration Tool Guide)(https://developer.salesforce.com/docs/atlas.en-us.daas.meta/daas/meta_development.htm)
2. [Metadata API Developer Guide)(https://developer.salesforce.com/docs/atlas.en-us.api_meta.meta/api_meta/meta_intro.htm)
3. [Apace Ant](http://ant.apache.org/)

# Configuration
1. Clone the repositary
2. Enter Salesforce Connection Information in _master.properties_ file. The file will be used in _master_ branch. See [Entering Salesforce Connection Information](https://developer.salesforce.com/docs/atlas.en-us.daas.meta/daas/forcemigrationtool_connect.htm) at Force.com Migration Tool Guide for more information.
3. Create new git branch, e.g. _dev_ or _feture1_
4. Copy _master.properties_ to _<branch name\>.properties_
5. Enter Salesforce Connection Information in the just created _.properties_ file.

You have to create seporate \*.properties file per each branch. So the brnaches will linked to the specific salesforce.com instance.

** Note: The \*.properties files are added to .gitignore **

# Usage

Ant targets:

1. commit - Commits changes with "Deployment: ${git.message}" message
2. deploy - deploys changes to the Salesforce.com instance
4. remove - deploys destructiveChanges.xml to to the Salesforce.com instance. See [Deleting Components from an Organization](https://developer.salesforce.com/docs/atlas.en-us.api_meta.meta/api_meta/meta_deploy_deleting_files.htm) at Metadata API Developer Guide
5. retrieve - refreshs _src_ folder by retrieving Metadata from Salesforce.com instance to the the temp folder _.src_, delete _src_ folder and rename _.src_ to _src_
6. push - runs deploy, remove, retrieve and commit.
