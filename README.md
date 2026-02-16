# oracle_pdb_ass_II_29178_Angel

## About This Project
This repository contains my practical work for **Assignment II** of the course **Database Development with PL/SQL (INSY 8311)**. The assignment required hands-on management of Oracle Pluggable Databases (PDBs) using Oracle 21c and SQL Developer.

---

## Student Details
- **Name:** KAYITARE KEZA Angel  
- **Student ID:** 29178  
- **Group:** D — Thursday Evening  
- **Instructor:** Eric Maniraguha  
- **Deadline:** February 16, 2026  

---

## Environment
- **Database:** Oracle 21c  
- **OS:** Windows 11  
- **Tool:** Oracle SQL Developer  

---

## What I Did

### Task 1 — Setting Up My Personal PDB
The goal here was to create a pluggable database that I will use throughout the semester for all PL/SQL work.

**PDB Name:** `ka_pdb_29178`  
**User Created:** `kayitare_plsqlauca_29178`

I created the PDB from the seed, opened it, and then created my personal user account inside it with the necessary privileges.

![pdb_creation](https://github.com/user-attachments/assets/025b419c-9924-41e5-9791-209957bf5958)

![open_pdb](https://github.com/user-attachments/assets/314788bd-68c4-4482-9a7c-be9a69513085)

![create_user_pdb](https://github.com/user-attachments/assets/b68286da-6024-4e8e-9a7d-bd47177139b0)

![confirm_user_pdb](https://github.com/user-attachments/assets/82d6555d-9aeb-435c-b581-4c864a18803b)

---

### Task 2 — Creating and Removing a Temporary PDB
This task demonstrated my ability to fully manage a PDB lifecycle — from creation to complete removal.

**Temporary PDB Name:** `ka_to_delete_pdb_29178`

I created the temporary PDB, confirmed it existed, then dropped it completely including all its data files, and verified it was gone.

![create_temp](https://github.com/user-attachments/assets/56da0744-2f21-41cb-8798-117975cd64c6)

![verify_temp](https://github.com/user-attachments/assets/43d91e8b-5950-4779-a995-1c1166f70a51)

![drop_temp](https://github.com/user-attachments/assets/bf6e0ee2-9bf9-405b-8bbf-d71aaa432c66)

![confirm_temp_deletetion](https://github.com/user-attachments/assets/fc32eced-a872-4085-b322-b66dbcaac1e7)

---

### Task 3 — Oracle Enterprise Manager (OEM)
I accessed the OEM dashboard through the browser at `https://localhost:5500/em` and verified that my Oracle environment and PDBs were visible.

![OEM Dashboard 1](https://github.com/user-attachments/assets/99595231-daf2-4cd2-a549-95d47d5b58ba)

![OEM Dashboard 2](https://github.com/user-attachments/assets/2e58e333-386f-4bb9-ad63-c6083eabbfa2)

---

## Challenges I Faced

**1. Permission error when deleting Oracle folders**  
During installation setup, I could not delete leftover Oracle folders even as an administrator. The fix was to stop all running Oracle services from `services.msc` first, then delete the folders using Command Prompt with administrator rights.

**2. Oracle service conflicts**  
Existing Oracle services were conflicting with the new installation. I had to manually stop each Oracle-related service before proceeding with a clean reinstall.

---

## Commands Reference

```sql
-- Create the PDB
CREATE PLUGGABLE DATABASE ka_pdb_29178
ADMIN USER ka_admin IDENTIFIED BY [password];

-- Open it
ALTER PLUGGABLE DATABASE ka_pdb_29178 OPEN;

-- Save state
ALTER PLUGGABLE DATABASE ka_pdb_29178 SAVE STATE;

-- Switch into PDB
ALTER SESSION SET CONTAINER = ka_pdb_29178;

-- Create user
CREATE USER kayitare_plsqlauca_29178 IDENTIFIED BY [password];

-- Grant privileges
GRANT CONNECT, RESOURCE, UNLIMITED TABLESPACE TO kayitare_plsqlauca_29178;

-- Create temp PDB
CREATE PLUGGABLE DATABASE ka_to_delete_pdb_29178
ADMIN USER temp_admin IDENTIFIED BY [password];

-- Drop temp PDB
DROP PLUGGABLE DATABASE ka_to_delete_pdb_29178 INCLUDING DATAFILES;
```

---

## Integrity Statement

I confirm that all the work in this repository was done by me personally. All commands were executed on my own machine and all screenshots reflect my own Oracle environment. I did not copy or share work with any other student.

**KAYITARE KEZA Angel | 29178 | INSY 8311 | February 2026**


---

## Final Checklist (Apply Before Submission)

- [x] **Correct PDB names used **

- [x] **User created inside the PDB**
 
- [x] **Temporary PDB created and deleted**

- [x] **OEM dashboard screenshot included**
 
- [x] **GitHub repository is PUBLIC**
 
- [x] **README is clear and professional**
 
- [x] **Deadline respected**

---

**Repository Link**: [GitHub URL]

**PDB Name Created**: ka_pdb_29178

**Issues Encountered**: Yes
