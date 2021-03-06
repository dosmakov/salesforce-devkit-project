# salesforce-devkit-project
The repository can be used to initiate a new Salesforce.com development project. It uses ant-salesforce and git.

# Note about Salesforce Developer Experience (DX)
The repository was an attempt to use git in the Salesforce.com development life-cycle before Salesforce DX was announced. Salesforce Developer Experience (DX) is a new way to manage and develop apps on the Force.com platform across their entire life cycle. It brings together the best of Force.com to enable source-driven development, team collaboration with governance, and new levels of agility for custom app development on Salesforce.

Go through  [Get Started with Salesforce DX](https://trailhead.salesforce.com/trails/sfdx_get_started) trailhead for more information.

# Reference links:
1. [Force.com Migration Tool Guide](https://developer.salesforce.com/docs/atlas.en-us.daas.meta/daas/meta_development.htm)
2. [Metadata API Developer Guide](https://developer.salesforce.com/docs/atlas.en-us.api_meta.meta/api_meta/meta_intro.htm)
3. [Apace Ant](http://ant.apache.org/)

# Configuration
1. Clone the repositary
2. Enter Salesforce Connection Information in _master.properties_ file. The file will be used in _master_ branch. See [Entering Salesforce Connection Information](https://developer.salesforce.com/docs/atlas.en-us.daas.meta/daas/forcemigrationtool_connect.htm) at Force.com Migration Tool Guide for more information.
3. Create new git branch, e.g. _dev_ or _feture1_
4. Copy _master.properties_ to _<branch name\>.properties_
5. Enter Salesforce Connection Information in the just created _.properties_ file.

You have to create seporate \*.properties file per each branch. So the brnaches will linked to the specific salesforce.com instance.

**Note: The \*.properties files are added to .gitignore**

# Usage

```
ant <target>
```

Ant targets:

1. **deploy** - deploys changes to the Salesforce.com instance
2. **remove** - deploys destructiveChanges.xml to to the Salesforce.com instance. See [Deleting Components from an Organization](https://developer.salesforce.com/docs/atlas.en-us.api_meta.meta/api_meta/meta_deploy_deleting_files.htm) at Metadata API Developer Guide
3. **retrieve** - refreshs _src_ folder by retrieving Metadata from Salesforce.com instance to the the temp folder _.src_, delete _src_ folder and rename _.src_ to _src_
4. **commit** - Commits changes with "Deployment: ${git.message}" message
5. **push** - runs deploy, remove, retrieve and commit.
