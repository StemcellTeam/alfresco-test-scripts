-----------
DESCRIPTION
-----------
Test scripts performed using the Selenium Firefox driver for basic Alfresco actions such as adding users, CRUD operations and search functionality. 

Selenium Web-driver
------------------

Selenium Web-driver is a tool developed to write automation scripts to test websites. Web-driver was first introduced in Selenium 2.0. The main feature of Web-driver is that it is able to drive a web browser by interacting with the HTML  similar to how a user would handle it. Currently Selenium-WebDriver is fully implemented and supported in Python, Ruby, Java and C#.

Following are the Alfresco basic functionality covered 
------------------------------------------------------

1. Login and Logout
2. Creating, deleting and editing a user.
3. Customising the dashboards.
4. Inviting internal and external user.
5. Creating user group.
6. Uploading, deleting and viewing documents.
7. Manage document permissions.
8. Checking the functionality of site searching.

-------------------------
Installation Instructions
-------------------------

1. Install Java 1.8
2. Install Maven
3. Git clone alfresco-test-scripts to your local computer 
4. Update pom.xml(alfresco-test-scripts/ABFT_4_2/pom.xml) with the latest selenium-java version
   You can find the latest version information here - http://mvnrepository.com/artifact/org.seleniumhq.selenium/selenium-java
     ```
	<dependency>
        	<groupId>org.seleniumhq.selenium</groupId>
        	<artifactId>selenium-java</artifactId>
        	<version>2.433.1</version>
     	</dependency>
     ```
5. Update pom.xml(alfresco-test-scripts/ABFT_4_2/pom.xml) with the latest Junit version
   Can find the latest version information here - http://mvnrepository.com/artifact/junit/junit
     ```
	<dependency>
		<groupId>junit</groupId>
		<artifactId>junit</artifactId>
		<version>4.11</version>
     	</dependency>
     ```
6. All the test cases related test data(test values) you can set it in the TestValues.xml file.
   Location - alfresco-test-scripts/ABFT_4_2/src/test/resources/TestValues.xml
7. Set Alfresco server URL
   Go to alfresco-test-scripts/ABFT_4_2/src/test/resources/TestProperties.xml
   And add the correct server URL Example: 
	```
	<ServerUrl>http://localhost:8080/share/page/</ServerUrl>
	```
8. Set Alfresco Admin username and password 
   Go to alfresco-test-scripts/ABFT_4_2/src/test/resources/TestProperties.xml
     <AdminUsername>admin</AdminUsername>
     <AdminPassword>admin</AdminPassword>
9. Make sure that the document that you will be using for Upload Test Case is available in your computer and Finder Window has List/Icon View (NOT Column View)
    Go to alfresco-test-scripts/ABFT_4_2/src/test/resources/TestValues.xml
    ```
	<DocumentLibraryTest>
		<test>
			<siteName>Test Site 5</siteName>
			<siteId>test-site-5</siteId>
			<documentName>AbftsUploadTest.txt</documentName>
			<userName>test</userName>
		</test>
	</DocumentLibraryTest>
	```
10. Start Alfresco server (local or remote, depending on your test xml configs)
11. Go to alfresco-test-scripts/ABFT_4_2 via terminal
12. Run <code>mvn test</code> to build and run the test cases


----
Note
----

Alfresco basic functionality automation test-scripts fully tested on:

1. Alfresco 4.2+ server (Tested up to 5.0.1.0) 
2. Firefox browser
3. Mac OSX 10.10 (other versions not tested)
