# **Warehouse Management System**

## **Level 1: Basic Product**
### **Goal:**
Start by creating a system to represent products in a warehouse.

- Create a blueprint for a product that includes:
  - Its name.
  - Its unique identifier (like a code or SKU).
  - Its quantity in stock.
- Add a way to describe the product, showing its name, code, and how many are available.

---

## **Level 2: Product Categories**
### **Goal:**
Group products into categories to add more detail.

- Create categories for products:
  - Perishable (like food or medicine).
  - Non-Perishable (like tools or electronics).
- Each category should have something special:
  - **Perishable:** Include an expiration date.
  - **Non-Perishable:** Include a warranty period (e.g., months or years).
- Update the descriptions to include these details.

---

## **Level 3: Warehouses**
### **Goal:**
Introduce warehouses to store the products.

- Create storage spaces called warehouses.
- Each warehouse should:
  - Have a name.
  - Have a maximum storage capacity (how many products it can hold).
  - Keep track of the products stored in it.
- Add ways to:
  - Add a product to a warehouse if there is enough space.
  - Remove a product from the warehouse.
  - List all the products in the warehouse.

---

## **Level 4: Warehouse Network**
### **Goal:**
Manage multiple warehouses as part of a network.

- Create a system that manages several warehouses together.
- Each warehouse in the network has its own name and stored products.
- Add ways to:
  - Add a new warehouse to the network.
  - Find which warehouse has a specific product.
  - Get a summary of all products across all warehouses.

---

## **Level 5: Shipments and Tracking**
### **Goal:**
Add the ability to manage shipments in and out of the warehouses.

- Create a way to track shipments for the products.
- Each shipment should:
  - Have a shipment ID.
  - Include the product being shipped.
  - Track the quantity being moved.
  - Record whether it is incoming (to the warehouse) or outgoing (from the warehouse).
- Add ways to:
  - Add a shipment record to the system.
  - Check the history of all shipments for a specific product.
  - Get a summary of all shipments for a particular warehouse.

---

## **Level 6: Using Interfaces and Generics**
### **Goal:**
Introduce interfaces and generics to make the system more flexible, reusable, and extensible.

- **Abstract Product Behavior:**
  - Create an interface `IProduct` to represent shared properties and behaviors of all products:
    - `Name`, `Code`, `Quantity`, and a method `GetDescription()`.
  - Update `Product`, `PerishableProduct`, and `NonPerishableProduct` to implement `IProduct`.

- **Abstract Warehouse Behavior:**
  - Create a generic interface `IWarehouse<T>`:
    - Represent warehouse operations like `AddProduct`, `RemoveProduct`, and `GetAllProducts`.
    - Use generics (`T`) to ensure that the warehouse can manage any product type that implements `IProduct`.

- **Generic Warehouse Implementation:**
  - Update the `Warehouse` class to implement `IWarehouse<T>` using generics to support various product types.

- **Generic Warehouse Network:**
  - Update `WarehouseNetwork` to manage multiple warehouses of any type:
    - Add new warehouses (`IWarehouse<T>`).
    - Search for products across warehouses.
    - List all products in the network.

---

### **Summary:**
By completing this task step by step, you'll design a warehouse system that:
1. Starts with basic product details.
2. Grows to categorize products.
3. Adds storage spaces for products.
4. Manages multiple warehouses in a network.
5. Tracks shipments in and out of the warehouses.
6. Introduces flexible and reusable abstractions with interfaces and generics.
