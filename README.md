Install and Configure Repo Server
 1. Install and configure Nexus or Artifactory
 2. Create the hosted maven 2 repo (rhpam-maven)
 3. Create a hosted maven 2 repo for snapshots (rhpam-snapshots)
 4. Create a hosted maven 2 repo for releases (rhpam-releases)
 5. Create a role with nx-all previlages and nexus-admin role (you can change the role as needed)
 6. Create a user in nexus with the role create in step 5

Create Offline Repository
 1. Download the maven offliner tool from the Red Hat PAM download page [Red Hat Process Automation Manager 7.11.1 Offliner Content List](https://access.redhat.com/jbossnetwork/restricted/softwareDetail.html?softwareId=100021&product=rhpam&version=7.11.1&downloadType=distributions) 
    a. Unzip it to a folder
    b. Run the offline-repo-builder.sh, this will create a folder called repository
 2. Compress the repository folder (maven offline repository) and copy it over to the Nexus or Artifactory repo server
 3. Download the maven repo provisioner tool  on the repo server to push the artifacts to the maven repo (rhpam-maven repository or another repo of choice) - ([maven-repository-
    provisioner-1.4.1-jar-with-dependencies.jar](https://repo.maven.apache.org/maven2/com/simpligility/maven/maven-repository-provisioner/1.4.1/maven-repository-provisioner-1.4.1-jar-with-dependencies.jar))
 4. Run the maven repo provisioner tool 
    a. java - jar maven-repository-provisioner-*-jar-with-dependencies.jar  -cd “<< path to the repository folder >>” -t “<< repo url >>" -u << repo user name >>  -p 
       << repo user password >>

Install/Configure the postgres DB with byteea
 1. Scripts attached for RH PAM 7.11.1

Install the Business Automation Operator
 1. Run the KIEApp.yaml to create the RHPAM Environment (sample KIEApp.yaml attached with byteea schema JVM argument)
 2. Update the Repo and the DB configurtions as appropriate
