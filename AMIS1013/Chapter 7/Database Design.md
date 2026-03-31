# Database Concept (Manual)
![[Pasted image 20260319124324.png]]
# Database Concept (Computer)
- Database – consists of a number of files/tables.
- Table (File) – collection of related data records.
- Record – collection of related items of data fields.
- Field - contains one logical unit of data characters.
![[Pasted image 20260319124744.png]]
## Key Field
- Meaning - a field used to identify and differentiate one record from other records in a table.
#### Recommended:
Human – Use No. / ID
Transaction – Use No.
Item – Use No. / Code

| Master Files | Key Fields        |
| ------------ | ----------------- |
| Payroll      | Employee No. / ID |
| Customer     | Customer No. / ID |
| Stock        | Stock Code        |

| Transaction Files | Key Fields  |
| ----------------- | ----------- |
| Invoice           | Invoice No. |
| Purchase Order    | PO No.      |
| Payment           | Payment No. |
## Types of File/Table
- Transaction File - contains transaction records captured from business transactions which changes frequently with the latest transaction data eg. Purchase Order file contains details of a PO such as PO number, PO date. Examples: PO, SO, Invoice, Payment, RFQ, Quotation etc.
- Master File - contains relatively more permanent records in a table eg. a customer file will contain details of a customer such as customer ID, Name and Contact Address. Examples: Stock, Supplier, Student, Customer, Branches etc.
- Organisation File - contains organization data used to help set up the organization structure eg Company file contains details of a Company such as Company No, Name, Address.
# Types of Keys
![[Pasted image 20260319130903.png]]
## 1) Primary Key
### Definition
A field or a combination of fields that uniquely identifies a particular record of an entity. A primary key must be unique
### Examples
- Student Table - Student ID
- Borrow Table - Borrow No.
#### Student Table

| Student ID | Name        | Phome      |
| ---------- | ----------- | ---------- |
| WM23D01    | Tan Ah Meng | 0335454884 |
| WM22B12    | Lilian Wong | 0445982378 |
#### Borrow Table

| Borrow No. | Date     | Student ID |
| ---------- | -------- | ---------- |
| 000000017  | 24-12-23 | WM22B12    |
| 000000018  | 24-12-23 | WM23D01    |
## 2) Foreign Key
### Definition
A field in one table that must match a primary key of another table and borrowed.
### Purpose
To establish the relationship between two tables (entities)
![[Pasted image 20260319131548.png]]
- STUDENT (Student Number, Name, Address, Email, Telephone, Programme Code* )
- PROGRAMME (Programme Code, Programme Name, Type)
## 3) Foreign Key
![[Pasted image 20260319131937.png]]
## 3) Compound Key
### Definition
Created by combining the primary keys from two tables which have relations. Normally used in an associative entity.
### Purpose
Server as a primary key and used to link (connect) to other tables (ie foreign keys)
### Example
Student Number and Course ID
![[Pasted image 20260319133020.png]]
## 3) Compound Key
![[Pasted image 20260319133042.png]]
## Database Design Language (DBDL)
- One of the design tools used to represent a data table and its data elements (fields or attributes).
- ERD :
  ![[Pasted image 20260319133336.png]]
- DBDL : STUDENT (Student ID, Name, Address, Advisor No.* )
- DBDL Components :
	- – Entity (Table) Name – in CAPITAL letters.
	- Primary Key – first field or a combination of fields, to be underlined.
	- Non-Key Fields – other data fields describing other non-key fields.
	- Foreign Key (if any) – last field. Indicated with an asterisk ( * )
# Steps in Database Design
## 1) Create an initial ERD
Identify 2 entities which are related. This can be carried out using the first ‘activity’ or ‘process’.
![[Pasted image 20260319142022.png]]
## 2) Assign all data elements to entities
List key and non-key data in Database Design Language (DBDL) format.
![[Pasted image 20260319142051.png]]
Example (in DBDL format)
STUDENT (Student Number, Name, Address, Handphone)
BORROW (Borrow Number, Date, Student ID*)
## 3) Resolve any many-to-many relationship
## 4) Relating the Entities by using foreign keys
![[Pasted image 20260319142213.png]]
STUDENT (Student ID, Name, Address, Handphone)
BORROW (Borrow Number, Date, Student ID*)
BOOK (Book Code, Title, Edition, Year-Published)
BORROWLINE (Book Code*, Borrow Number*, Qty)
## 5) Creating data dictionary entries
Data dictionary – details about each data field.
Software tools – eg. Oracle, DB2 can be used.
# Data Dictionary
## Example of Data Dictionary Format
