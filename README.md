# ExpiresFilter
This project is a port of Tomcat 7.0 [ExpiresFilter](https://tomcat.apache.org/tomcat-7.0-doc/config/filter.html#Expires_Filter) to Tomcat 6. It's a Maven Project created in Eclipse Neon.

This project will generate a jar file that you can put in your /opt/tomcat/lib folder. See "Installation" bellow.

I tested it with Tomcat 6.0.24. 

# How to build and deploy

You can import this project to your Eclipse.

### Adjust pom.xml for your environment

My environment uses java jre 1.6 and Tomcat 6.0.24. 

If you use different versions, edit the pom.xml file and change maven compiler "target" version, or the versions in the "catalina" and "juli" artifacts.

### Build the jar file

    mvn clean install

The jar file will be created in the project's **./target** folder.

### Put the jar in the tomcat's lib dir

Copy the jar to $CATALINA_HOME/lib or $CATALINA_HOME/webapps/<APP>/WEB-INF/lib dirs.

Configure the web.xml file as described in the doc [ExpiresFilter](https://tomcat.apache.org/tomcat-7.0-doc/config/filter.html#Expires_Filter).

Restart tomcat

# Implementation Notes

This package does not change the original filter behaviour and the documentation of the original filter can be followed integrally.

This package started by copying the original class org.apache.catalina.ExpiresFilter to bnegrao.filters.ExpiresFilter and then bringing the group of classes used by ExpiresFilter but are missing in Tomcat 6. 

The only part of the code that was modified is the inner class  **ExpiresFilter.XHttpServletResponse**, that was extended to provide the "getStatus()" method that is not present in Tomcat 6 HttpServerResponse implementation.
