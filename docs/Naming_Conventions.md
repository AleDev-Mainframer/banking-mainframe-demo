# Nomenclatures in Demo Banking Systems.

This document describes the naming conventions used for the different types of components within the system.
In real banking environments, it is usually mandatory to follow specific naming standards whenever new components are developed.

The naming convention depends on the type of component being created.
Remember that in IBM z/OS Mainframe environments, components names such as JCLs, COBOL Programs, and COPYBOOKs are limited to 8 characters.

## 1) COPYBOOKS - TEMPLATES:
We can have two types of TEMPLATES in Host Mainframe:
1- COPYs - The most common template used for files allocated in Mainframe.
2- DCLGEN - Kind of template that is useful for generate data relationship between DB2 TABLES and COBOL PROGRAMS.

For this project, the following naming convention will be used for COPYBOOKs.

*EXAMPLE:*

**CD + CB + EX + E + 0**

- CD - Banking Sector ('CD' Cards).
- CB - Online or Batch template ('CB' CopyBook / 'DG' DCLGEN).
- EX - Copy for External or Internal file.
- E  - Input File ('I' Internal / 'E' External).
- 0  - Component Versioning.

In this example, the COPYBOOK represents an external file received through a transfer process. The file serves as an INPUT for a Card Department procedure within the Banking environment.

Therefore, the component name will be:
**CDCBEXE0**

## 2) JOBs (JCL):

JCL components will be named following a convention similar to the one used for COPYBOOKs, with a few differences.

*EXAMPLE*

**BK + CD + TF + V + 0**

- BK - Banking Main Environment
- CD - Banking Sector ("CD" = Cards)
- TF - First Job Identifier. It should be descriptive, for example: "TF" (Transfer), "AC" (Accounting), "M1" (Module 1), etc.
- V  - Second Job Identifier. In this example, "V" is used for versioning purposes.
- 0  - Component Version.

The resulting component name for this example is:

**BKCDTFV0**

## 3) COBOL Programs

COBOL programs follow a naming convention similar to JCL components, with a few differences.

*EXAMPLE*

**CD + CB + ST + V + 0**

- CD - Banking Sector ("CD" = Cards)
- CB - Program Type ("CB" = COBOL, "AS" = Assembler)
- ST - First Descriptive Identifier, for example: "ST" (Settlements)
- V  - Second Identifier. In this example, "V" is used for versioning purposes, although it may also represent a common identifier shared by programs belonging to the same module.
- 0  - Component Version.

The resulting component name for this example is:

**CDCBSTV0**
