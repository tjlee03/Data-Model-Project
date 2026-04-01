# MIST-4610-Project-1
Group Project 1
## Team Name and Members:
 • Makenna Clark-811340225-(https://github.com/MakennaClark/Data-Model-Project)
 
 • Mikey Cap-811608237- (https://github.com/mgc96398/Data-Model-Project/tree/main)
 
 • William Barret-811181795 - (https://github.com/Wbarrett1013/MIST4610-GroupOne-Project-1)
 
 •Talmage Lee-811563323- (https://github.com/tjlee03/Data-Model-Project/tree/main)
 
## Problem Description:
Our team designed a database to model the operations of a property management company that oversees two off-campus student housing communities. In our project, we created 12 entities to represent the core components of the system, along with the relationships between them to form a complete data model. From the company’s perspective, we modeled properties and units to organize housing availability and track occupancy. Building on this, we included tenant-related entities such as leases and rent payments to capture the financial transactions and agreements between tenants and the company, ensuring accurate tracking of rent status and lease terms. On the operational side, we incorporated entities for maintenance requests and employees to manage service issues and staff responsibilities within the properties. Additionally, we modeled parking spaces, pets, and amenities to account for optional services and resident needs, including reservations and usage tracking. To support external interactions, we included vendors and related processes to handle outsourced services and maintenance support. This allows the system to reflect real-world scenarios. Overall, our data model captures both the day-to-day operations and the supporting services required to efficiently manage student housing communities, ensuring accurate tracking of resources, transactions, and resident activities.

## Data Model:
![Data Model Image](https://github.com/MakennaClark/Data-Model-Project/blob/main/Data%20Model%20Image.jpeg?raw=true)
Our team's data model is based on the management of multi-unit residential properties. Each property has many relationships wiht other entities in the table. For example, a single property is subdivided into multiple units, and that same property can also feature many available amenities for residents. The property is managed by many employees, and it features many designated parking spots. Each specific unit also has complex relationships with other entities. A unit can have multiple leases, however only one can be active at a given time to signify that th eunit is occupied. Furthermore, a unit serves as the primary location for multiple maintenance requests submitted by occupants, which are then assigned to and fulfilled by various external vendors. Additionally, each tenant features relationships with many other entities in the table. A single tenant can sign many leases over time and resides in one specific unit per lease. A tenant is also responsible for making many individual rent payments, which are associated with their specific lease. Tenants also feature relationships with entities that exist outside of their direct living space: a tenant can create many amenity bookings for shared property facilities and can own many pets that reside with them in their unit.

## Data Dictionary:
![Properties](https://github.com/MakennaClark/Data-Model-Project/blob/main/Properties.png?raw=true)
![Units](https://github.com/MakennaClark/Data-Model-Project/blob/main/Units.png?raw=true)
![Tenants](https://github.com/MakennaClark/Data-Model-Project/blob/main/Tenants.png?raw=true)
![Leases](https://github.com/MakennaClark/Data-Model-Project/blob/main/Leases.png?raw=true)
![Rent Payments](https://github.com/MakennaClark/Data-Model-Project/blob/main/RentPayments.png?raw=true)
![Maintenance Requests](https://github.com/MakennaClark/Data-Model-Project/blob/main/MaintenenceRequests.png?raw=true)
![Vendors](https://github.com/MakennaClark/Data-Model-Project/blob/main/Vendors.png?raw=true)
![Employees](https://github.com/MakennaClark/Data-Model-Project/blob/main/Employees.png?raw=true)
![Parking Spots](https://github.com/MakennaClark/Data-Model-Project/blob/main/ParkingSpots.png?raw=true)
![Pets](https://github.com/MakennaClark/Data-Model-Project/blob/main/Pets.png?raw=true)
![Amenities](https://github.com/MakennaClark/Data-Model-Project/blob/main/Amenities.png?raw=true)
![Amenity Bookings](https://github.com/MakennaClark/Data-Model-Project/blob/main/AmenityBookings.png?raw=true)


## Ten Queries (1-6 Complex, 7-10 Simple):

1. Lists the name of each property, the number of completed payments received, and the total revenue collected from those payments. Only properties that have collected more than $2,000 in total completed payments are shown. Results are ordered by total revenue in descending order.

![Query 1](https://github.com/mgc96398/Data-Model-Project/blob/main/Query%201%20.png?raw=true)

Query 1 allows management to quickly identify the top revenue-generating properties. A property manager overseeing 25 properties needs to know which locations are bringing in the most money so they can allocate maintenance budgets, staffing, and marketing resources accordingly. 

2. Lists all tenants who have never submitted a maintenance request.

![Query 2](https://github.com/mgc96398/Data-Model-Project/blob/main/Query%202.png?raw=true)

Query 2 allows management to identify tenants who have never reported any issues. This could mean two things: either those tenants are satisfied, or they are not reporting problems that could be getting worse over time. A proactive manager could reach out to these tenants for a satisfaction check or schedule a routine unit inspection to catch hidden issues like water damage or pest problems before they become expensive.

3. Lists the vendors who have handled more maintenance requests than the average number of requests per vendor, along with their service category and total request count.

![Query 3](https://github.com/mgc96398/Data-Model-Project/blob/main/Query%203.png?raw=true)

Query 3 allows management to identify which vendors are being relied on the most. Vendors with above-average workloads (like Quick Fix Appliances with 3 requests) may need contract renegotiation for volume discounts, or management may want to evaluate whether they should bring in a second vendor in that category to distribute the work.

4. Lists the properties whose unit occupancy rate falls below the overall company average. The query calculates the number of occupied units and the occupancy percentage for each qualifying property

![Query 4](https://github.com/mgc96398/Data-Model-Project/blob/main/Query%204.png?raw=true)

Query 4 is essential for any property manager because vacant units directly equal lost revenue. By comparing each property's occupancy to the company-wide average, management can immediately see which properties are underperforming.

5. Lists each payment method used by tenants, the total number of transactions made with that method, the number of completed and failed transactions, and the failure rate as a percentage. Results are ordered by failure rate in descending order

![Query 5](https://github.com/mgc96398/Data-Model-Project/blob/main/Query%205.png?raw=true)

Query 5 reveals that checks have a 50% failure rate — by far the most unreliable payment method — while Credit Card, Debit Card, and Bank Transfer have zero failures. A property manager can use this to justify changing the company's payment policy, such as adding a processing fee for checks or requiring tenants to switch to electronic payment methods. Failed payments create accounting overhead and delay cash flow, so reducing check usage would directly improve operational efficiency. 

6. Lists tenants whose last names match common surname patterns (Clark, Hall, Walker, or Lewis), along with their monthly rent and property name, but only for tenants whose leases are still active (ending on or after April 1, 2024)

![Query 6](https://github.com/mgc96398/Data-Model-Project/blob/main/Query%206.png?raw=true)

Query 6 demonstrates REGEXP for flexible pattern matching, which is useful in database management for finding tenants based on name patterns. In practice, a property manager might use this type of query to pull up all tenants from a certain family (e.g., multiple Clarks or Lewises who may be related), to cross-reference names for duplicate account detection, or to quickly filter a large tenant list during targeted outreach campaigns such as lease renewal reminders.

7. Lists every tenant with an active lease (ending in 2024 or later), the number of bedrooms and bathrooms in their unit, and the property they live in.

![Query 7](https://github.com/mgc96398/Data-Model-Project/blob/main/Query%207.png?raw=true)

Query 7 gives management a complete roster of all current tenants, where they live, and what type of unit they occupy.

8. Lists the number of leases and the average monthly rent for each bedroom count (1- bedroom, 2-bedroom, 3-bedroom).

![Query 8](https://github.com/mgc96398/Data-Model-Project/blob/main/Query%208.png?raw=true)

Query 8 helps management understand their pricing structure. It shows that 2-bedroom units are the most commonly leased (10 leases), while 3-bedroom units command the highest average rent at $1,783. A manager could use this to evaluate whether their pricing is competitive with the local Athens rental market, or to decide which unit types to prioritize in future property acquisitions or renovations.

9. Lists all maintenance requests that are not yet resolved (Open, In Progress, or Urgent), along with the assigned vendor and their service category. Results are sorted by the date the issue was reported

![Query 9](https://github.com/mgc96398/Data-Model-Project/blob/main/Query%209.png?raw=true)

Query 9 is the maintenance team's daily dashboard. It shows every outstanding issue, how longit has been open, and which vendor is responsible. The "Outlets in bedroom sparking" issue marked as Urgent is a safety hazard that demands immediate follow-up.

10. Lists all tenants who own pets, along with the pet's name, type, breed, and the propertythe tenant currently lives in. Only tenants with active leases are included

![Query 10](https://github.com/mgc96398/Data-Model-Project/blob/main/Query%2010.png?raw=true)

Query 10 allows management to see exactly which tenants have pets and at which properties. This is important for ensuring pet deposits have been collected, verifying that pets comply with breed or size restrictions in the lease, and planning pet-friendly amenities or services. 

## Matrix:
![Matrix](https://github.com/mgc96398/Data-Model-Project/blob/main/Matrix.png?raw=true)
![Matrix](<img width="613" height="289" alt="Matrix" src="https://github.com/user-attachments/assets/8a4527d8-b305-4fc8-82ab-89e509767831" />)

