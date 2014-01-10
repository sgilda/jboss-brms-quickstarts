stateful-ksession: Stateful Kie Session Quickstart
==================================================
Author: Rafael Benevides
Level: Intermediate
Technologies: CDI, JSF, Drools
Summary: This Quickstart shows how to use Stateful Kie Session
Target Product: BRMS
Product Versions: EAP 6.1, EAP 6.2
Source: <https://github.com/jboss-developer/jboss-brms-quickstarts>

What is it?
-----------

This projects demonstrates the use of Drools Stateful KIE session. Stateful KIE sessions are longer lived and allow iterative changes over time.

In this use case we see a 'House' (with a fire alarm) and it contains 'Rooms' and fire 'Sprinkler''s for each room. 

This Quickstarts contains two modules:

- The Kmodule project: Contains the model classes (House, Room, Alarm, Sprinkler and Fire) and the rule file (houserules.drl).

- The Web project: Contains a web application that allows you to simulate the fire on each room.

System requirements
-------------------

The application this project produces is designed to be run on Red Hat JBoss Enterprise Application Platform 6.1 or later. 

All you need to build this project is Java 6.0 (Java SDK 1.6) or later, Maven 3.0 or later.

 
Configure Maven
---------------

If you have not yet done so, you must [Configure Maven](../README.md#configure-maven) before testing the quickstarts.



Start the JBoss Server
----------------------

1. Open a command prompt and navigate to the root of the JBoss server directory.
2. The following shows the command line to start the server:

        For Linux:   JBOSS_HOME/bin/standalone.sh
        For Windows: JBOSS_HOME\bin\standalone.bat


Build and Deploy the Quickstart
-------------------------

_NOTE: The following build command assumes you have configured your Maven user settings. If you have not, you must include Maven setting arguments on the command line. See [Build and Deploy the Quickstarts](../README.md#build-and-deploy-the-quickstarts) for complete instructions and additional options._

1. Make sure you have started the JBoss Server as described above.
2. Open a command prompt and navigate to the root directory of this quickstart.
3. Type this command to build and deploy the archive:

        mvn clean install jboss-as:deploy

4. This will deploy `web/target/brms-stateful-ksession-web.war.war` to the running instance of the server. 


Access the application 
---------------------


Access the running application in a browser at the following URL:  <http://localhost:8080/brms-stateful-ksession-web/>

You will be presented to a Dashboard that shows two tables:

On the left Table there are house's rooms and you can simulate a fire on the each room.

Click on the 'Initiate Fire' button on any room and realize that all Sprinkler on that room (on the right table) will be turned on. You will also see a text 'FIRE ALARM RINGING'

If you 'Extinguish Fire' on that Room, the Sprinkler's for that room will be turned off.

If there isn't any Fire on any Room, the 'FIRE ALARM RINGING' will also be disapear.


Undeploy the Archive
--------------------

1. Make sure you have started the JBoss Server as described above.
2. Open a command line and navigate to the root directory of this quickstart.
3. When you are finished testing, type this command to undeploy the archive:

        mvn jboss-as:undeploy


Run the Arquillian Tests (For quickstarts that contain Arquillian tests)
-------------------------

Run the Arquillian Tests 
-------------------------

This quickstart provides Arquillian tests. By default, these tests are configured to be skipped as Arquillian tests require the use of a container. 

_NOTE: The following commands assume you have configured your Maven user settings. If you have not, you must include Maven setting arguments on the command line. See [Run the Arquillian Tests](../README.md#run-the-arquillian-tests) for complete instructions and additional options._

1. Make sure you have started the JBoss Server as described above.
2. Open a command prompt and navigate to the root directory of this quickstart.
3. Type the following command to run the test goal with the following profile activated:

        mvn clean test -Parq-jbossas-remote 


Run the Quickstart in JBoss Developer Studio or Eclipse
-------------------------------------

You can also start the server and deploy the quickstarts from Eclipse using JBoss tools. For more information, see [Use JBoss Developer Studio or Eclipse to Run the Quickstarts](../README.md#use-jboss-developer-studio-or-eclipse-to-run-the-quickstarts) 

Debug the Application
------------------------------------

If you want to debug the source code or look at the Javadocs of any library in the project, run either of the following commands to pull them into your local repository. The IDE should then detect them.

    mvn dependency:sources
    mvn dependency:resolve -Dclassifier=javadoc
