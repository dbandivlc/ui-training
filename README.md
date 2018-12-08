# Exercise - Vlocity Build

Welcome to the [Vlocity Build Tool] brought to you by [Vlocity](https://vlocity.com).

Vlocity Build is a command line tool to export and deploy Vlocity DataPacks in a source control friendly format through a YAML Manifest describing your project. Its primary goal is to enable Continuous Integration for Vlocity Metadata through source control. It is written as a Node.js Command Line Tool.

## Quick start

Before getting started ensure you have Node JS installed : https://nodejs.org/

1. Create a project folder `mkdir vlocity-build`
2. Change into the `vlocity-build` folder using `cd vlocity-build`.
3. Run `npm install --global vlocity`. 
4. Create a `properties` file in the root folder : `build_training.properties`
5. Create a folder named `dataPacksJobs` and create Job file : `DataPack.yaml`
6. Download Training zip file from Groups - Install SetUp DataPack - Vlocity Build.
7. Extract the folder from Training zipfile and add it in the root folder. 

  Folder Strucure:

    vlocity-build
    ├── build_training.properties
    ├── Training                    # Documentation files (alternatively `doc`)
    │   ├── Attachment              # Table of contents
    │   ├── AttributeCategory              # Frequently asked questions
    │   ├── DataRaptor             # Miscellaneous information
    │   ├── OmniScript            # Getting started guide
    │   └── ...                 # etc.
    └── dataPackJobs
        └── DataPack.yaml  

6. In the `build.properties` file, add the below code.
```
# Salesforce Username and Password + Security Token
sf.username = <Username>
sf.password = <Password><SecurityToken>

# Please uncomment if using a Sandbox 
sf.loginUrl = https://<login-or-test>.salesforce.com

# Path to dataPacksJobsFolder. Allows storing job files inside specified folder
vlocity.dataPacksJobFolder = ./dataPacksJobs
```
7. In the `DataPack.yaml` file, add the below code.
```
projectPath: ./Training
expansionPath: .
buildFile: AllDataPacks.json
preStepApex:
  Deploy: 
    VlocityUITemplate: DeactivateTemplatesAndLayouts.cls
    VlocityUILayout: DeactivateTemplatesAndLayouts.cls
postStepApex:
  Deploy: 
    Product2: EPCProductJSONUpdate.cls      
queries: 
  - VlocityDataPackType: OmniScript
    query: Select Id, %vlocity_namespace%__Type__c, %vlocity_namespace%__SubType__c, %vlocity_namespace%__Language__c from %vlocity_namespace%__OmniScript__c where %vlocity_namespace%__SubType__c = 'UIFlow'
  - VlocityDataPackType: SObject
    query: Select Id FROM CarBrands__c
  - Product2
delete: true
activate: true
compileOnBuild: true
maxDepth: -1
continueAfterError: true
defaultMaxParallel: 10
exportPacksMaxSize: 10
useAllRelationships: false
supportHeadersOnly: true
supportForceDeploy: true
```
8. Run the following command in the terminal
`vlocity packDeploy -propertyfile build_training.properties -job DataPack.yaml`

Login to your org using your browser, you should be able to see Product2, OmniScripts, DataRaptors and Integration Procedures installed.
