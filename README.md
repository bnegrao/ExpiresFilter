# ExpiresFilter
This project is a port of Tomcat 7.0 [ExpiresFilter](https://tomcat.apache.org/tomcat-7.0-doc/config/filter.html#Expires_Filter) to Tomcat 6. It's a Maven Project created in Eclipse Neon.

This package does not change the original filter behaviour and the documentation of the original filter can be followed integrally.

This package started by copying the original class org.apache.catalina.ExpiresFilter to bnegrao.filters.ExpiresFilter and then bringing the group of classes used by ExpiresFilter but are missing in Tomcat 6. 

The only part of the code that was modified is the inner class  ExpiresFilter.XHttpServletResponse, who was extended to provide the "getStatus()" method that is not present in Tomcat 6 HttpServerResponse implementation.

I tested it with Tomcat 6.0.24. 

# How to compile

Import this project to your Eclipse.

Edit the pom.xml and adjust the java
