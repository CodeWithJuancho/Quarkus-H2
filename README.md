# quarkus-h2 project

This project uses Quarkus, the Supersonic Subatomic Java Framework.

If you want to learn more about Quarkus, please visit its website: https://quarkus.io/ .

## Running the application in dev mode

You can run your application in dev mode that enables live coding using:
```shell script
./mvnw compile quarkus:dev
```

## How to set H2 Database console url in the Quarkus

0.	Assuming that you already have the quarkus-jdbc-h2 extension added
1.	Add the quarkus-vertx and quarkus-undertow extensions
2.	Create the deployment descriptor under src/main/resources/META-INF/web.xml
3.	Configure the H2 console Servlet like so

    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE web-app
            PUBLIC "-//Sun Microsystems, Inc.//DTD Web Application 2.3//EN"
            "http://java.sun.com/dtd/web-app_2_3.dtd">
    
    <web-app>
        <display-name>My Web Application</display-name>
    
        <servlet>
            <servlet-name>h2-console</servlet-name>
            <servlet-class>org.h2.server.web.WebServlet</servlet-class>
        </servlet>
    
        <servlet-mapping>
            <servlet-name>h2-console</servlet-name>
            <url-pattern>/h2/*</url-pattern>
        </servlet-mapping>
    
    </web-app>

Run ./mvnw quarkus:dev and go to http://localhost:8080/h2 where the console should show up.

## Absolute Path vs Relative Path

3. Is not scalable and quality code
2. Is not well programmed
1. Is not reproducible right out of the box for other developer

### Connect to H2 file-in-memory db

You can connect to the H2 file in-memory database through any database manager:

1. Copy-paste your absolute path of the **/src/main/resources/data/** folder +> `YOUR_ABSOLUTE_PATH_TO_DATA_FOLDER`

2. Set the following jdbc connection url over your database manager specifying that the Data Source is **H2**

    `jdbc:h2:file:YOUR_ABSOLUTE_PATH_TO_DATA_FOLDER/database;AUTO_SERVER=true;DB_CLOSE_DELAY=-1`



