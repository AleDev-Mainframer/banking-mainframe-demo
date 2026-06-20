# Functional Analysis - Card Transactions Reporting Process

## 1. Objective

The purpose of this process is to receive a daily card transactions file and generate a control report containing transaction information grouped by merchant.

This process is intended as a demonstration of a typical IBM Mainframe batch application using COBOL, JCL, COPYBOOKs and VSAM files.

---

## 2. Scope

The process includes:

* Reception of an external input file.
* Validation of file structure.
* Processing of transaction records.
* Merchant information lookup.
* Generation of a reporting file.
* Generation of control statistics.

The process does not perform accounting movements or database updates.

---

## 3. Input Files

### Daily Transactions File

The input file is received from an external source.

File Structure:

* Header Record
* Detail Records
* Trailer Record

The detail records contain card transaction information.

Example:

H2026062000000005

D000001000001000001500

D000001000002000002200

D000002000001000003500

T0000000003

---

## 4. Reception Process

A JCL component is responsible for receiving and validating the input file.

The process performs the following validations:

* Header record exists.
* Trailer record exists.
* Record count matches trailer information.
* File is not empty.

If any validation fails, the process ends with an error condition.

---

## 5. Processing

A COBOL batch program reads the input file sequentially until End Of File.

For each transaction:

* Merchant information is retrieved from a VSAM file.
* Transaction counters are updated.
* Transaction amounts are accumulated.

---

## 6. Output Files

### Reporting File

The reporting file contains summarized information by merchant.

Example fields:

* Merchant Code
* Merchant Name
* Transaction Quantity
* Total Amount

### Control Report

The control report contains:

* Records Read
* Records Processed
* Records Rejected
* Total Amount Processed

---

## 7. VSAM Master File

A VSAM file is used to store merchant information.

The primary key is:

* Merchant Code

Example information:

* Merchant Name
* Merchant Category
* Merchant Status

---

## 8. Expected Result

The process generates a summarized report of daily card transactions and control information that can be used for operational monitoring purposes.
