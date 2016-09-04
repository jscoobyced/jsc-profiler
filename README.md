# JSC Profiler
## Overview
Manage people profile by collecting information about them. This application
can be helpful for manager to keep their team profile.   
It is a KnockoutJS based application, backed by a SQLite database. It can be easily modified to use any JDBC enabled DB.

## Installation
### Eclipse
* Download Eclipse NEON for Java EE developer:  
   Linux 
[32 bits](https://eclipse.org/downloads/download.php?file=/technology/epp/downloads/release/neon/R/eclipse-jee-neon-R-linux-gtk.tar.gz) or
[64 bits](https://eclipse.org/downloads/download.php?file=/technology/epp/downloads/release/neon/R/eclipse-jee-neon-R-linux-gtk-x86_64.tar.gz)  
   Windows 
[32 bits](https://www.eclipse.org/downloads/download.php?file=/technology/epp/downloads/release/neon/R/eclipse-jee-neon-R-win32.zip) or
[64 bits](https://www.eclipse.org/downloads/download.php?file=/technology/epp/downloads/release/neon/R/eclipse-jee-neon-R-win32-x86_64.zip)  
   Main download page 
[Eclipse](https://eclipse.org/downloads/eclipse-packages/)
* Install a few eclipse plugins:  
[Buildship Gradle Integration](https://marketplace.eclipse.org/content/buildship-gradle-integration)  
[JS Hint](https://marketplace.eclipse.org/content/jshint-eclipse)  
[Markdown Text Editor](http://marketplace.eclipse.org/content/markdown-text-editor)  

### Glassfish

* Download and install GlassFish (suggested 4.1.1 or above):    
[Main Download Page](https://glassfish.java.net/download.html)  
* Add the <Glassfish_Home_Folder>/glassfish/bin to your PATH  

* Download and copy **sqlite-jdbc-3.8.11.2.jar** to <Glassfish_Home_Folder>/glassfish/domains/domain1/lib/ext/ folder
* Create a new JDBC Connection pool (replace **/home/cedric/workspace/sqlite.db** with any preferred path
```
asadmin create-jdbc-connection-pool --datasourceclassname org.sqlite.SQLiteDataSource --restype javax.sql.DataSource  --property url="jdbc\:sqlite\:/home/cedric/workspace/sqlite.db" ProfilerPool  
```
* Create a new JDBC Resource
```
asadmin create-jdbc-resource --connectionpoolid ProfilerPool jdbc/ProfilerPool
```