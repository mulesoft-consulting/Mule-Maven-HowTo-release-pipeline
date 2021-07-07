# Release Pipelines

Contains example scripts for implementing release pipelines for Mule release processes.

These are scripts developed for Jenkins running on a linux server.

##Component Release Pipelines

###component.release
* Is a Jenkins declarative pipeline
* Create a new "Pipeline" item in Jenkins folder 
* Choose "This project is parameterized"
* Uses standard Maven foundation
* Uses parameters to deploy any deployable artifact published to an artifact respository
* Uses Git tags to determine what versions of an artifactId are available
* Edit the pipeline parameters section to define appropriate default and choice values
* Edit the pipeline environment section as required (MULE_SETTINGS in particular)
* Edit the pipeline deploy functions to include additional mvn command line parameters as required 