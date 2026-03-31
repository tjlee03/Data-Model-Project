# MIST-4610-Project-1
Group Project 1
## Team Name and Members
 • Makenna Clark-811340225-(https://github.com/MakennaClark/Data-Model-Project)
 
 • Mikey Cap-811608237-
 
 • William Barret-
 
 •Talmage Lee-
 
## Problem Description
Our team designed a database to model the operations of a property management company that oversees two off-campus student housing communities. In our project, we created 12 entities to represent the core components of the system, along with the relationships between them to form a complete data model. From the company’s perspective, we modeled properties and units to organize housing availability and track occupancy. Building on this, we included tenant-related entities such as leases and rent payments to capture the financial transactions and agreements between tenants and the company, ensuring accurate tracking of rent status and lease terms. On the operational side, we incorporated entities for maintenance requests and employees to manage service issues and staff responsibilities within the properties. Additionally, we modeled parking spaces, pets, and amenities to account for optional services and resident needs, including reservations and usage tracking. To support external interactions, we included vendors and related processes to handle outsourced services and maintenance support. This allows the system to reflect real-world scenarios. Overall, our data model captures both the day-to-day operations and the supporting services required to efficiently manage student housing communities, ensuring accurate tracking of resources, transactions, and resident activities.

## Data Model
![Data Model Image](https://github.com/MakennaClark/Data-Model-Project/blob/main/Data%20Model%20Image.jpeg?raw=true)
Our team's data model is based on the management of multi-unit residential properties. Each property has many relationships wiht other entities in the table. For example, a single property is subdivided into multiple units, and that same property can also feature many available amenities for residents. The property is managed by many employees, and it features many designated parking spots. Each specific unit also has complex relationships with other entities. A unit can have multiple leases, however only one can be active at a given time to signify that th eunit is occupied. Furthermore, a unit serves as the primary location for multiple maintenance requests submitted by occupants, which are then assigned to and fulfilled by various external vendors. Additionally, each tenant features relationships with many other entities in the table. A single tenant can sign many leases over time and resides in one specific unit per lease. A tenant is also responsible for making many individual rent payments, which are associated with their specific lease. Tenants also feature relationships with entities that exist outside of their direct living space: a tenant can create many amenity bookings for shared property facilities and can own many pets that reside with them in their unit.

## Data Dictionary
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


## Ten Queries
