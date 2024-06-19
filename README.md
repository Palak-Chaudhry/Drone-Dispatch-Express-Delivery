# Drone-Dispatch-Express-Delivery
designed and developed a system to monitor deliveries of grocery products to customers using MySQL.

This system will support a "third party" grocery service. Customers will place orders with the service. The service will
coordinate with grocery stores to find the products (at variable – but hopefully the lowest – prices) and arrange
for a drone to deliver the products to the customer. On delivery, the store will be paid electronically by the
customer.
The system will support various types of users, including customers and employees of the grocery stores. All
users must be either customers and/or employees - our system will not keep track of any other types of user
accounts. All users will have distinct usernames when accessing the system.
Attributes that are used to identify entities in our system will normally consist of forty (40) or fewer
alphanumeric characters in some regular pattern/format. This will be the default format for entity-identifying
and "entity unique" attributes in our system unless otherwise noted.
We will also maintain the first name, last name, address, and birthdate of each user. The birthdate will be
represented in the "yyyy-mm-dd" date format. This will be the default format for dates in our system unless
otherwise noted. We will use the birthdate to help authenticate users, and send birthday greeting messages
along with discounts. Some users might not want to share their birthdate, but we must have their name and
address for drone deliveries and/or tax and salary purposes.
Some users might have relatively long first and/or last names, so we will ensure that we can manage names that
have one hundred (100) or fewer characters. Our default size for storing "general purpose" descriptive
attributes will be one hundred (100) or fewer characters unless otherwise noted.
We are handling the address as a single string, so we must ensure that we can store addresses of up to five
hundred (500) characters.
Each store has a distinct identifier, and a (possibly duplicated) longer name. Each store also keeps track of the
revenue it has earned from delivering orders successfully. Stores are supported (in general) by various
employees. Employees can support the company in different roles – for example, store workers or drone pilots.
We must track the unique tax identifier (e.g., Social Security Number for some people) for each employee for
legal purposes. The tax-identifier will be stored using a "xxx-xx-xxxx" format. We will also keep track of the
number of months (as an integer) that they have worked (i.e., time in service) for the company. We must also
keep track of the salary for each employee.
Some employees are drone pilots. Drone pilots control the drones as they carry groceries back and forth
between the stores and the customer's homes. Being a drone pilot is unique and time-consuming role, and an
employee is not allowed to be a drone pilot and store worker at the same time. Drone pilots are often treated
as "independent contractors" or "freelancers", so we don't really track which store they work for at any given
time. What's most important is that they pilot a drone that is contractually obligated to serve a specific store.
Each drone pilot must have a valid license to signify that they have received the proper training to operate the
drone safely. Each license will have a unique ID for tracking purposes. Flight skills also tend to improve with
experience, so we must also keep track of the number of successful deliveries (as an integer) for each pilot.
There are other employee roles such as financial data analysts or logistical coordinators, but we won't keep
track of those roles explicitly in our system.
Store workers are the people you often encounter in grocery stores stocking shelves; serving in the deli, bakery,
or seafood section; or acting as a cashier. Store workers are responsible for making sure that the stores are
ready to provide products as needed. Each store will have an identifier and a name. The identifiers will be
unique, though names might be shared. Each store worker must be employed by at least one store, though an
employee can also work at multiple stores as part of a "time-flex" plan. Each store can employ multiple store
workers.
Each store must also have one store worker to act as the overall manager for that store. Managing a store
implies that you must also be employed by that store. An employee may be the manager for at most one store.
It's too much work to manage more than one store at the same time.
Stores can purchase many drones to deliver orders to customers in a timely manner. Each drone pilot can
control one drone at a time. It's unsafe for a human pilot to control more than one drone at a time. Each drone
has been purchased/sponsored by a single store, and is used to serve (e.g., carry orders for) that store alone. A
drone must be identified relative to the specific store that it serves.
Drones need to be taken out of service for maintenance after making a certain number of trips, where a trip is
equivalent to delivering one order. We must keep track of the number of trips that a drone has remaining
before it needs maintenance. Each drone has a limited capacity - measured in pounds - to carry orders up to a
maximum weight. A drone must be controlled by one pilot at a time. Having multiple pilots for a single drone
would eventually lead to conflicts and crashes.
Stores offer lots of different products, where each product has a 'universally' identifying barcode, a name, and a
weight measured in an even (i.e., integer) number of pounds. Customers who wish to purchase products can
place an order. Also, a specific product might be offered by many different stores. The inventory of possible
products is so large that we are not interested in tracking which stores sell which specific products. Our goal is
simply to ensure that each product identified by a specific barcode has a consistent name and weight for
tracking purposes.
An order must be requested by a specific customer and must also be assigned to a specific drone for eventual
delivery. Each order will have an identifying receipt number, and a record of the date on which the order was
placed. An order will consist of one or more lines, where each line represents a certain quantity (i.e., one or
more) of a product being ordered at a given unit price. Customers are allowed to place multiple orders
concurrently.
We must track a customer's rating as an integer from one (1) to five (5), where a higher number indicates that
the customer has been more reliable in ordering products over time. We must track the customer's credit as the
number of dollars that they have to request orders.
Our system must be able to calculate and display the cost of an order as the total cost of each line, which is the
cost of the product as listed on that order multiplied by the quantity purchased. Our system must be able to
calculate and display the total cost for all of the outstanding orders for each customer.
A customer's credit must always be greater than or equal to the total cost of all of the orders for which they are
currently waiting. A new order cannot be placed unless the customer requesting the order has enough credit to
cover all of the customer's existing and new orders.
Our system must be able to calculate and display the weight of an order as the total of the weight of each line,
which is the weight of the individual product multiplied by the quantity purchased. Our system must be able to
calculate and display the total weight (i.e., payload) for all of the orders being delivered by each drone. A new
order cannot be placed unless the drone assigned to deliver the order has enough lifting capacity to carry its
current orders along with the new order. Our system must be able to calculate and display the incoming
revenue for each store as the total cost of all orders currently being delivered by drones on behalf of that store.
Each product can be listed at most once on a given order, but the quantity for that product can be one or more.
The price (and the quantity) for a product can vary between different 
