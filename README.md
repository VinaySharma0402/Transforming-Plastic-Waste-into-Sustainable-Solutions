# Transforming-Plastic-Waste-into-Sustainable-Solutions
# ♻️ Re Plastic Innovations - Plastic Waste Management on Salesforce

This Salesforce-based application helps manage **recycled plastic product inventory**, **automate order processing**, and **handle restock requests** efficiently. The system supports warehouse management by reducing manual intervention and improving transparency and automation in inventory tracking.

---

## 📦 Key Features

- **Recycled Product Tracking:** Manage recycled plastic products with fields like stock level, threshold, and capacity.
- **Order Management:** When orders are created, stock is automatically updated.
- **Restock Automation:** Automatically generates restock requests if stock falls below threshold.
- **Restock Approval Process:** On approval, product stock is updated.
- **Email Notifications:** Email alerts sent when restock requests are approved.
- **Task Management:** Allows scheduling of tasks related to stock handling and order management.

---

## 📁 Salesforce Custom Objects

| Object Name                                         | Purpose                                     |
|-----------------------------------------------------|---------------------------------------------|
| `Re_Plastic_Innovations_Recycled_Product__c`       | Stores product info like stock & threshold. |
| `Re_Plastic_Innovations_Order__c`                  | Represents an order placed for products.    |
| `Re_Plastic_Innovations_Restock_Request__c`        | Auto-created when stock is insufficient.    |

---
## 🖼️ Application Screenshots

### 📌 Recycled Product Records
![Recycled Product Screenshot]<img width="1920" height="1200" alt="Screenshot (56)" src="https://github.com/user-attachments/assets/ce7a0f18-e706-4d4e-a3b2-cb7e3bfcc6ab" />


### 📌 Order Placement Page
![Order Screen](<img width="1920" height="1200" alt="Screenshot (61)" src="https://github.com/user-attachments/assets/cc524289-fb77-4591-945b-3a8c2a33b315" />


### 📌 Restock Request Automatically Created
![Restock Request]<img width="1920" height="1200" alt="Screenshot (65)" src="https://github.com/user-attachments/assets/467b86b5-8e92-41e1-bf03-1e108e80583b" />


### 📌 Approved Restock and Updated Stock Level
![Restock Approved]<img width="1920" height="1200" alt="Screenshot (58)" src="https://github.com/user-attachments/assets/ecac6783-f2c6-4b62-974c-363d311fe363" />


## ⚙️ Apex Classes & Triggers

### Triggers
- **`UpdateStockAfterOrder`**
  - Fired after inserting an order.
  - Calls `InventoryManager.processOrderStock()`.

- **`UpdateStockAfterRestockApproval`**
  - Fired after restock request approval.
  - Calls `InventoryManager.processRestockApproval()` and sends email.

### Classes
- **`InventoryManager`**
  - Contains business logic for handling order stock deduction and restock approvals.

- **`EmailNotificationHelper`**
  - Sends email when restock requests are approved.

---

## 🧪 Test Class

- **`InventoryManagerTest`**
  - Ensures 100% code coverage.
  - Verifies:
    - Stock reduction after orders
    - Restock request creation
    - Stock update after approval

---

## 🛠️ How to Use

### Step 1: Create a Product
- Go to `Recycled Product` object and create a record.
- Set `Stock_Level__c = 50` and `Threshold__c = 10`.

### Step 2: Create Orders
- Create orders under `Re_Plastic_Innovations_Order__c` with quantity:
  - One order with quantity 20
  - One with quantity 40

### Step 3: Verify Restock Request
- Go to related list of the product.
- Check for generated `Restock Request` if stock falls below threshold.

### Step 4: Approve Restock
- Update the `Restock Request` status to "Approved".
- Stock will auto-update and an email will be sent.

---

## ✉️ Notification

Email is sent to `mabdulrahaman066@gmail.com` on restock approval.
You can modify the recipient list in `EmailNotificationHelper` class.

---

## ✅ Test Instructions

1. Open `InventoryManagerTest` class.
2. Click **Run Test**.
3. Ensure test passes and check code coverage (should be **100%**).

---

## 📌 Notes

- Auto Number fields like `Name` should **not be set manually**.
- All logic is handled via **Apex triggers** and **helper classes**.
- Be sure to deploy all components (triggers, classes, test class) before using in production.

---

## 👤 Author

**Ram Vinay Kumar**  
Email: vinaysharma8548@gmail.com
Project: `Transforming-Plastic-Waste-into-Sustainable-Solutions`

---

