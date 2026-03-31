## What is System Design
##### Purpose
- Design shows how the system will fulfill what the system should do
##### Output
- Design translates the System Requirements Spec into a 'blueprint' called System Design Specification.
##### Person
- Designer details the system specifications
##### Areas 
- ISs may have many possible designs eg database, forms, security, interfaces (input,output), procedures reports etc.
## Importance of Design
##### Maintenance
- It provides necessary 'roadmap' and documentation for maintenance staff.
##### Quality
- Quality of design affects quality of software. A good design produces a quality software
##### Testing
- Design outputs (eg Design Spec) provide the necessary criteria for testing of the software.
##### Communication
- It serves as a communication medium between the designers of sub-systems eg between Purchasing and Warehousing systems.
##### Development
- Design will be developed (programmed) into a software
## Overview Areas of Design
![[Pasted image 20260317221559.png]]
## Physical and Logical Design
### Logical Design
- Phase - Developed during the system analysis phase.
- Focus - Describes the functions and features of the system (eg. input, process, output) that must be performed.
- Design - Defines what functions must be carried out eg what data to input.
### Physical Design
- Phase - Developed during the systems design phase.
- Focus - Describes the actual physical processes of entering (eg barcode), verifying and storing data.
- Design - Defines how the functions will be implemented physically eg use of barcode for input
## Exercise for Student
![[Pasted image 20260317221945.png]]
## Overview of Models Used in Design Stage
![[Pasted image 20260317222016.png]]
# System Architecture Design
### Meaning
- Shows an overall architectural design structure of the entire system consisting of both internal systems, external systems and hardware (server, clients and network infrastructure), and their relationship between them.
### Purpose
- To ensure that the design of the entire system is more structured, and hence enhancing the development and future maintenance process
## Example 1 – Architecture Design for a Purchasing System
![[Pasted image 20260317222250.png]]
# System Structure Design
### Meaning
- Shows the design structure of an internal system, consisting of various modules and how they are related (eg. information flow) to each other.
### Purpose
- To design a more structured system (eg. high modularity and low coupling) to enhance development and maintenance process.
## Example 1 – Accounting System Structure
![[Pasted image 20260317222449.png]]
# System Function Design
![[Pasted image 20260317222514.png]]
## Functional Decomposition Diagram (Structure Charts)
### Design Tool  
- FDD is a design tool used for a top-down representation of a system and its modules.
- Each module contains many functions or processes
- DFD can be used to draw the Structure Chart.
  Context Diagram represents the whole system while the low-level DFD represents the modules.
![[Pasted image 20260317222653.png]]
- FDDs can be used at several stages of systems development.
	- During analysis phase - FDDs are used to identify business functions
	- During design phase - FDDs show how the DFDs are organized into lower-level modules (processes).
	- During development phase - The processes can be translated into program codes.
# Example 1 - CRM (FDD)
![[Pasted image 20260317222856.png]]
# Example 2 - ERP 
![[Pasted image 20260317222915.png]]
# Example 3 - Library System
![[Pasted image 20260317222931.png]]
# Example 4 - Leisure Club System
![[Pasted image 20260317222947.png]]
# Steps of Decomposition
1) Identify the process eg. Inventory system consists of : Receive Goods, Distribute Goods, Issues Goods, Return Goods.
2) Group related activities that need to be performed for each process to form a sub-system eg. for sales system: answer enquiries, create quotation, receive order etc.
   ![[Pasted image 20260317223257.png]]
# User Interface Design
### Meaning
- The way users interact with the system when using it
### 2 Ways
- Hardware
- Software
# Types of User Interface
1) Command-line Interface
2) Menu-Driven Interface
3) Improved Menu Interface
	1) Pop-up Menu
	2) Pull-down and Cascading Menu
4) Toolbar and Icon-Based Interface (Similar with Microsoft Office)
5) Form-based Interface
6) Natural Language Interaction
	1) English may be used to interact with the computer system
	2) It allows users to enter questions and commands, and produce outputs in their native language
	3) Examples - Database queries, voice entry systems.
# Examples of Input Devices Used
- Keyboard
- Mouse
- Touch Screen
- Graphics Tablet
- Light Pen
- Voice
- Scanners / Readers
- Sensors
# User-Friendliness Characteristics
## 1) Ease of Data Entry
1) Data entry screen in the same logical order as the input form.
2) Clearly designed, input fields are highlighted, by color, flashing or reverse coloring.
3) Clear titles of fields
4) Provision of data validation checks in order to reduce potential human data entry errors.
## User Interface Controls
![[Pasted image 20260318142747.png]]
## 2) Meaningful Error Messages
- Errors are reported, simple, unambiguous, suggest a course of action.
- Example of poor error message
  ![[Pasted image 20260318142921.png]]
- Example of good error message
  ![[Pasted image 20260318143117.png]]
## 3) HELP Facilities
- On-screen help
- Types of Help: context specific; hypertext and hypermedia.
- Context Sensitive Help
	- Help users are unsure to perform a certain function, or made an error.
	- Illustrate with an example on the application of the command
	- Include a mechanism to allow users to recover from their errors.
## 4) Consistent with Other Modules
-  Modules of a system ‘look and feel’ and operate in similar way.
- Examples : F1 = ‘Help’, F2 = ‘Save’ etc
### Advantages
- Facilitate 'transferable’ skills which increase productivity
- Cost saving due to reduced training time
## 5) Adherence to Industry Standards
- Use commands and techniques that are used in other software applications.
- Advantages - Facilitate ‘transferable’ skills which increase productivity users.
## 6) Escapability (Forgiving)
- Users may make mistakes when using or learning to use system.
- System response – Esc or undo keys, message ‘continue or cancel’.
## 7) Other User-Friendliness Features
- Pull-Down List
- Default Value eg system date, tax rate, discounts, suppliers
- Radio Buttons/Checked Boxes
- Validation Checks eg. data type check 
- Automated Inputs eg scanning, reading, sensing
## 8) Pull-down List
- A list of the acceptable or approved values that can be selected for a certain data field
  ![[Pasted image 20260318143857.png]]
## Others
### Default Values
Fields entered by the system during data entry. Used when the value of the field can be predicted with some certainty eg. VAT rate, Dates.
### Radio Buttons/Checked Boxes
### Validation Checks eg. data type check
### Automated Inputs
- Scanned, read, sensed inputs
# Input Design
## Types of Input Devices
- Biometic device
- Biometric device 
- Data collection device
- Digital camera 
- Graphic input device
- Stylus pen
- Keyboard 
- MICR
- Microphone
- Mouse
- RFID
- Scanner / OCR
- Terminal 
- Touch screen
- Voice input device
## Exercise for Students
- Fine Grocer is a hypermarket located in KL.
- Identify 4 areas where input devices are used and what they are in Fine Grocer.
## Suggested Answers
![[Pasted image 20260318144518.png]]
# Verification and Validation
- Verification - Before input data into a system, verification check (eg use human eyes) will be carried out.
- alidation - During input, data is subjected to another checks (eg programs ) for accuracy before processing could be carried out.
## Types of Data Validation
### Format Check
- Check that data conform to certain expected picture or format.
- Example - a product code have a picture format of AAA/99/AAA.
### Existence/Presence Check
- Check whether the data keyed in exists or not in the relevant database.
- Example - a Social Security number is checked for existence before user is allowed to save the record.
### Null Value Check
- Used to ensure that a value has been entered and not left blank for mandatory fields.
- Example – when filling form, check for mandatory fields
### Data Type Check
- Check that a data item fits the required data type.
- Example - numeric or alphabetic data
### Size Check
- Check that the data conforms to a certain number of characters.
- Example – telephone numbers must be 8 digits.
### Limit Check 
- Check that the data is not below or above a certain value.
- Example – a customer’s age must not be less than 10 years (Lower Limit Check).
### Range Check
- Check that the data lies within predetermined acceptable limits (lower and upper)
- Example - in a wages application, check clock card with ‘hours worked’ outside the range 10-80 hours.
# Consideration for Input Design

| Factors   | Comment / Example                                                   |
| --------- | ------------------------------------------------------------------- |
| Volume    | Large volumes require automated input                               |
| Frequency | Infrequent input needs keyboard<br>terminals.                       |
| Accuracy  | Built-in data validation checks. Automated<br>input.                |
| Speed     | Some transactions require that they be<br>input immediately eg. ATM |
# Examples of Input Screen
![[Pasted image 20260318145929.png]]
# Output Design
## Types of Outputs
- Display (Screen)
- Sound (Sound and audio devices)
- Printed (Printers and plotters)
- Filmed - Computer output microfilm (COM)
- Other devices – Mobile devices, ATM, POS terminals, VDUs
# Exercise for Students
- Identify and briefly explain 3 types of output devices used in an airline industry
1) Printer – for printing of boarding pass
2) Speaker – for announcement of departure and arrival
3) Screen – for check-in
4) Kiosk – for self check-in
# Report Design
## Report Characteristics
- Functional Area – a report must be designed for a particular functional area (eg Sales department) eg. Sales Analysis for they Year 2022.
- Level of Staff/Details – a report designed for a particular staff of certain level eg. a Summarized Sales for sales manager.
- Purpose of Report – a report contains information which are relevant and useful to the users for making decision
# 3 Types of Reports
1) Exception reports
	1) Meaning - Filtered items using specific criteria
	2) Example: “Top 5 saleable items for the year 2023.
![[Pasted image 20260318151134.png]]
2) Summary reports
	1) Meaning - Totals and sub-totals, may be graphs or charts
	2) Example: “Total sales for the year 2023, for Item A, breakdown by month, branch, or salesman.
![[Pasted image 20260318151149.png]]
3) Detail reports
	1) Meaning: Report every single item.
	2) Example: Detail daily sales for a customer for the month of Dec, 2023.
![[Pasted image 20260318151202.png]]
# Report Design Layout
![[Pasted image 20260318151227.png]]
# Attributes of a Good Report
### Appropriate Report Title
- Name. The report title should lead the readers to know what it will contain.
- Length. The title used should be clear, simple and concise.
### Pleasing Report Layout
- Labels. All data entry fields and data should have appropriate labels.
- Layout. Information on a report should be well layout on paper or displayed on a screen with sufficient margins and spaces between the data items.
### Meaningful Report Content
- Presentation. Information contained in a report should be presented in a way that is useful to the users.
- Relevant. A report should only contain information which are relevant and required by the users.
