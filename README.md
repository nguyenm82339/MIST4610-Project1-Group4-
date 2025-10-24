# Team 4 MIST 4610 Group Project 1

## Team Members:

1. Smit Shah
2. Nicholas Nichols 
3. Martin Nguyen 
4. Riley Collman
5. Sidd Navar


## Scenario Description:
Our project models a full-service casual sit-down restaurant that serves guests in a dine-in manner. Our project helps to try and streamline the overall restaurant operation by tracking customers, employees, menu items, orders, payments, inventory, suppliers, reservations, feedback, etc. 


## Data Model

Explanation of data model: 

Our model is based on the structure of a full-service casual dining restaurant. The goal of this database is to efficiently manage restaurant operations including customers, employees, orders, payments, inventory, reservations, and suppliers.

The Customer entity represents guests who dine at the restaurant. Each customer can make multiple reservations and place multiple orders over time, which is why there are one to many relationships between Customer and both Reservations and Order.

The Reservations entity records all customer reservations, including which customer made the reservation and which table was booked. Each reservation is linked to a record in the Tables entity, which stores details about the seating capacity and location of each table in the restaurant. This allows the restaurant to manage seating availability accurately.

The Order entity tracks each transaction made by customers. Orders are connected to the Customer table through a foreign key to identify who placed the order and to the OrderDetails table, which lists the specific menu items included in each order. Because each order may include multiple menu items and each menu item can appear in multiple orders, the OrderDetails table serves as an associative entity between Order and MenuItems.

The MenuItems entity contains all food and beverage items offered by the restaurant. It includes attributes such as the item name, price, and category. Each menu item can have one or more ingredients, which are defined in the Ingredients table. The Ingredients entity lists all ingredients used in menu items and connects to both MenuItems and Supplier through foreign keys.

The Supplier entity represents companies that provide raw ingredients to the restaurant. Suppliers deliver inventory items that are tracked in the Inventory table. Because one supplier can provide multiple inventory items and one inventory item can be sourced from multiple suppliers, the Supplier_has_Inventory table captures this many to many relationship.

The Employee entity represents the staff working at the restaurant such as servers, chefs, hosts, and managers. Each employee has an ID, role, salary, and hire date. Employees are assigned to shifts, which are recorded in the Shifts table. The one to many relationship between Employee and Shifts shows that an employee can work multiple shifts but each shift is assigned to one employee.

The Payments table stores information about payment transactions for each order including payment method and amount. Each payment links back to an order through a foreign key allowing management to analyze total revenue, preferred payment methods, and daily performance.

The Feedback table allows customers to leave reviews about their dining experience. Each feedback record is linked to a customer, enabling the restaurant to collect opinions and measure customer satisfaction.

Overall, the data model captures and connects all the core operations of the restaurant from customer reservations and supplier relationships to employee scheduling and payments, allowing management to maintain efficient service, monitor business activity, and make informed operational decisions.


<img width="958" height="606" alt="Project4610Dia" src="https://github.com/user-attachments/assets/6000854f-8439-4fa9-b0b1-33f479f704e1" />

## Data Dictionary:
<img width="688" height="390" alt="Screenshot 2025-10-23 at 8 48 06 PM" src="https://github.com/user-attachments/assets/fd7c8d2f-b2a1-4fc5-afad-021bee0795a4" />

<img width="680" height="330" alt="Screenshot 2025-10-23 at 8 50 12 PM" src="https://github.com/user-attachments/assets/44d7da9a-6cf6-4ca5-ad1a-dc219cbf0758" />

<img width="683" height="312" alt="Screenshot 2025-10-23 at 8 50 21 PM" src="https://github.com/user-attachments/assets/cd7e26ae-79fe-4d1d-a073-b46e2503cd7e" />

<img width="674" height="246" alt="Screenshot 2025-10-23 at 8 51 15 PM" src="https://github.com/user-attachments/assets/09d7608e-c570-4bfa-bb73-7c2ba251fee1" />

<img width="699" height="227" alt="Screenshot 2025-10-23 at 8 51 20 PM" src="https://github.com/user-attachments/assets/701c7d8c-25a4-4c86-91fa-772a4defd673" />

<img width="683" height="450" alt="Screenshot 2025-10-23 at 8 51 30 PM" src="https://github.com/user-attachments/assets/cdd0e4fa-259a-4bb6-93ce-5436bc3ad215" />

<img width="689" height="220" alt="Screenshot 2025-10-23 at 8 52 41 PM" src="https://github.com/user-attachments/assets/b03bdf7b-77de-4458-81ed-df33b32412f8" />

<img width="689" height="487" alt="Screenshot 2025-10-23 at 8 52 55 PM" src="https://github.com/user-attachments/assets/be894a66-513b-4898-beb7-62b6a9fee9e9" />

<img width="692" height="284" alt="Screenshot 2025-10-23 at 8 53 08 PM" src="https://github.com/user-attachments/assets/98eb5d61-32bc-4b79-aa4a-49cb4d23b4b7" />

<img width="676" height="196" alt="Screenshot 2025-10-23 at 8 53 16 PM" src="https://github.com/user-attachments/assets/91c970de-3557-40e2-a78d-38caaff8143b" />

<img width="705" height="290" alt="Screenshot 2025-10-23 at 8 54 35 PM" src="https://github.com/user-attachments/assets/b53c2b8b-469a-46c3-af95-eb0408e00c4d" />

<img width="675" height="305" alt="Screenshot 2025-10-23 at 8 54 44 PM" src="https://github.com/user-attachments/assets/dea951f2-fbc4-4415-a699-64013c75b829" />

<img width="693" height="497" alt="Screenshot 2025-10-23 at 8 55 03 PM" src="https://github.com/user-attachments/assets/295cb325-5916-4844-a091-c8aa99f07f78" />

<img width="676" height="269" alt="Screenshot 2025-10-23 at 8 55 14 PM" src="https://github.com/user-attachments/assets/fbfc4760-2d49-409c-9897-54554b70227e" />

## Queries:


1. Query 1 calculates the overall average rating given by customers for the restaurant. The output of AvgRating represents the average rating across all feedback in the Feedback table. 

<img width="419" height="124" alt="query1" src="https://github.com/user-attachments/assets/e289d396-c484-47bb-92f4-4e2f634ed9b1" />

Query 1 allows managers to quicky look at overall customer satisfaction with the restaurant. Higher ratings mean that customers are happy with the food and service while a lower rating shows that the restaurant needs improvements. Tracking the average rating helps managers make changes to the restaurant in order to improve customer experience. 


2. Query 2 lists all tables in the restaurant with their location and the total number of reservations each table has received. It is then grouped by table and ordered in descending order by total reservations. 

<img width="468" height="135" alt="query2" src="https://github.com/user-attachments/assets/2b606950-4e4e-4675-9902-d90312dc249c" />


This query helps managers see which tables are most popular with customers. The tables with most reservations may need more staff attention to ensure a better customer experience. Understanding table popularity helps managers to make plans to further optimize seating and staffing for a particular table during peak hours. It is listed in descending order to make it easy to identify the most frequent tables being used. 

