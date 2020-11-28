# quarkus-h2 project

This project uses Quarkus, the Supersonic Subatomic Java Framework.

If you want to learn more about Quarkus, please visit its website: https://quarkus.io/ .

## Running the application in dev mode

You can run your application in dev mode that enables live coding using:
```shell script
./mvnw compile quarkus:dev
```

Connect to H2 file-in-memory db
You can connect to the H2 file in-memory database through any database manager:


Copy-paste your absolute path of the /src/main/resources/data/ folder +> ${YOUR_ABSOLUTE_PATH_TO_DATA_FOLDER}


Set the following jdbc connection url over your database manager specifying that the Data Source is H2
jdbc:h2:file:${YOUR_ABSOLUTE_PATH_TO_DATA_FOLDER}/database;AUTO_SERVER=true;DB_CLOSE_DELAY=-1

