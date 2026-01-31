## Master Table
During database design, master tables are designed first. Since the master table is created to **represent the core entities of the system**, the design of the master table i.e its columns and constraints describe the entities in the system.
### For example:
#### Online shop system:
- Core entities:
  - Customer
  - Product
  - Seller
These become **Master Tables** because they exist even when nothing is happening

## Transaction Table
Is an activity performed by entities (Master Tables) within the system. These activities are captured in transaction tables and usually, these transaction entries have foreign keys to master records. 
### For example:
#### Online shop system:
- Order
- Payment
- Shipment
