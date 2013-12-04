Tutorial
========

This tutorial indicates how to create a new project and generate source code from an existing database.

This tutorial needs some requirements which are not mandatory otherwise to use Telosys Tools.

Requirements
---

You need to download :
- Eclipse, 
- Telosys Tools version 2.0.7 plugin for Eclipse
- M2eclipse for Kepler (with WTP support)

Steps
---

1. Create project
---

- In eclipse, create new "Maven Project"
- In "New Manen Project" wizard, select "Create a simple project (skip archetype selection)"
- Click "Next"
- Define "Group Id", "Artifact Id"
- Select "war" for "Packaging"
- Click "Finish"
- The new project is added in the workspace

2. Initialize Telosys Tools
---
- Open the properties window of this new project
- In the left entries, select "Telosys Tools"
- "Telosys Tools" properties window is displayed
- Fill all project informations in "General", "Packages" and "Folders" tab
- Click on "init Telosys Tools" in the "General" tab => The "Telosys Tools" directory is now added in the project
- In the "download" tab, download from this Github repository the "spring-mvc-jpa-templates"
- After download, close the project properties window
- In the project, copy the directory : "Telosys Tools / downloads / spring-mvc-jpa-templates" in "Telosys Tools / templates"

3. Configure database in Telosys Tools
---

- Edit the "pom.xml" of your project to add the dependency to the JDBC driver of your database

Example for PostgreSQL :

	<dependencies>
    	<dependency>
            <groupId>postgresql</groupId>
            <artifactId>postgresql</artifactId>
            <version>9.1-901-1.jdbc4</version>
        </dependency>
    </dependencies>
    
or MySQL :

	<dependencies>
    	<dependency>
			<groupId>mysql</groupId>
			<artifactId>mysql-connector-java</artifactId>
			<version>5.1.27</version>
		</dependency>
	</dependencies>

- Open the database configuration file : "Telosys Tools / databases.dbcfg"
- The database editor is displayed
- Add a new connection to your database
- Test the connection to get "Connection is OK"
- Click on "Information" tab and click on "Get database info" button to verify database connection
- Click on "Meta-data" tab and click on "Get tables" to see the tables of your database
- If all is OK, click on "Generate repository" button to generate a new ".dbrep" file in the "TelosysTools/repos" directory 

4. Generate source code
---

- Open the ".dbrep" file in the "TelosysTools/repos" directory
- Click on "Generate links from foreign keys" button which is located at bottom of the tab
- You can see now the links between all entities
- Click on the "Bulk generation" tab
- In the entities list, select an entity which must correspond to a table with no foreign key
- Select the "spring-mvc-jpa" templates bundle in the dropdown list => all templates are now visible in right list
- Select all templates and select "copy static resources"
- Click on the "Generate" button
- You should have a successfull message
- Wait for Maven which downloads all dependencies
- The project source code should compile successfully
- The "pom.xml" has been overrided during generation: fill "artifactId" and "name" in "pom.xml" with the name of your project

5. Database connection in the source files
---

- Open the "src/main/ressources/META-INF/config/database.properties" to configure the database connection
- Edit this file to enable the connection to your database from JPA/Hibernate

=> [Dialect list](http://www.javabeat.net/list-of-hibernate-sql-dialects/#)

6. Start the application
---

- In eclipse, add a Tomcat or another J2EE server
- Deploy the application on this server
- Start the server
- You should not have error message in the console view
- Open a Web navigator and tap this url : "http://localhost:8080/[application]", with "[application]" : the name of your webapp in eclipse
- The welcome page is now displayed in the web navigator and contains a link to manage only one entity
- Click on this link and next create a new entity
- Continue to create, modify, delete this entity in order to test the application
- Stop the server

7. Generate source code for all entities
---

- After testing the application for one entity, you can generate source code for all entities that you want to manage by this application
- For that, open the ".dbrep" file in the "TelosysTools/repos" directory
- Click on the "Links between entities" tab
- Click on "Generate links from foreign keys" button which is located at bottom of the tab
- You can see now the links between all entities
- Click on the "Bulk generation" tab
- In the entities list, select all entities
- Select the "spring-mvc-jpa" templates bundle in the dropdown list => all templates are now visible in right list
- Select all templates and select "copy static resources"
- Click on the "Generate" button
- You should have a successfull message
- The project source code should compile successfully
- The "pom.xml" has been overrided during generation: fill "artifactId" and "name" in "pom.xml" with the name of your project
- Open the "src/main/ressources/META-INF/config/database.properties" file to edit database connection for JPA/Hibernate
- Publish and Start the server
- In the web navigator, tap welcome page url "http://localhost:8080/[application]", with "[application]" : the name of your webapp in eclipse
- The welcome page is now displayed in the web navigator with a link for each entities
- Test your application
- You can now adapt this application as you wish

8. Remove Telosys Tools
---

- Delete the "TelosysTools" directory of your project
- Delete the "telosys-tools.cfg" file at the root of your project
- You have finished

