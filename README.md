# Release Pipelines

Contains example scripts for implementing release pipelines for Mule release processes.

These are scripts developed for Jenkins running on a linux server.

##Component Release Pipelines

All these pipeline scripts use the standard Maven foundation that establishes the standard Maven command syntax. This includes using a standard settings.xml file which is stored on the Jenkins server in a file referenced by the MULE_SETTINGS environment value.

These are meant to be examples and may require customization to fit with your specific organization's processes and procedures.

###component.release

Deploys a single component according to values specified in the Build Parameters.

* Is a Jenkins declarative pipeline
* Create a new "Pipeline" item in Jenkins folder 
* Choose "This project is parameterized"
* Uses standard Maven foundation
* Uses parameters to deploy any deployable artifact published to an artifact respository
* Uses Git tags to determine what versions of an artifactId are available
* Edit the pipeline parameters section to define appropriate default and choice values
* Edit the pipeline environment section as required (MULE_SETTINGS in particular)
* Edit the pipeline deploy functions to include additional mvn command line parameters as required 

###coordinated.release

Deploys many components. Each component to deploy is specified as a deploy() function call. This shows deploying two versions of the same application to different environments. The deployment uses a Build Parameter value and the second shows hardcoding the environment.

* Is a Jenkins declarative pipeline
* Create a new "Pipeline" item in Jenkins folder 
* Choose "This project is parameterized"
* Uses standard Maven foundation
* Uses parameters to deploy any deployable artifact published to an artifact respository
* Uses deploy() function to specify deployment specifics for each component
* Edit the pipeline parameters section to define appropriate default and choice values
* Edit the pipeline environment section as required (MULE_SETTINGS in particular)
* Edit the pipeline deploy functions to include additional mvn command line parameters as required