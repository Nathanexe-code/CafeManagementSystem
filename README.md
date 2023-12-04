# CafeManagementSystem
Cafe Management System

## Entities:

1. **Customer**
   - customer_ID: Unique identifier for customers
   - customer_Name: Customer's name
   - customer_Address: Customer's address
   - customer_Email: Customer's email
   - customer_RegDate: Registration date with a default value
   - customer_LoyaltyPoint: Loyalty points associated with the customer

2. **CustomerPhone**
   - customer_Phone: Phone number of a customer
   - customer_ID: Foreign key linking to the Customer entity

3. **CafeManager**
   - manager_ID: Unique identifier for cafe managers
   - manager_Name: Manager's name
   - manager_Address: Manager's address
   - manager_Email: Manager's email
   - manager_Salary: Manager's salary
   - manager_JoinDate: Manager's join date

4. **ManagerPhone**
   - manager_Phone: Phone number of a manager
   - manager_ID: Foreign key linking to the CafeManager entity

5. **CashierManager**
   - cashier_ID: Unique identifier for cashiers
   - cashier_Name: Cashier's name
   - cashier_Address: Cashier's address
   - cashier_Email: Cashier's email
   - cashier_Salary: Cashier's salary
   - cashier_JoinDate: Cashier's join date
   - manager_ID: Foreign key linking to the CafeManager entity
   - customer_ID: Foreign key linking to the Customer entity

6. **CashierCustomer**
   - cashier_ID: Foreign key linking to the CashierManager entity
   - customer_ID: Foreign key linking to the Customer entity

7. **CashierManagerRelation**
   - cashier_ID: Foreign key linking to the CashierManager entity
   - manager_ID: Foreign key linking to the CafeManager entity

8. **InventoryManager**
   - inventoryManager_ID: Unique identifier for inventory managers
   - inventoryManager_Name: Inventory manager's name
   - inventoryManager_Address: Inventory manager's address
   - inventoryManager_Email: Inventory manager's email
   - inventoryManager_Salary: Inventory manager's salary
   - manager_ID: Foreign key linking to the CafeManager entity

9. **InventoryManagerPhone**
   - inventoryManager_Phone: Phone number of an inventory manager
   - inventoryManager_ID: Foreign key linking to the InventoryManager entity

10. **Menu**
    - menu_ID: Unique identifier for menu items
    - menu_Name: Menu item's name
    - menu_Price: Menu item's price
    - menu_Availability: Menu item's availability status
    - menu_Description: Menu item's description
    - menu_NutriInfo: Menu item's nutritional information
    - menu_Category: Menu item's category
    - inventoryManager_ID: Foreign key linking to the InventoryManager entity

11. **MenuInventory**
    - menu_ID: Foreign key linking to the Menu entity
    - inventoryManager_ID: Foreign key linking to the InventoryManager entity

12. **Orders**
    - order_ID: Unique identifier for orders
    - order_Date: Order date with a default value
    - order_PaymentMethod: Payment method used for the order
    - order_Status: Order status
    - order_Discount: Discount applied to the order
    - order_CustomerID: Foreign key linking to the Customer entity
    - order_ManagerID: Foreign key linking to the CafeManager entity

13. **OrderDetails**
    - order_ID: Foreign key linking to the Orders entity
    - menu_ID: Foreign key linking to the Menu entity
    - orderDetails_Quantity: Quantity of a menu item in an order

14. **Vendor**
    - vendor_ID: Unique identifier for vendors
    - vendor_Name: Vendor's name
    - vendor_Address: Vendor's address
    - vendor_Email: Vendor's email
    - manager_ID: Foreign key linking to the CafeManager entity

15. **VendorPhone**
    - vendor_Phone: Phone number of a vendor
    - vendor_ID: Foreign key linking to the Vendor entity

## Relationships and Cardinality:

1. **Customer to CustomerPhone:** One-to-Many (1:N) - A customer can have multiple phone numbers.

2. **CafeManager to ManagerPhone:** One-to-Many (1:N) - A manager can have multiple phone numbers.

3. **CafeManager to CashierManager:** One-to-Many (1:N) - A manager can manage multiple cashiers.

4. **Customer to CashierCustomer:** Many-to-Many (M:N) - A customer can be associated with multiple cashiers, and a cashier can serve multiple customers.

5. **CashierManager to CashierManagerRelation:** One-to-Many (1:N) - A cashier can have multiple relations with managers.

6. **CafeManager to InventoryManager:** One-to-Many (1:N) - A cafe manager can manage multiple inventory managers.

7. **InventoryManager to InventoryManagerPhone:** One-to-Many (1:N) - An inventory manager can have multiple phone numbers.

8. **InventoryManager to Menu:** One-to-Many (1:N) - An inventory manager can manage multiple menu items.

9. **InventoryManager to MenuInventory:** One-to-Many (1:N) - An inventory manager can be associated with multiple menu items through inventory information.

10. **Customer to Orders:** One-to-Many (1:N) - A customer can place multiple orders.

11. **CafeManager to Orders:** One-to-Many (1:N) - A cafe manager can oversee multiple orders.

12. **Orders to OrderDetails:** One-to-Many (1:N) - An order can have multiple order details.

13. **Menu to OrderDetails:** One-to-Many (1:N) - A menu item can be part of multiple order details.

14. **CafeManager to Vendor:** One-to-Many (1:N) - A cafe manager can manage multiple vendors.

15. **Vendor to VendorPhone:** One-to-Many (1:N) - A vendor can have multiple phone numbers.

## ERD Diagram
