spring-mvc-jpa-templates-TT207
==============================

Spring MVC + JPA templates for Telosys Tools v2.0.7

Description
----------

These templates generates J2EE web application based on Spring MVC, Spring IOC, Spring Data and JPA.
Bootstrap v3 and JQuery are used in front-end pages for reponsive design and navigators compatibility.

The main objective is to respect the guidelines and the best practices in J2EE Web applications development.

For that, unit and integration tests are generated. The integration tests can used in-memory Sql database or a real testing database.

The application manages each entity with CRUD (Create, Read, Update, Delete) operations.

Architecture
---

Presentation layer: 
- Spring MVC, JSPX Pages, Jquery, Bootstrap

Business logic layer: 
- Services injected by Spring IOC

Database Access Objects layer: 
- Java Persistance API, Spring Data

Requirements
---

You need to download :
- Eclipse Kepler
- Telosys Tools version 2.0.7 plugin for Eclipse
- M2eclipse for Kepler (with WTP support)

Steps
---

1 In eclipse, create new "Maven Project"
2 In "New Manen Project" wizard, select "Create a simple project (skip archetype selection)"
3 Click "Next"
4 Define "Group Id", "Artifact Id"
5 Select "war" for "Packaging"
6 Click "Finish"
7 The new project is added in the workspace
8 Open the properties window of this new project
9 In the left entries, select "Telosys Tools"
10 Fill all project informations and Click on "init Telosys Tools"
11 The "Telosys Tools" directory is now added to the project
12 Click on the "download" panel of Telosys Tools properties windows
13 Download from this Github repository the "spring-mvc-jpa-templates"
14 Close the project properties winodow
15  

How to use it
---

Open 
Use all templates of "spring-mvc-jpa-templates-TT207"
Select 