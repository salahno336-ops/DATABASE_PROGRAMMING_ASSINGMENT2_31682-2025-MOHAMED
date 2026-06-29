# DATABASE_PROGRAMMING_ASSINGMENT2_31682-2025-MOHAMED

# Individual Assignment II: Oracle Pluggable Database (PDB) Administration

## 1. Assignment Overview
The objective of this assignment is to demonstrate practical skills in Oracle Multitenant Architecture, specifically focusing on creating, configuring, and managing Pluggable Databases (PDBs), user administration, and environment documentation.

## 2. Oracle Environment
* **Oracle Version Used:** Oracle Database 19c / Free Edition
* **Operating System:** Windows 11
* **Tools Used:** SQL*Plus, Oracle Enterprise Manager (OEM) Express, GitHub

## 3. Task Documentation
* **PDB Creation Process:** Successfully created `al_pdb_31682` from the CDB seed by mapping the correct local directory path `D:\ORACLE\ORADATA\FREE\PDBSEED\`, and altered its state to OPEN.
* **User Creation Process:** Switched container session to `al_pdb_31682`, created the local database user `ali_plsqlauca_31682`, and successfully granted CONNECT, RESOURCE, and DBA privileges.
* **Temporary PDB Management:** Created `al_to_delete_pdb_31682`, verified its status in the container list, closed the instance, and dropped it completely including all associated datafiles.

## 4. Challenges, Solutions, and System Reporting
* **Challenge 1 (File Name Convert Error):** Received `ORA-65005` during PDB creation due to invalid file path pattern.
  * *Solution:* Explicitly provided the absolute local system path `D:\ORACLE\ORADATA\FREE\` inside the `FILE_NAME_CONVERT` clause.
* **Challenge 2 (Listener and Network Connectivity - Oti/OEM Issue):** Received `ORA-12514` (Service not registered with the listener) when attempting to establish a connection using the standard TCP/IP network connection string (`localhost:1521`). Additionally, the Oracle Enterprise Manager (OEM) port/service did not launch or function correctly within this local environment setup.
  * *Solution/Report:* To bypass the listener failure and the non-functional OEM service, a direct local session container swap was performed using `ALTER SESSION SET CONTAINER = al_pdb_31682;` followed by an internal user connection authentication block, which successfully authorized the account.

## 5. Lessons Learned
Gained deep hands-on experience with Oracle Multitenant Architecture, container switching, user isolation within PDBs, handling local listener mapping errors, and cloud-ready database administration basics.

## 6. Integrity Statement
I confirm that this assignment represents my own practical work, screenshots, and documentation. All external resources consulted have been properly acknowledged.
