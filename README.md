# SQL JOINS(INNER-LEFT-RIGHT-FULL)

# SQL Joins – Customer & Orders 

## Overview

This project demonstrates the use of **SQL JOIN operations** to combine data from two related tables:

* **CUSTOMERS** – stores customer details.
* **ORDERS** – stores customer order information.

The dataset is created in a sample database named **SALESDB** and used to illustrate different join types:

* **INNER JOIN**
* **LEFT JOIN**
* **RIGHT JOIN**
* **FULL JOIN**

## Tables & Sample Data

### 1. CUSTOMERS Table

| CUSTOMER\_ID | NAME    | EMAIL                                         |
| ------------ | ------- | --------------------------------------------- |
| 1            | SRAVANI | [SRAVANI@GMAIL.COM](mailto:SRAVANI@GMAIL.COM) |
| 2            | LAVANYA | [LAVANYA@GMAIL.COM](mailto:LAVANYA@GMAIL.COM) |
| 3            | SHANNI  | [SHANNI@GMAIL.COM](mailto:SHANNI@GMAIL.COM)   |
| 4            | SNEHA   | [SNEHA@GMAIL.COM](mailto:SNEHA@GMAIL.COM)     |
| 5            | SWARUPA | [SWARUPA@GMAIL.COM](mailto:SWARUPA@GMAIL.COM) |

### 2. ORDERS Table

| ORDER\_ID | CUSTOMER\_ID | ORDER\_DATE | AMOUNT |
| --------- | ------------ | ----------- | ------ |
| 101       | 1            | 2024-03-09  | 5900   |
| 102       | 2            | 2025-05-10  | 3229   |
| 103       | 3            | 2025-08-11  | 200    |

---

## Join Types Demonstrated

### **INNER JOIN**

* Returns rows where **CUSTOMERS.CUSTOMER\_ID** matches **ORDERS.CUSTOMER\_ID**.
* Only customers with orders appear in the result.

**Result Example:**

| CUSTOMER\_ID | NAME    | ORDER\_ID | AMOUNT |
| ------------ | ------- | --------- | ------ |
| 1            | SRAVANI | 101       | 5900   |
| 2            | LAVANYA | 102       | 3229   |
| 3            | SHANNI  | 103       | 200    |

---

### **LEFT JOIN**

* Returns all customers, even if they have no orders.
* Order fields show as `NULL` for customers without orders.

**Result Example:**

| CUSTOMER\_ID | NAME    | ORDER\_ID | AMOUNT |
| ------------ | ------- | --------- | ------ |
| 1            | SRAVANI | 101       | 5900   |
| 2            | LAVANYA | 102       | 3229   |
| 3            | SHANNI  | 103       | 200    |
| 4            | SNEHA   | NULL      | NULL   |
| 5            | SWARUPA | NULL      | NULL   |

---

### **RIGHT JOIN**

* Returns all orders, including those without matching customers.
* In this dataset, all orders have matching customers, so it looks like the INNER JOIN output.

---

### **FULL JOIN**

* Combines the results of LEFT and RIGHT joins.
* Returns all customers and all orders, matching where possible.
* Customers without orders and orders without customers are included.

