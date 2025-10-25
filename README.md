# Team 4 MIST 4610 Group Project 1

## Team Name:
29704 Group 4



## Team Members:

1. Smit Shah [@smit9shah](https://github.com/smit9shah)
2. Nicholas Nichols [@nnichols915](https://github.com/nnichols915)
3. Martin Nguyen [@nguyenm82339](https://github.com/nguyenm82339)
4. Riley Collman [@rcollman44](https://github.com/rcollman44)
5. Sidd Navar [sn18206-oss](https://github.com/sn18206-oss)


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

<img width="722" height="456" alt="Screenshot 2025-10-25 at 6 31 53 PM" src="https://github.com/user-attachments/assets/693071a7-988a-4e7b-bb97-acbef95523c1" />


1. Query 1 calculates the overall average rating given by customers for the restaurant. The output of AvgRating represents the average rating across all feedback in the Feedback table. 

<img width="419" height="124" alt="query1" src="https://github.com/user-attachments/assets/e289d396-c484-47bb-92f4-4e2f634ed9b1" />

Query 1 allows managers to quicky look at overall customer satisfaction with the restaurant. Higher ratings mean that customers are happy with the food and service while a lower rating shows that the restaurant needs improvements. Tracking the average rating helps managers make changes to the restaurant in order to improve customer experience. 

2. Query 2 lists all tables in the restaurant with their location and the total number of reservations each table has received. It is then grouped by table and ordered in descending order by total reservations. 

<img width="468" height="135" alt="query2" src="https://github.com/user-attachments/assets/2b606950-4e4e-4675-9902-d90312dc249c" />

This query helps managers see which tables are most popular with customers. The tables with most reservations may need more staff attention to ensure a better customer experience. Understanding table popularity helps managers to make plans to further optimize seating and staffing for a particular table during peak hours. It is listed in descending order to make it easy to identify the most frequent tables being used. 

3. Query 3 summarizes menu item performance by showing the amount of times menu items were ordered and the total revenue that is associated with each item. The query joins OrderDetails and MenuItems to connect the ordered line items with their corresponding name and price.

<img width="697" height="438" alt="Screenshot 2025-10-25 at 4 27 06 PM" src="https://github.com/user-attachments/assets/d61a4a7b-b125-40bb-85c4-b48ab9c70c74" />


This output helps the restaurant management figure out which dishes are the top earners, and which items do not sell as well. From this, the high-revenue items can be more heavily pushed as well as making sure ingredients required for those menu items are frequently stocked. This query also helps overall with management being able to make data driven decisions about menu items and restocks. 

4. Query 4 reports employee first/last name as well as their role. It also shows the number of shifts each employee has. It joins employee and shifts tables to be able to record the individual shifts while linking them back to each employee.


<img width="699" height="464" alt="Screenshot 2025-10-25 at 4 27 53 PM" src="https://github.com/user-attachments/assets/9fae9d2d-13fb-434c-a3b5-bd0f3e5b6b61" />

This output helps managers see which employees have certain numbers of shifts compared to others as well as which ones may not have shifts at all depending on a certain period of time. This is useful when it comes to balancing employee workloads and creating schedules. It can also help in finding out which roles are being scheduled, and which are not to try and make better staffing decisions.  

5. Query 5 finds menu items whose names contain the letter "a" and whose price is above the restaurant's average menu item price. The query uses a subquery to calculate the overall average price and a REGEXP filter to match item names containing "a" or "A."
   
<img width="720" height="388" alt="image" src="https://github.com/user-attachments/assets/7fbdbbb5-f0bd-4fe5-8f2f-9a659675b360" />

This query allows restaurant management to quickly identify premium-priced dishes within popular naming patterns. By isolating these items, managers can evaluate whether the pricing aligns with demand and customer perception. 

6. Query 6 identifies all tables that do not have any reservations on a particular date. It joins the Tables and Reservations data logically through a NOT EXISTS clause, checking which tables have no entries for the specified day.

<img width="1106" height="512" alt="image" src="https://github.com/user-attachments/assets/958bce75-9131-44d0-ab07-4c99a33d70cd" />

This output helps restaurant managers easily see which tables are unbooked on a given day. Knowing table availability in advance supports floor planning, scheduling, and walk-in management. During busy periods, it ensures that the team can quickly identify open seating. During slow days, it provides insight into underutilized areas that could be reconfigured to increase reservations. 

7. Query 7 This query calculates the average feedback rating for each employee and shows those with ratings above 4.0 

<img width="859" height="326" alt="Screenshot 2025-10-25 at 5 53 09 PM" src="https://github.com/user-attachments/assets/46cd4163-d938-4dde-9a7f-faa0ed0917a3" />

Managers can recognize employees that provide good service. This helps in rewarding employees with top performance and maintaining high customer satisfaction. 

8. Query 8: This query lists suppliers and counts how many inventory items are for each supply. 

<img width="1165" height="311" alt="Screenshot 2025-10-25 at 5 54 55 PM" src="https://github.com/user-attachments/assets/3c074f79-5109-48df-9759-eafe1c7c6cdd" />

Managers of the restaurant can identify which suppliers provide most items. Managers can use this information to prioritize other suppliers if they have high volumes of supply. 

9. Query 9: Query 9 calculates the average salary for each employee in the restaurant. It groups employees by role and calculates the average salary. The results are sorted from the highest to lowest average salary in descending order. 

<img width="563" height="278" alt="Screenshot 2025-10-25 at 6 03 48 PM" src="https://github.com/user-attachments/assets/7a1493ae-3850-4877-ae8b-9c68fc73354d" />

This query can be useful to see the average pay for each job. It makes sures employees are paid fairly.  

10. Query 10: This counts how many menu items exist in each category in the restaurant.

<img width="564" height="271" alt="Screenshot 2025-10-25 at 6 15 28 PM" src="https://github.com/user-attachments/assets/114a2924-365e-4325-8bcf-17dc689f500a" />

Managers can see the different items in each category and make changes to the menu by introducing new items or removing them. 





