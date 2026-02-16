# oracle_pdb_ass_II_29146_Ihozo_Meg


## 
Repository Link: https://github.com/megihozo69-beep/oracle_pdb_ass_II_29146_Ihozo_Meg

PDB Name Created: [me_pdb_29146]

Issues Encountered:

--

## Overview

This assignment involved working with Oracle Database 21c using the multitenant architecture. The tasks included creating and managing Pluggable Databases (PDBs), creating users inside the PDB, deleting a temporary PDB, and accessing Oracle Enterprise Manager (OEM) to monitor the database environment. The assignment demonstrates practical skills in database administration and PDB management.


## Oracle Environment Used

- Oracle Database Version: 21c
- Tool Used: SQL Developer
- OEM: Oracle Enterprise Manager Express

                               Task1
  Create a New Pluggable Database

A new Pluggable Database (PDB) was created following the required naming convention. The PDB was opened in READ WRITE mode, and a local user was created inside it with the necessary privileges for future coursework.
reating a pluggable database here:

this is for creating PDB:
create PLUGGABLE DATABASE me_pdb_29146
ADMIN USER pdbadmin IDENTIFIED BY admin
FILE_NAME_CONVERT = ('pdbseed','me_pdb_29146');
                         
                         creating the user in our PDB

CREATE USER meg_plsqlauca_29146 IDENTIFIED BY auca;

-- so to be sure about your user you created just we find it using:
SELECT username FROM dba_users WHERE username = 'MEG_PLSQLAUCA_29146';

                          task 2
                          
## overview

A temporary PDB was created using the specified naming format. Its existence was verified, then it was properly closed and deleted completely, including its data files. Final verification confirmed that the PDB no longer existed. 

firstly we created a temporary PDB as, 

CREATE PLUGGABLE DATABASE be_to_delete_pdb_28840
ADMIN USER MEG_PLSQLAUCA_29146 IDENTIFIED BY admin
FILE_NAME_CONVERT = ('pdbseed','me_to_delete_pdb_29146');

verifying if it was created
select name from v$pdbs;
 
 After we have to make our PDB open by
 ALTER PLUGGABLE DATABASE me_to_delete_pdb_29146 OPEN;
 
Dropping an existing PDB we do:

DROP PLUGGABLE DATABASE me_to_delete_pdb_29146 INCLUDING DATAFILES;

but before dropping it completely we have to close first our PDB we open before:
ALTER PLUGGABLE DATABASE me_to_delete_pdb_29146 CLOSE IMMEDIATE;




                         task 3
Oracle Enterprise Manager Express was configured and accessed through the browser. The dashboard was used to verify the Oracle environment, confirm the created PDB, and display the user account created inside the PDB. as shown below in the image this is display out of that browser where you login from.


<img width="955" height="424" alt="task3 " src="https://github.com/user-attachments/assets/370804d4-2af8-4681-8825-c8f4d23d0146" />



                         Conclusion

This tasks improve understanding of Oracle Multitenant Architecture, PDB lifecycle management, user administration, and Oracle Enterprise Manager monitoring.
