# Fact Recording
- Purpose - Facts about the existing system must be recorded / () so that they can be referred to during the subsequent stages.
- Methods - System analyst may use different recording methods eg descriptions, diagrams etc
# Models Used in Fact Recording
1) Narrative Description (most popular)
2) Data Flow Diagram (DFD)
3) Entity Relationship Diagram (ERD)
4) Functional Decomposition Diagram (Structure Chart)
5) Decision Tables
6) Decision Tree
7) Flowcharts eg. System flowchart, program flowchart, clerical procedural flowchart
8) Others eg UML diagrams (eg Activity Diagrams)
# Examples of Models Used in Analysis Phase
The analysis phase activity may involve creating a variety of models.
They are referred to as logical models. Describe what is required without committing to one specific technology on how to carry out.
# Data Flow Diagram
![[Pasted image 20260225145150.png]]
# Definition of DFD
- Graphical Models - DFD uses graphical model to document the operation of the current system.
- () - The processes of the current system are modelled with a set of symbols or notations.
- () - The diagramming notation used: process, data store, data flow and entity.
- Rules - There are rules that govern the connections between these symbols
# 4 Components of DFD
![[Pasted image 20260225145624.png]]
# Popular DFD Symbols
![[Pasted image 20260225145732.png]]
# Notation Used (TARC)
![[Pasted image 20260225145827.png]]
# Data Flow
- Definition
	- A () by which data moves from one part of the IS to another part.
	- Represents a specific piece of data in ()
- Examples
	- Calculating Gross Pay Process : Input data flows (eg. worked hours, pay rate, employee number); Output data flows (eg. gross pay)
	- Creating Purchase Order Process : Input data flows (purchase requisition, items details, supplier details); Output data flows (eg.PO)
- Symbol/Notation
- ![[Pasted image 20260225150218.png]]
# Process
- Definition
	- Describe the main () that take place within the system. It changes incoming data flows into outgoing data flows
- Examples
	- Calculate gross pay
	- Preparing vendor cheques
- Symbol
	- A circle
	- Labeled with an active () (eg. Calculate) and a noun
# Data Store
- Definition
	- Shows information that is stored within the system
	- It is accessed and updated by the processes
	- It is a file or ().
- Examples
	- Student Scores
	- Employee Salary and Deduction data
- Symbol/Notation
	- An open-ended rectangle
	- Labeled with a name () and a number as an identifier
# Entities
- Definition
	- Represents a person, department, organisation or other IS that receives (sink) or send (source) information to/from the system concerned.
	- Show the () if the IS
- Examples 
	- Customer
	- Patient
- Symbol
	- A rectangle
	- Labeled with a ()
# Steps in Drawing DFD
- Start by drawing a () Diagram
- Draw detail diagrams using a series of 'explosion' or level of abstraction eg. Diagram 0, Diagram 1 etc. until 'functional primitive'
![[Pasted image 20260225151314.png]]
# DFD and Levels of Abstraction ('explosion')
![[Pasted image 20260225151520.png]]
Note :
1) Date stores not shown in context diagram
2) The number of external entities remain the same
3) In 'balancing', the number of inflows and outflows remain the same
# Step 1 - Context Diagram
- Definition - represents the entire software element as a single process () with input and output data indicated by incoming and outgoing arrow. Boundary indicated by external entities.
![[Pasted image 20260225151814.png]]
# Example 1 - Sales Order System
- In XYZ Ltd, when a sales order is received from a customer, the sales personnel would have to check whether the particular customer's credit limit has been exceeded or not. This can be carried out by checking with the Accounts Dept. The next thing to check is the availability of the stock items ordered.
- Where all these are in proper order, then an order confirmation will be sent to the customer and a delivery request sent to the Warehouse. The Warehouse would confirm if the delivery of goods has been completed. After the goods have been sent to the customer.
# Context Diagram
![[Pasted image 20260225152403.png]]
# Step 2 - Diagram 0 DFD
![[Pasted image 20260225152437.png]]
# Step 3 - Diagram 1 DFD (For Receive Order Process)
![[Pasted image 20260225152503.png]]
# Example 2 - Ticket Reservation System
- The ticketing functions start with the customer booking tickets online in the comfort of their homes or simply walk-in to any of the 50 ticketing counters located in various places throughout the country. When a reservation is made, cash payment is collected to be banked later in the day. Payment can also be made using credit cards where the normal credit verification with the credit card firm is carried out. Cancellation, if any can only be allowed at least two weeks prior to the concert when refunds will be given. In other cases no refunds will be allowed
# Context Diagram - Ticket Reservation System
![[Pasted image 20260225153209.png]]
# Diagram 0 DFD
![[Pasted image 20260225153238.png]]
# Steps in Drawing DFD - Purchasing System
## Example 3 - Purchasing System
- Purchase requests are received from other branches to buy goods. The company practices a centralized purchasing policy.
- The purchasing department will invite request for quotations to suppliers. Suppliers will be sending in quotation for biddings.
- A purchase order will be prepared, a copy of which is sent to the supplier and a copy retained. Occasionally, new suppliers may be included into the suppliers file.
- When goods are delivered by the suppliers, the items received are checked against the purchase order. The delivery order is filed after noting any discrepancies.
- When the invoice is received from the supplier, it is checked against the delivery order, payment is then made and invoice is filed.
## Step 1 - Draw Context Diagram
- Draw a single process that represents the entire system. The process is named after the system with number zero
- Identify and draw the external entities
- Draw the data flows from an external entity to the system and from the system to that external entity
- NOTE : Logical assumptions on data flows may be made for this system. Other data flows which are not within the functions of a purchasing system will have to be left out
# Context Diagram
![[Pasted image 20260225154905.png]]
# Step 2 - Diagram 0 DFD
![[Pasted image 20260225154937.png]]
# Step 3 - Diagram 1 DFD - Prepare PO
![[Pasted image 20260225155027.png]]
# Important Points (Rules on DFD)
## DFD Rules
- () Rules
	- Transformation - Processes must have both inputs and outputs and they mist differ, that is some transformation must occur to the inputs to produce the outputs
	- Process Number - Each process is numbered but this is only for ease of identification and not to show sequence.
	- Process Heading - The description of the process should be a verb like 'prepare', 'calculate', 'check' etc plus objects (nouns)
- Data Flow Rules
	- Arrows - Arrows must always finish at or start from a process.
	- Label - Every arrows must be labeled. However, there is no requirement to label arrows that go in and out of data stores.
- () Rules
	- Number - Data stores are given a reference number (for reference only)
# Repeated Diagrams
- Rather than having data flow arrows criss-crossing all over the place it is often simpler to show a symbol more that once on the same diagram.
- Repeated Data Store
  ![[Pasted image 20260225155944.png]]
- Repeated Entity
  ![[Pasted image 20260225155959.png]]
# Some Common Errors