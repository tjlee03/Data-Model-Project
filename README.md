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


# Ten Query Descriptions and Justifcations (1-6 Complex, 7-10 Simple):
## Query 1
Description: Lists the name of each property, the number of completed payments received, and the total revenue collected from those payments. Only properties that have collected more than $2,000 in total completed payments are included. Results are ordered by total revenue in descending order.

![Query 1](https://github.com/mgc96398/Data-Model-Project/blob/main/Query%201%20.png?raw=true)

Justification: This query allows management to quickly identify the top revenue-generating properties. A property manager overseeing a portfolio of 25+ properties needs to know which locations are bringing in the most income so they can allocate maintenance budgets, staffing, and marketing resources accordingly. Properties falling below the $2,000 threshold may warrant further investigation into vacancy rates or payment collection issues.

## Query 2
Description: This query lists all tenants who have never submitted a maintenance request. It compares the full tenant list against the maintenance request table and returns only those tenants with no matching records.

![Query 2](https://github.com/mgc96398/Data-Model-Project/blob/main/Query%202.png?raw=true)

Justification: This helps management identify tenants who have never reported any issues. This could indicate tenant satisfaction, or it could signal unreported problems such as water damage, pest issues, or HVAC failures that are getting worse over time. A proactive manager could use this list to schedule routine unit inspections or send out satisfaction surveys, ultimately preventing small issues from becoming costly repairs.

## Query 3
Description: This query lists the vendors who have handled more maintenance requests than the average number of requests per vendor, along with their service category and total request count. A subquery calculates the overall average, and the outer query filters for vendors exceeding that threshold.

![Query 3](https://github.com/mgc96398/Data-Model-Project/blob/main/Query%203.png?raw=true)

Justification: This query identifies which vendors are being relied on the most. Vendors with above average workloads may need contract renegotiation for volume discounts, or management may want to bring in a second vendor in that service category to distribute the work and reduce response times. It also helps flag potential over dependence on a single vendor, which poses a risk if that vendor becomes unavailable.

## Query 4
Description: This query lists the properties whose unit occupancy rate falls below the overall company average. It calculates the number of occupied units and the occupancy percentage for each property, then compares each property's rate against the company wide average using a subquery.

![Query 4](https://github.com/mgc96398/Data-Model-Project/blob/main/Query%204.png?raw=true)

Justification: Vacant units directly equal lost revenue. By comparing each property's occupancy to the company wide average, management can immediately identify underperforming properties that may need targeted marketing, rent adjustments, unit renovations, or a change in leasing strategy. This makes sure resources are directed where they will have the greatest impact on the bottom line.

## Query 5
Description: This query lists each payment method used by tenants, the total number of transactions made with that method, the number of completed and failed transactions, and the failure rate as a percentage. Results are ordered by failure rate in descending order.

![Query 5](https://github.com/mgc96398/Data-Model-Project/blob/main/Query%205.png?raw=true)

Justification: This query reveals which payment methods are the most and least reliable. For example, if checks show a significantly higher failure rate than electronic methods, a property manager can justify updating the company's payment policy, such as adding a processing fee for checks or requiring tenants to switch to electronic payments. Failed payments create accounting overhead and delay cash flow, so reducing unreliable payment methods directly improves operational efficiency.

## Query 6
Description: This query lists tenants whose last names match common surname patterns (such as Clark, Hall, Walker, or Lewis) using a REGEXP operator, along with their monthly rent and property name. Only tenants with active leases ending on or after April 1, 2024 are included.

![Query 6](https://github.com/mgc96398/Data-Model-Project/blob/main/Query%206.png?raw=true)

Justification: This query demonstrates the use of REGEXP for flexible pattern matching within a database. In practice, a property manager might use this type of query to identify potentially related tenants sharing a surname, to cross reference names for duplicate account detection, or to quickly filter a large tenant list during targeted outreach campaigns such as lease renewal reminders or compliance notices.

## Query 7 
Description: This query lists every tenant with an active lease ending in 2024 or later, the number of bedrooms and bathrooms in their unit, and the property they live in. It joins the Tenant, Lease, Unit, and Property tables to pull all of this information together.

![Query 7](https://github.com/mgc96398/Data-Model-Project/blob/main/Query%207.png?raw=true)

Justification: This gives management a complete roster of all current tenants, their locations, and the type of unit they occupy. It serves as a foundational reference for day to day operations, from coordinating maintenance schedules by unit type to planning move out logistics to making sure lease records are accurate and up to date across all properties.

## Query 8 
Description: This query lists the number of leases and the average monthly rent for each bedroom count (1 bedroom, 2 bedroom, 3 bedroom). It groups leases by the number of bedrooms in the associated unit and calculates aggregate statistics for each group.

![Query 8](https://github.com/mgc96398/Data-Model-Project/blob/main/Query%208.png?raw=true)

Justification: This helps management understand the portfolio's pricing structure and unit mix. It reveals which unit types are most commonly leased and how average rent varies by size. A manager could use this data to evaluate whether current pricing is competitive with the local rental market, to decide which unit types to prioritize in future acquisitions or renovations, or to identify pricing gaps that could be adjusted to maximize revenue.

## Query 9 
Description: This query lists all maintenance requests that are not yet resolved, meaning they have a status of Open, In Progress, or Urgent. It also shows the assigned vendor and their service category. Results are sorted by the date the issue was reported so that the oldest unresolved issues appear first.

![Query 9](https://github.com/mgc96398/Data-Model-Project/blob/main/Query%209.png?raw=true)

Justification: This query serves as the maintenance team's daily operational dashboard. It shows every outstanding issue, how long it has been open, and which vendor is responsible. Sorting by report date makes sure that the oldest and potentially most neglected issues are surfaced first. Urgent items like electrical hazards or water leaks demand immediate follow up, and this query ensures nothing falls through the cracks.

## Query 10
Description: This query lists all tenants who own pets, along with the pet's name, type, breed, and the property the tenant currently lives in. Only tenants with active leases are included in the results.

![Query 10](https://github.com/mgc96398/Data-Model-Project/blob/main/Query%2010.png?raw=true)

Justification: This allows management to maintain a clear record of pets across the portfolio. It is important for verifying that pet deposits have been collected, making sure pets comply with breed or size restrictions outlined in the lease agreement, scheduling pet related property inspections, and planning pet friendly amenities or services. Accurate pet tracking also reduces liability and helps resolve neighbor complaints more efficiently.

## Matrix:
![Matrix](https://github.com/tjlee03/Data-Model-Project/blob/main/Matrix.png?raw=true)

## Database Information: 
Name of the database: al_Group_21479_G1
Additional information: Each query listed above is marked in the database using stored procedures which can be called using the following format: CALL Q1();
