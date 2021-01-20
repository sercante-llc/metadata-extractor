# Salesforce Metadata Extractor

This simple project is designed to easily extract almost ALL metadata from a Salesforce Org so that it can easily be searched.

## Instructions

1. Clone this repository, [or download and extract a zip file](https://github.com/sercante-llc/metadata-extractor/archive/main.zip):

    ```
    git clone https://github.com/sercante-llc/metadata-extractor.git
    cd metadata-extractor
    ```

1. Connect SFDX to your org. [Install Salesforce CLI if you don't already have it](https://developer.salesforce.com/docs/atlas.en-us.sfdx_setup.meta/sfdx_setup/sfdx_setup_install_cli.htm)
    ```
    # likely the command that will work for you
    sfdx force:auth:web:login -s -a myorg

    # if you are using a sandbox, use this:
    sfdx force:auth:web:login -s -a myorg -r https://test.salesforce.com

    # if you want to specify a company specific login URL, use this command
    sfdx force:auth:web:login -s -a myorg -r https://mycompanyloginurl.my.salesforce.com
    ```
1. Download your metadata
    ```
    sfdx force:source:retrieve --manifest manifest/package.xml -u myorg
    ```
1. View your files in force-app/main/default