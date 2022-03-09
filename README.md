# Tomcat installatin : ..
sudo yum install tomcat tomcat-webapps tomcat-admin-webapps tomcat-docs-webapp tomcat-javadoc -y

**# java-tomcat-maven-example
Prerequisites:**

Edit /usr/share/tomcat/conf/tomcat-users.xml/tomcat-users.xml in tomcat ::

	<role rolename="tomcat"/>
	<role rolename="admin-script"/>
	<role rolename="manager-script"/>
	<role rolename="manager-gui"/>
	<role rolename="manager-jmx"/>
	<role rolename="manager-status"/>
	<role rolename="manager"/>
	<role rolename="admin"/>
	<user password="password" roles="tomcat" username="admin"/>
	<user password="password" roles="manager-gui" username="admin"/>
	<user password="password" roles="admin,admin-script,manager-gui,manager-script,manager-jmx,manager-status" username="admin"/>

Edit /etc/maven/settings.xml in maven ::

	<server>
	<id>TomcatServer</id>
	<username>admin</username>
	<password>password</password>
	</server>
	<server>     
	<id>nexus-site</id>
	<username>admin</username>
	<password>dba1e994-b90d-498f-88fd-7b9ee8291627</password>
	</server>

---------------------------------
**Automation:**
Deploying Project War files to Tomcat using Maven ::

	mvn install tomcat7:deploy

--------------------------------
**Automation:**
Deploying Project snapshots to nexus using Maven ::

	mvn clean deploy
