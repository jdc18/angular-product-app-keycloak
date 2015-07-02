Angular Product App2 for Keycloak
========================
Author: Juan Diego Calle
Level: Intermediate
Technologies: AngularJS JAX-RS

What is it?
-----------

It is a sample, deployable Maven 3 project, but you really dont need maven.  It is based on Angular Product App from keycloak.
https://github.com/keycloak/keycloak/tree/master/examples/demo-template
You'll need the the database-service example from the demo-template from Keycloak.

System requirements
-------------------

You need Bower running
A web server like Apache, Nginx, Apache Tomcat, or JBoss/WildFly for the this page. 
A server running JBoss/Wildfly running Keycloak's Database-service to request the products

Configure Keycloak
----------------------------

On the keycloak server create a realm and add Public Client (Acces Type Public) with the proper Valid Redirect URIs and Web Origins.
Copy the proper keycloak.json file to usr/main/web/app.

Install Angular Dependencies
----------------------------

Go to usr/main/webapp and run bower install

        bower install
 
Configure Maven
---------------

If you have not yet done so, you must [Configure Maven](https://github.com/jboss-developer/jboss-developer-shared-resources/blob/master/guides/CONFIGURE_MAVEN.md) before testing the quickstarts.


Start JBoss WildFly with the Web Profile
-------------------------

1. Open a command line and navigate to the root of the JBoss server directory.
2. The following shows the command line to start the server with the web profile:

        For Linux:   JBOSS_HOME/bin/standalone.sh
        For Windows: JBOSS_HOME\bin\standalone.bat

 
Build and Deploy the Quickstart
-------------------------

_NOTE: The following build command assumes you have configured your Maven user settings. If you have not, you must include Maven setting arguments on the command line. See [Build and Deploy the Quickstarts](https://github.com/jboss-developer/jboss-eap-quickstarts#build-and-deploy-the-quickstarts) for complete instructions and additional options._

1. Make sure you have started the JBoss Server as described above.
2. Open a command line and navigate to the root directory of this quickstart.
3. Type this command to build and deploy the archive:

        mvn clean package wildfly:deploy

4. This will deploy `target/angular-product-app2.war` to the running instance of the server.

Or just mvn install or just copy src/main/webapp to your web server.  Running your page without a web server will give you trouble when loading external files like keycloak.json or any $http request.
 

Access the application 
---------------------

The application will be running at the following URL: <http://localhost:8080/angular-product-app2/>.


Undeploy the Archive
--------------------
Only if you are running on JBoss/Wildfly

1. Make sure you have started the JBoss Server as described above.
2. Open a command line and navigate to the root directory of this quickstart.
3. When you are finished testing, type this command to undeploy the archive:

        mvn wildfly:undeploy


