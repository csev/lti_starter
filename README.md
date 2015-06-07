Tsugi for Java Persistence Architecture (JPA)
=============================================

This is a fork of azeckoski/lti\_starter as I intend to refactor this and align
the library patterns with Tsugi's APIs.

IMS LTI 1 and 2 based starter (sample) application written using Java and Spring Boot

The goal is to have a Java based web app which can serve as the basis (or starting point) for building a fully compliant LTI 1 or 2 based tool without having to manage the complexities of LTI 2 or come up with a strategy for handling the various types of data storage.

Parts based on the data structures and code in tsugi (https://github.com/csev/tsugi) which is a Multi-tenant learning tool hosting platform (http://www.tsugi.org)

Build
-----
This will produce a starter.war file in the *target* directory which can be placed into any standard servlet container.

    mvn install

Install Tsugi
-------------

Then download and install MAMP and  the PHP Tsugi application and create its database use the default passwords for a dev
environment.

    http://www.tsugi.org/

The default settings for this servlet expect that database to be up and 
available (i.e. MAMP is running and MySQL is on port 8889)  You can connect this
to a different database by editing:

    src/main/resources/application.properties

But for the simple case - just install and get Tsugi running and then run this Java application.

Quick Run
---------
You can run the app in place to try it out without having to install and deploy a servlet container.

    mvn clean install spring-boot:run

Then go to the following default URL:

    http://localhost:8080/

Customizing
-----------
Use the application.properties to control various aspects of the Spring Boot application (like setup your own database connection).
Use the logback.xml to adjust and control logging.

Debugging
---------
To enable the debugging port (localhost:8000) when using spring-boot:run, use the main profile: -Pdebug. Then you can attach any remote debugger (eclipse, intellij, etc.) to localhost:8000. NOTE that the application will pause until you connect the debugger to it.

    mvn clean install spring-boot:run -Pdebug
