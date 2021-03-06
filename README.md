dataZ Installer
===============

Installs, updates and switch branches of all dataZ/DataStore Projects. And it also generates a parent (gradle) project for all cloned projects (on a specified path).

__CAUTION__: The dataZ installer DOES NOT build or create the JAR files (_see Using dataZ Projects_). It only clones the dataZ related projects and create the gradle parent project.


Three Simple Steps
==================

1. Clone this repository (or download is as ZIP) from Github.
2. Start installing the actually dataZ projects.
3. Use the projects (build, install, modify, ...).


How to clone this Repository?
=============================

Just call

    git clone https://github.com/loddar/dataz-install.git


How to Install?
===============

After cloning this repository, you should execute

      ./gradlew install

or under Windows

      gradlew.bat install

This will create (clone) all dataZ projects into a directory (default is __../dataz-projects__). If you like to change the target directory, you can use
the *-PtargetDir* Gradle property. If you don't like to call it all the time, change the property in _gradle.properties_.

Example:

    ./gradlew -PtargetDir=$HOME/my/target/directory install

That's it. After installation you found all dataZ projects in the default directory

    ../dataz-projects
    
or if you've used _$HOME/my/target/directory_ 
    
   $HOME/my/target/directory 


__CAUTION__: The dataZ projects (actually their JARs) have __not__ been build or installed, yet. (See _Using dataZ Projects_).

How to update?
==============

Just call

    ./gradlew update

or

    ./gradlew -PtargetDir=$HOME/my/target/directory update


Switching to an existing branch
================================

Sometimes it is necessary to switch to a branch. First you muast know which are the existing branches. 

You can resolve them by calling

    ./gradlew show-branches  

or of course 

    ./gradlew -PtargetDir=$HOME/my/target/directory show-branches
     

You will get something like this:

```
    :show-branches
    Show branches of project 'dataset':
    * master
      remotes/origin/HEAD -> origin/master
      remotes/origin/Release0.5
      remotes/origin/master
    Show branches of project 'datastore-sql':
    * master
      remotes/origin/HEAD -> origin/master
      remotes/origin/Release0.5
      remotes/origin/master
    Show branches of project 'datastore-neo4j':
    * master
      remotes/origin/HEAD -> origin/master
      remotes/origin/Release0.5
      remotes/origin/master
```

Now you can switch to an __existing__(!) branch like _Release0.5_ by calling
    
    ./gradlew switch-branch -Dbranch=Release0.5

or 

    ./gradlew -PtargetDir=$HOME/my/target/directory switch-branch -Dbranch=Release0.5
    
Using dataZ Projects
======================

First go to the parent project.

    cd ../dataz-projects
    
or

    cd $HOME/my/target/directory
    
Build, install, etc the projects.
 
    ./gradlew install
    
    
__Remarks__
 
- If you wan't to work on a branch, do not forget to switch (see _Switching to an existing branch_).   
- If you like to create the jar files, then call _./gradlew build_.
- If you like to install the jar files within your local maven repository, then call _./gradlew install_.
- If you like to create idea project files, then call _./gradlew idea_.
- If you like to create eclipse project files, then call _./gradlew eclipse_.

The Dependencies
================

Java8 and Git must be installed. You can download it from here:

* [Java 8 SDK on Oracle](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)
* [Git](http://git-scm.com/downloads)

Gradle is optional, because you can use the Gradle Wrapper (gradlew). But if you like to download, you can find it [here](https://www.gradle.org/downloads).

Issues
======

If you want to report any issue or feature request (specific to the dataZ Installer), please do it [here](https://github.com/loddar/dataz-install/issues).


Social
======

You can found me on

[Twitter](https://twitter.com/failearly)

[LinkedIn](https://www.linkedin.com/in/markoumek)


License
=======

![GPL v3](http://www.gnu.org/graphics/gplv3-127x51.png)
