Install and Configure Repo Server
Install and configure Nexus or Artifactory
Create the hosted maven 2 repo (rhpam-maven)
Create a hosted maven 2 repo for snapshots (rhpam-snapshots)
Create a hosted maven 2 repo for releases (rhpam-releases)
Create a role with nx-all previlages and nexus-admin role (you can change the role as needed)
Create a user in nexus with the role create in step 5

Create Offline Repository
Download the maven offliner tool from the Red Hat PAM download page Red Hat Process Automation Manager 7.11.1 Offliner Content List 
Unzip it to a folder
Run the offline-repo-builder.sh, this will create a folder called repository
Compress the repository folder (maven offline repository) and copy it over to the Nexus or Artifactory repo server
Download the maven repo provisioner tool to push the artifacts to the maven repo (rhpam-maven repository or another repo of choice) - (maven-repository-provisioner-1.4.1-jar-with-dependencies.jar)
Run the maven repo provisioner tool 
java - jar maven-repository-provisioner-*-jar-with-dependencies.jar  -cd “<<path to the repository folder>>” -t “<<repo url>>" ﻿-u <<repo user name>>  -p <<repo user password>>

Install/Configure the postgres DB with byteea
Scripts attached for RH PAM 7.11.1

Install the Business Automation Operator
Run the KIEApp.yaml to create the RHPAM Environment (sample KIEApp.yaml attached with byteea schema JVM argument)
Update the Repo and the DB configurtions as appropriate
