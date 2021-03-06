easy-module-archetype
=====================
[![Build Status](https://travis-ci.org/DANS-KNAW/easy-module-archetype.png?branch=master)](https://travis-ci.org/DANS-KNAW/easy-module-archetype)


SYNOPSIS
--------

           mvn archetype:generate -DarchetypeGroupId=nl.knaw.dans.easy \
                    -DarchetypeArtifactId=easy-module-archetype \
                    -DarchetypeVersion=1.x-SNAPSHOT \
                    -DgroupId=nl.knaw.dans.easy \
                    -DartifactId=easy-module \
                    -Dpackage=nl.knaw.dans.easy.module \
                    -DmoduleSubpackage=module \
                    -Dname="EASY Module" \
                    -Ddescription="A longer description of this module"


DESCRIPTION
-----------

### Maven Archetype Plug-in

Creates an EASY scala project, prepopulated with common files and structure. 

see <http://maven.apache.org/archetype/maven-archetype-plugin>

### Example usage

Using interactively retrieved parameters in the defaults of others does not currently seem feasible. The order in which the 
parameters are asked from the user cannot be configured, and does not seem to follow any predictable pattern. That is why 
some redundant information needs to be provided. The `moduleSubpackage` parameter *must* be the last package in `package`.

      mvn archetype:generate \ 
                -DarchetypeGroupId=nl.knaw.dans.easy \
                -DarchetypeArtifactId=easy-module-archetype \ 
                -DarchetypeVersion=1.x-SNAPSHOT \
                -DartifactId=easy-test-module \
                -Ddescription="A test module" \
                -Dpackage=nl.knaw.dans.easy.test 
                -DmoduleSubpackage=test

This will create a module called `easy-test-module`. You need to execute `mvn license:format` in this module before
you can successfully build it.

ARGUMENTS
----------

* `-DgroupId`, -- the group ID for the new project. Defaults to `nl.knaw.dans.easy`.
* `-DartifactId` -- the artifact ID for the new project. Use all-lower-case and dash-separated names, starting with `easy-`
* `-Ddescription`, -- longer description for the new project
* `-Dname`, -- long name for the new project
* `-DmoduleSubpackage`, - the package under `nl.knaw.dans.easy` that is used by this project
* `-Dversion`, -- defaults to **1.x-SNAPSHOT**


INSTALLATION AND CONFIGURATION
------------------------------

### Installation steps:

1. Unzip the tarball to a directory of your choice, e.g. /opt/
2. A new directory called easy-module-archetype-<version> will be created


BUILDING FROM SOURCE
--------------------

Prerequisites:

* Maven 3.3.3 or higher

Steps:

        git clone https://github.com/DANS-KNAW/easy-module-archetype.git
        cd easy-module-archetype
        mvn install
