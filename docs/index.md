# Security Model Automation Remediation Tool (SMART)

##Links

DBM ID: [APP-8643](https://carta.xom.com/CARTA/Application.aspx?alfa_param=0W3z2pufeI3h5Vit2ZLi5pYHjasdzAM73JRM76RbMtHMwtDtuiAiW8YxCbdXmb2ekYxVY7IYIAqlxSes9f4sKT1QlijvFj3CfMbVe8fApCGVIs61TV8ogkKXiq%2BPkRT2Mjq0ENK43E7vvb5aXhBixQ%3D%3D)

Production: [http://goto/onpremiaas](http://goto/onpremiaas)

Development: [http://goto/onpremiaasdev](http://goto/onpremiaas)


---

## Scope of the Security Model and Environment

Application that enable the customer to apply/enforce Windows Local Groups permissions on their servers.

- Windows 2012 and higher.

## Referenced Other Pratices

---
[Mulesoft APIs Best Pratices](https://anypoint.mulesoft.com/exchange/a31966b0-fc4e-4ac8-af23-c40fc73ce072/how-to---things-you-should-know/)

[Publish API to openshift](https://anypoint.mulesoft.com/exchange/a31966b0-fc4e-4ac8-af23-c40fc73ce072/continuous-integrationdelivery-pipeline-overview/)

[DBAM Documentation](http://goto/dbamdocs)

## Server Roles

---

### Production

|Server Role|Server Names|Location|Description of Role|Machine Group Membership|
|:---:|:---:|:---:|:---:|:---:|
|Database Server|HOESQL041|Houston / NA / Standard Server|Host Production Database| - |
|---|---|---|---|---|

<br>
### Acceptance/Development

|Server Role|Server Names|Location|Description of Role|Machine Group Membership|
|:---:|:---:|:---:|:---:|:---:|
|Database Server|HOESQL042|Houston / NA / Standard Server|Host Development Database| - |
|Database Server|HOESQL1611|Houston / NA / Standard Server|Host Development Database| - |
|---|---|---|---|---|

<br>
## **Security Configuration for the Production Environment**

### Roles and Associated Domain Accounts

|Account Role|Owner|Scope of Role|Member of|
|:---:|:---:|:---:|:---:|
|NA\xswinge|DCC1|Mulesoft API / Database Server|-|
|NA\xswingeprd|DCC1|Mulesoft API / Database Server|-|
|---|---|---|---|

<br>
**Purpose & Potential Exposures:** Services Account ID that grants read access to the app-secmodel-data database.

**Potential Exposures:** None.

### **Domain Global Groups**

|Group Role|Owner|Scope of Role|Member of|
|:---|:---|:---|:---|
|NA\DCC-WINDOWS-VRA.UG|DCC1|To add as support group. Members of this group will be able to use the “on behalf” option on VRA. It contains the TA accounts (privileged accounts) of Windows teams. For now keep the minimal number of analysts that are effectively working in this new process|-|
|NA\DCC-WINDOWS-VRA-TESTERS.UG|DCC1|To add as end user group. Members of this group will be the users and record owners participating in the pilot. Contains their LAN IDS|-|
|---|---|---|---|

<br>
### **Server Local Accounts**

None.

### **Server Local Groups**

None.

### **Services**

None.

### **Folder / Share Permissions**

None.

### [**Databases Roles**](https://docs.microsoft.com/en-us/sql/relational-databases/security/authentication-access/database-level-roles?view=sql-server-ver15)

|Database Role|Description|
|:---:|---|
|db_accessadmin|Members of the db_accessadmin fixed database role can add or remove access to the database for Windows logins, Windows groups, and SQL Server logins.|
|db_backupoperator|Members of the db_backupoperator fixed database role can back up the database.|
|db_datareader|Members of the db_datareader fixed database role can run a SELECT statement against any table or view in the database.|
|db_datawriter|Members of the db_datawriter fixed database role can add, delete, or change data in all user tables.|
|db_ddladmin|Members of the db_ddladmin fixed database role can run any Data Definition Language (DDL) command in a database.|
|db_denydatareader|Members of the db_denydatareader fixed database role cannot read any data in the user tables within a database.|
|db_denydatawriter|Members of the db_denydatawriter fixed database role cannot add, modify, or delete any data in the user tables within a database.|
|db_owner|Members of the db_owner fixed database role can perform all configuration and maintenance activities on the database, and can also drop the database in SQL Server. (In SQL Database and SQL Data Warehouse, some maintenance activities require server-level permissions and cannot be performed by db_owners.)|
|db_securityadmin|Members of the db_securityadmin fixed database role can modify role membership for custom roles only and manage permissions. Members of this role can potentially elevate their privileges and their actions should be monitored.|
|public|Every database user belongs to the public database role. When a user has not been granted or denied specific permissions on a securable object, the user inherits the permissions granted to public on that object. Database users cannot be removed from the public role.|

<br>
### **Database Permissions**

None.

### **Database Jobs**

None.

### **Computer and/or User Group Policy Objects**

None.

### **Registry Modifications**

None.

### **Middleware Settings - IIS Virtual Directories**

None.

### **Scheduled Tasks**

None.

### **ECM Monitoring**

None.

---
### **Security Configuration for the Acceptance / Development Environment**

### Roles and Associated Domain Accounts

|Account Role|Owner|Scope of Role|Member of|
|:---:|:---:|:---:|:---:|
|NA\xswinge|DCC1|Mulesoft API / Database Server|-|
|---|---|---|---|

<br>
**Purpose & Potential Exposures:** Services Account ID that grants read access to the app-secmodel-data database.

**Potential Exposures:** None.

### **Domain Global Groups**

|Group Role|Owner|Scope of Role|Member of|
|:---|:---|:---|:---|
|NA\DCC-WINDOWS-VRA.UG|DCC1|To add as support group. Members of this group will be able to use the “on behalf” option on VRA. It contains the TA accounts (privileged accounts) of Windows teams. For now keep the minimal number of analysts that are effectively working in this new process|-|
|NA\DCC-WINDOWS-VRA-TESTERS.UG|DCC1|To add as end user group. Members of this group will be the users and record owners participating in the pilot. Contains their LAN IDS|-|
|---|---|---|---|

<br>
### **Server Local Accounts**

None.

### **Server Local Groups**

None.

### **Services**

None.

### **Folder / Share Permissions**

None.

### [**Databases Roles**](https://docs.microsoft.com/en-us/sql/relational-databases/security/authentication-access/database-level-roles?view=sql-server-ver15)

|Database Role|Description|
|:---:|---|
|db_accessadmin|Members of the db_accessadmin fixed database role can add or remove access to the database for Windows logins, Windows groups, and SQL Server logins.|
|db_backupoperator|Members of the db_backupoperator fixed database role can back up the database.|
|db_datareader|Members of the db_datareader fixed database role can run a SELECT statement against any table or view in the database.|
|db_datawriter|Members of the db_datawriter fixed database role can add, delete, or change data in all user tables.|
|db_ddladmin|Members of the db_ddladmin fixed database role can run any Data Definition Language (DDL) command in a database.|
|db_denydatareader|Members of the db_denydatareader fixed database role cannot read any data in the user tables within a database.|
|db_denydatawriter|Members of the db_denydatawriter fixed database role cannot add, modify, or delete any data in the user tables within a database.|
|db_owner|Members of the db_owner fixed database role can perform all configuration and maintenance activities on the database, and can also drop the database in SQL Server. (In SQL Database and SQL Data Warehouse, some maintenance activities require server-level permissions and cannot be performed by db_owners.)|
|db_securityadmin|Members of the db_securityadmin fixed database role can modify role membership for custom roles only and manage permissions. Members of this role can potentially elevate their privileges and their actions should be monitored.|
|public|Every database user belongs to the public database role. When a user has not been granted or denied specific permissions on a securable object, the user inherits the permissions granted to public on that object. Database users cannot be removed from the public role.|

<br>
### **Database Permissions**

None.

### **Database Jobs**

None.

### **Computer and/or User Group Policy Objects**

None.

### **Registry Modifications**

None.

### **Middleware Settings - IIS Virtual Directories**

None.

### **Scheduled Tasks**

None.

### **ECM Monitoring**

None.
