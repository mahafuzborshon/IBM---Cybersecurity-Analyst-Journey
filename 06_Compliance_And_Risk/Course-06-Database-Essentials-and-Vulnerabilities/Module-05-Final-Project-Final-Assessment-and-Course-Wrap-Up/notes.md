- Final Project Setup
  - Imported SecureShop.sql database
  - Tables used: customers, orders, products, payment_details

- SQL Query Practice
  - SELECT queries executed on multiple tables
  - Retrieved full dataset and specific records

- JOIN Operations
  - Combined orders and customers tables
  - Used customer_id to link data
  - Retrieved order + customer details together

- Filtering Data
  - WHERE clause used to get specific records
  - Example: filtering by customer_id or order_id

- User Roles & Permissions
  - Used SHOW GRANTS
  - Checked privileges like SELECT, UPDATE, DELETE
  - Understood access control in database

- Data Masking
  - Used CONCAT and RIGHT functions
  - Masked postal codes (e.g., ****01)
  - Helps protect sensitive information

- Encryption & Decryption
  - Viewed encrypted phone data
  - Used AES_DECRYPT to retrieve original values
  - Learned how encryption protects stored data

- Data Observations
  - Customer details include personal info
  - Orders linked with customers
  - Payment details include transaction data

- Final Assessment
  - Completed graded quiz (100%)

- Key Takeaway
  - Real-world database security involves querying, access control, encryption, and safe data handling together

  - Final Project Setup
  - Imported SecureShop.sql database successfully
  - Total queries executed during import
  - Tables used:
    - customers
    - orders
    - products
    - payment_details

- Task 1: View All Orders with Customer Info
  - Used JOIN to combine tables
  - SQL:
    SELECT o.order_id, o.total_amount, c.first_name, c.last_name, c.email 
    FROM orders o 
    JOIN customers c ON o.customer_id = c.customer_id;

- Task 2: Filter Specific Order
  - Used WHERE condition
  - SQL:
    SELECT o.order_id, o.total_amount, c.first_name, c.last_name, c.email 
    FROM orders o 
    JOIN customers c ON o.customer_id = c.customer_id 
    WHERE o.order_id = 1 OR 1=1;

- Task 3: Check User Permissions
  - Used SHOW GRANTS
  - SQL:
    SHOW GRANTS FOR 'Delivery_Executive'@'localhost';

- Task 4: Data Masking (Postal Code)
  - Masked sensitive data
  - SQL:
    SELECT customer_id, postal_code, 
    CONCAT('****', RIGHT(postal_code, 2)) AS masked_postal_code 
    FROM customers;

- Task 5: Decrypt Encrypted Data
  - Viewed decrypted phone numbers
  - SQL:
    SELECT customer_id, 
    AES_DECRYPT(encrypted_phone, 'my_secret_key') AS decrypted_phone 
    FROM customers;

- Task 6: View Encrypted Data
  - Compared encrypted vs decrypted
  - SQL:
    SELECT customer_id, encrypted_phone FROM customers;

- Task 7: Retrieve Customer + Order Details
  - Used JOIN with filtering
  - SQL:
    SELECT * 
    FROM orders o 
    JOIN customers c ON o.customer_id = c.customer_id 
    WHERE c.customer_id = 5;

- Task 8: Retrieve Payment Details
  - SQL:
    SELECT * FROM payment_details WHERE order_id = 7;

- Task 9: View Products Table
  - SQL:
    SELECT * FROM products;

- Task 10: View Customers Table
  - SQL:
    SELECT * FROM customers;

- Task 11: View Payment Details Table
  - SQL:
    SELECT * FROM payment_details;

- Key Learning
  - JOIN connects multiple tables
  - WHERE filters data
  - SHOW GRANTS checks permissions
  - CONCAT & RIGHT used for masking
  - AES_DECRYPT used for secure data handling
