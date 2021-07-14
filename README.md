# DMDB (the *Dunder Mifflin* Database)

This entry won't be as serious or instructional as other entries may be - this is just a bit of fun that I had at university that I would like to share. My team and I worked on this during the first semester of our third year, and it was a blast trying to fit the world of NBC's *The Office* into a system that makes sense. The show gives a lot of attention to detail to the company, usually used as a foil against characters, but this allowed us to extract some important information about *Dunder Mifflin* as a whole.

Here follows the analysis that my team and I did on the Dunder Mifflin company and their need for a database.

# Phase 1 - Database initial study

<p align="center">
  <img width="625" src="https://github.com/nuclearcheesecake/DMDB/blob/main/misc/phase1intro.png">
</p>

## 1. Company background

Dunder Mifflin is a paper and office supplies supplier founded in 1949 by Robert Dunder and
Robert Mifflin, with its headquarters located in New York City, New York. The company has
many branches across the United States of America, such as in Nashua, Scranton, Utica,
Akron and many more. It is based in the fictional universe of NBC’s The Office, but the
company on the show is modelled with such attention to detail that its operations can be
observed sufficiently to craft an operational database for its use.

There is a large disconnect between the sales and warehouse departments (both explained
in further detail below) in terms of data collection and sharing. Often, sales are made but are
dispatched late due to the poor handling of orders by the administration office. Records are
sometimes lost or misplaced, which worsens the problem. The company needs a data
management system in order to avoid these issues, as the company’s main selling point is
customer satisfaction rather than having a huge client base.

Corporate would also like to get a clearer picture of the daily operations of each branch.
Thus they have outsourced our company, Saber II, to help create and implement an
operational database for their corporate head office. This would not only solve the mishaps
in data sharing between each branch’s sales and warehouse department, but also give
corporate the chance to monitor the efficiency of each branch, and make sure that
everything operates smoothly.

## 2. Analysing the Company situation
### 2.1 Company objectives

Dunder Mifflin’s goal is to cater to local and small businesses’ paper and office needs. The
objectives set out by the company to achieve this goal are as follows:
* Building good relationships with clients.
* Ensuring client queries are always responded to and resolved in a swift manner.
* Ensuring safe and reliable delivery of their products to their clients.
* Turning a profit, but not at the cost of customer satisfaction.
* Maintaining a small client-base rather than a large one as it is easier to manage and
maintain. This also helps the company handle client queries without overwhelming
their staff.
* Earning and retaining the loyalty of their customers through charity work for the
community and sending gifts to clients’ offices.

### 2.2 Company operations

Dunder Mifflin’s role in the community is to serve as a middle-man retailer between paper
(and other supplies) factories and local business. Their day-to-day operations are as follows:

In the sales department, salesmen have the option to travel and close deals by solely visiting
potential clients, or to work in-office. The latter option is the most popular, and here clients
are contacted by the sales department via telephone, or alternatively, potential customers
phone in and enquire about the products and services Dunder Mifflin has to offer. Sometimes
sales are made over the telephone, other times a meeting is scheduled in order for the sales
representatives to meet the client in person and discuss with the client how to fulfil their
office needs.

Each closed deal is then documented on the respective sales representative’s report.
Sometimes, contracts are signed which entitles Dunder Mifflin to supply a client’s office
needs for an agreed term before the contract expires. Sales representatives receive a 1%
commission of each sale made.

Orders are sent to the warehouse department, where the order is packaged and dispatched
to the customer.
Once an order is delivered it is indicated and sent back to the office to keep track of
business operations. The warehouse is also responsible for maintaining the delivery
vehicles. It is the warehouse department’s responsibility to ensure that delivery times don’t
clash which results in deliveries being late.

The regional manager of each branch is required to keep track of all operations for the
respective branch, as well as conducting employee reports quarterly. If the branch manages
to stay under budget for the month, the manager receives a bonus of 15% of the saving
made.

The accounting department is responsible for calculating employee salaries based on their
base salary and any bonuses that may be paid out as well. They are also in charge of
keeping track of and reporting the expenditure of the branch based on the branch’s budget,
and the financial performance of the branch.

The HR department handles any internal disputes, assures that the branch is managed
ethically, and helps with the hiring process. All complaints against fellow employees are kept
on file and can be pulled for employee reports.

The product control department is in charge of making sure that the products received from
the branch’s suppliers are up to a certain quality standard. There are three main
responsibilities to be performed by this department:
* Supplier relations involve meeting with suppliers, and ordering the correct type and
quantity of stock needed to fill a branch's inventory at regular intervals. If there are
delays with deliveries expected from the suppliers, it is the responsibility of the
product control staff to enquire with the supplier and try to rectify the mishap.
* Customer service representatives are required to answer calls from clients regarding
any queries, compliments or complaints. If a compliment or complaint is received, it
must be recorded and filed. Staff members of this department occasionally send out
gift baskets to unsatisfied clients. This must be disclosed and recorded as it forms
part of branch expenditure.
* Quality assurance representatives discuss any faults found with products, and
perform site visits to the manufacturer’s factories to inspect the quality standards of
the factory. They are also allowed to perform inspections on samples taken from
stock in the warehouse.

Finally, the office administrator is in charge of making sure that everything in the office runs
smoothly. This involves making sure that office stationery is available, as well as other small
maintenance responsibilities for the office. Any money spent by the administrator towards
office upkeep must be recorded and filed.

Company logo:

<p align="center">
  <img width="525" src="https://github.com/nuclearcheesecake/DMDB/blob/main/misc/dunder-mifflin-logo-5E325D4D51-seeklogo.com.png">
</p>

### 2.3 Organisational structure

Dunder Mifflin is governed top-down by their Corporate Headquarters’ branch in New York
City. The day-to-day operations per regional branch, as described in the section above, are
performed by various departments, with their own internal structure. See the following page
for the Organisational Chart for Dunder Mifflin.

<ins> Notes on the following diagram: </ins>
* The locations of the regional branches do not include every Dunder Mifflin branch to
ever have existed. The locations listed are those branches that are still operational to
this day.
* The structures in blue will be the same for each location, as each location represents
a regional branch.

<p align="center">
  <img width="825" src="https://github.com/nuclearcheesecake/DMDB/blob/main/misc/DM_ORGCHART.jpg">
</p>

## 3. Defining Problems and Constraints
### 3.1 Problems

* Orders made are not placed to the warehouse on time.
* Lack of documentation or late documentation for every order whether successful or
not.
* Unorganized order placements can result in delivery conflictions and late deliveries.
* Records of orders made are lost or misplaced.
* Late order placements to warehouse can result in scheduling difficulties.
* Warehouse employees can become stressed out due to rushed orders.
* Delivery conflictions result in extra expenses.
* Late deliveries can result in customer dissatisfaction and loss in customer loyalty.
* Inaccurate timely reports.
* Poor stock management - quality assurance rep struggles to keep track of which
stock has been checked, and the inventory system may be outdated or not easy to
use.
* No travel history for salesmen who leave to close deals.
* No current system in place
* No record of clients visited where deals were unsuccessful. No procedure thereafter.
* No follow-up with clients for feedback on delivered goods.
* Unanswered calls lead to unsatisfied customers.
* Data anomalies will be present in departments reports - thus the need to align
reports, as well as combine reports of branches for corporate.
* Sales Team experiences great pressure due to risk of losing contracts of customers
who don’t receive timely deliveries.
* No fill in for sick or ill drivers.

### 3.2 Constraints

* Each contract may only involve one salesman.
* Each salesman may be in-office OR travelling
* Each client order placed has an order number.
* Client feedback is classified as complaint/compliment and tallied per salesman.
* There are a limited number of vehicles for deliveries per branch, and each vehicle is
either available or not at a certain time.
* Each salesman has a unique employee number.
* Each order to a supplier has an invoice number.
* Each salesman earns 1% commission on a sale they made.

## 4. Database System Specification
### 4.1 Objectives to solve identified problems

In order to solve Dunder Mifflin’s problems, a database is a clear solution. This way all the
sales and their deliveries can be managed efficiently, stock can be updated in real-time, and
corporate can watch and keep control of the daily operations in all their branches.

The database will need to have the following characteristics:

* The database will be decentralized, as each department (sales, warehouse, supplier
relations) will have a say in the design of the structure of their relevant part of the
operational database. Each unit thus creates a subset of the larger system, which will
then be standardised across all branches once Saber II has completed their analysis.
* The database must be permission based so that only certain data is present for
specific employees - eg, the foreman for the warehouse at the Utica branch can only
see sales made by Utica salespeople and Utica’s clients, but David Wallace (CFO)
can see all sales and contracts.
* Database entry and retrieval must be fast, so that the sale orders are sent out to the
warehouse effectively to ensure quick delivery for customer satisfaction - this must
thus be automated whenever a salesman closes a deal.
* The database must schedule deliveries according to sale orders or contracts.
* The database must record (for each branch):
  * The salesmen
  * Inventory (products available with their amount in stock)
  * Contracts
  * Once-off sales
  * Orders received from suppliers
  * Deliveries due
  * Delivery vehicles on hand
  * Delivery staff
  * Clients and their location
* There should also be data on the different branches, and each regional manager
(including whether or not they receive the 15% bonus).
* Reports must be generated monthly regarding the efficiency of sales and delivery
per branch.

We need a system that will allow specific (access restrictions granted, per branch or level of
management) employees to access and modify information or data relevant to their job and
department objectives. This might involve writing reports, entering information after a
successful sale, or overseeing automated entries, such as delivery due dates.

Thus the proposed initial objective of the database will be to store and manage information
about all sales (including inputs/salesmen and output/warehouse) to ensure a streamlined
approach to business while keeping the customers happy. Eventually the database could
connect to a HR/customer relations database to create a more complex view of each
salesman and their performance, or interface with suppliers’ own databases to automatically
order stock. But for now the system will mainly focus on creating timely deliveries and
generating reports for corporate.

Thus the benefits of this new database can be seen as:

* Removal of data anomalies as the database gives a complete and accurate view of
company operations, available regionally to each employee, and totally to corporate
management.
* Increase in customer satisfaction with timely deliveries.
* Sales history for each salesman recorded, and thus accurate commission.
* Organisation of all sales results in the resolution of delivery conflicts.
* Decrease of time mismanagement, as when in doubt, an employee can check the
database to see what tasks need to be fulfilled.
* Useful reports for management to reward branches/salespeople with bonuses or
promotions.


### 4.2 Information that company requires from database

Ultimately, the company wants to know when sales are made, and how that affects the
inventory and delivery staff. In the process, additional information that could improve report
generation (such as salesmen’s tallies of compliments/complaints, and quality assurance of
inventory) can also be included.

We will now list some proto-entities (data needed by Dunder Mifflin on certain objects, which
the database might be able to include as entities in our conceptual model).

Firstly, there will need to be data based on branches. This is to be able to bin all relevant
salesmen, sales and deliveries into the correct branch. Branch data includes:

* Branch name
* Physical address
* Regional manager
* Amount of delivery vehicles

There should also be a table with information on regional managers:

* Employee number
* Name and surname
* Which branch they manage
* Date started management position
* 15% bonus this year Yes/No, thus Under/Over budget
* Salary
* Bonus amount to add to salary

The database should also record data on each salesman when they are appointed at the
company:

* Employee number
* Branch name
* Name and surname
* Travelling or In-office
* Contact details
* Address
* Next of kin
* Next of kin contact details
* Salary earned
* Commission earned
* Salary pay date
* Total complaints
* Total compliments

Similar data should be captured for delivery staff:

* Employee number
* Branch name
* Name and surname

There should be a data instance for each client, containing important information:

* Client organisation name
* Client physical address
* Client telephone number
* Client e-mail address
* Contract or once-off deal historically

Sometimes, contracts are signed which entitles Dunder Mifflin to supply a client’s office
needs for an agreed term before the contract expires. In this case, the details captured are:

* Client organisation name
* Agreed benefits such as discounts, if any
* Contract start date
* Contract expiry date
* Sales representative’s name
* Sales representative’s employee number

The details captured for every once-off sale made are as follows:

* Client organisation name
* Products sold
* Services to be provided
* Sales representative’s employee number
* Time sale was made
* Total amount owed
* Date of order placement

Both types of sale are recorded by the relevant salesman when the sale/contract is finalised.

There should then also be data on the deliveries due, which will be automatically generated
by using data from once-off sales and contracts. The warehouse receives the following
information:

* Branch (from where to be delivered)
* Client organisation name (to be delivered to)
* Products to be delivered
* Date of order placement

Information is stored regarding the fleet of delivery vehicles per branch as follows, to be
updated continually by drivers:

* Vehicle VIN
* Vehicle license plate number
* Vehicle model name
* Vehicle model year
* Vehicle size
* Date of last service
* Codes of services due, if any
* Vehicle availability (if the vehicle is on the road or at the branch)

Next, data on the inventory/products should be recorded:

* Material number (Material can be regarded as anything that can be bought, stored,
and sold)
* Material description
* Branch at which available (there thus might be multiple instances of the same
material, but with differing values in the branch attribute).
* Bin number at branch (Binning is basically storage in a specific labeled location, such
as a specific rack in a specific warehouse)
* Material quantity
* Quality assurance check (has the rep checked it?)
* Certificates
* Special instructions (What if the material is fragile?)
* Reorder point (level of inventory which triggers an action to replenish that particular
inventory stock)
* Minimum order quantity
* Value
* Supplier

And then also information regarding the suppliers of each branch’s inventory:

* Vendor name
* Vendor address
* Payment terms
* Contract number
* Vendor accreditation (check that a supplier meets certain minimum criteria)
* Contact details
* Contact person
* Supplier performance rating (out of 10 - helps management monitor if supplier
contract should be renewed)
* Annual supplier spending (How much you spend with a given supplier annually)

It would also be helpful if the regional manager receives information such as:

* Sales made per half year for each employee
* Deliveries made on time
* Late deliveries
* Employees with a series of complaints

And corporate received information on:

* Branch growth
* Performance comparisons of branches
* Over-/Under-performing salesmen

### 4.5 Scope

There are several interrelated problems in Dunder Mifflin that can be solved using a single
database. The database we create will thus be a conglomeration of the following areas of
information, drawing from each to serve the ultimate purpose:

* *Organizational data* - This information is formalised and managed by corporate to
keep track of employees. Access to be given to regional management and HR. The
attributes stored per salesman can be obtained from the proto-entity section above.
* *Inventory data* - For use in the warehouse department, as well as supplier relations
and quality assurance. Without this data in our database, Dunder Mifflin could run
into delivery conflicts.
* *Supplier data* - Information on various suppliers. The attributes listed above for
suppliers are standard across industry, used by most businesses in the same
industry as Dunder Mifflin.
* *Customer data* - This enables salesmen to form relationships and make regular sales
(especially through contracts) and also let’s the warehouse keep track of what and
where to deliver.
* *Sales data* - The database should be able to update delivery tables when sales are
made, update inventory when stock is dispatched, etc..

Although this seems like a big problem with complicated objectives, there are restrictions to
what the database will be able to do.

We will not include detailed employee complaints from HR, only a tally (+1 for each
complaint filed), and the same for compliments.
We also will not include full quality assurance reports, as that would serve no purpose in the
database. The inventory table is there because the delivery staff needs to be able to ship
stock on time, and this table eases the process of keeping the inventory full and accurately
deducting material counts as a shipment goes out, as well as indicate whether or not there
has been a quality assurance check, otherwise the material can’t be shipped, or will be
shipped with possible faults.
Both of these are thus a part of the database in some way, but not to their fullest extent, so
only relevant data will be captured.

Not all employees’ data will be captured. This is not a complete organisational database.
Only employees relevant to the sales and delivery process, and regional management.

It is also not a database for accounting purposes. Thus we do not record every transaction
(such as if the office administrator buys pens) nor overtime worked by employees - even
salesmen. The sales are recorded purely to be able to dispatch deliveries, and record a
salesman’s history, so that corporate can track possible promotion candidates. The salaries
of salesmen are also recorded for this purpose.

### 4.4 Boundaries

There exists different levels of boundaries to build this database:

* Financial:
  * Dunder Mifflin will give us a specified budget. This should cover all our
operational costs, and we may not exceed this.
  * So far the budget stands at R250 000.
  * Software licensing might raise the cost of the system.
* Software:
  * The software used must be able to integrate into their computer system - the
only requirement is Windows 10.
  * Additional software needed will have to be installed by our package we
deliver to them.
  * The database will also only be available on the company’s intranet, so remote
access from the internet will be impossible.
* Physical:
  * The database needs to be able to run on the local machines of every branch
and not just corporate - thus it needs to be compatible with their hardware.
  * There is no prior database system, but our database still needs to run on
hardware with a good CPU, otherwise the benefit of speed might be lost.
  * Memory on computers at regional branches might be more limited than at
corporate, but hopefully the accessing restrictions placed on regional
branches will cause the database to fit. Corporate will have the infrastructure
to handle the entire database.
  * We are only 6 people in our project team, each with limited time on our hands.
* Temporal:
  * We have exactly 10 weeks to design, build and implement the database.
  * We will also have to meet with representatives of the company at regular
intervals to give them deliverables, and discuss the state of the project. This
will use more of our time.

