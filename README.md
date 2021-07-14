# DMDB (the *Dunder Mifflin* Database)

This entry won't be as serious or instructional as other entries may be - this is just a bit of fun that I had at university that I would like to share. My team and I worked on this during the first semester of our third year, and it was a blast trying to fit the world of NBC's *The Office* into a system that makes sense. The show gives a lot of attention to detail to the company, usually used as a foil against characters, but this allowed us to extract some important information about *Dunder Mifflin* as a whole.

Here follows the analysis that my team and I did on the Dunder Mifflin company and their need for a database.

(Note that, although I lead the team, I did not solely do all of the work. I do not want to post my team members' information on the internet, but if a reputable person communicates privately with me, I can contact my team members and confirm whether they would be comfortable sharing their information with such a person. We also made a video about the project that is available on request, once again because I do not feel comfortable sharing anyone's media without their consent on who will be able to see it. Enjoy the project!)

## Table of contents

[Phase 1 - Database initial study](#1)
[1. Company background](#2)
[2. Analysing the Company situation](#3)
[2.1 Company objectives](#4)
[2.2 Company operations](#5)
[2.3 Organisational structure](#6)
[3. Defining Problems and Constraints](#7)
[3.1 Problems](#8)
[3.2 Constraints](#9)
[4. Database System Specification](#10)
[4.1 Objectives to solve identified problems](#11)
[4.2 Information that company requires from database](#12)
[4.5 Scope](#13)
[4.6 Boundaries](#14)

[Phase 2 - Conceptual design](#15)
[1. Conceptual design](#16)
[1.1 Business rules](#17)
[1.2 Entity-Relationship diagram](#18)

[Phase 3 - Physical design](#19)
[1. Database objects](#20)
[1.1 Physical data model](#21)
[1.2 Oracle physical data model](#22)
[1.3 Creating tables](#23)
[1.4 Indexes](#24)
[1.5 Constraints](#25)
[1.6 Data entry](#26)
[1.7 Views](#27)
[2. Queries](#28)
[2.1 Ensuring company specifications](#29)
[2.2 Sequences used](#30)
[2.3 Extra functionality](#31)

<a name="1"></a>
# Phase 1 - Database initial study

<p align="center">
  <img width="625" src="https://github.com/nuclearcheesecake/DMDB/blob/main/misc/phase1intro.png">
</p>

<a name="2"></a>
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

<a name="3"></a>
## 2. Analysing the Company situation
<a name="4"></a>
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

<a name="5"></a>
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

<ins> Company logo: </ins>

<p align="center">
  <img width="525" src="https://github.com/nuclearcheesecake/DMDB/blob/main/misc/dunder-mifflin-logo-5E325D4D51-seeklogo.com.png">
</p>

<a name="6"></a>
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

<a name="7"></a>
## 3. Defining Problems and Constraints
<a name="8"></a>
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

<a name="9"></a>
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

<a name="10"></a>
## 4. Database System Specification
<a name="11"></a>
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

<a name="12"></a>
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

<a name="13"></a>
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

<a name="14"></a>
### 4.6 Boundaries

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

<a name="15"></a>
# Phase 2 - Conceptual design
<a name="16"></a>
## 1. Conceptual design
<a name="17"></a>
### 1.1 Business rules

* The database holds many businesses/persons who are restricted to only access certain
parts of it.
* An employee can be a sales employee.
* An employee can be a delivery employee.
* An employee can be a regional manager employee.
* The sales employees get paid a base salary, the delivery employees get paid an hourly
wage, and the regional manager employee gets paid a base salary.
* A sales employee can make many deals for which they earn a commission.
* Regional managers earn an annual 15% bonus if their branch is under budget.
* Zero or many sales can be placed by one client, which is made by one and only one
salesman.
* All employees are entitled to only one employee ID.
* Many businesses have only one client number if they place sales, or a vendor name if
they supply products.
* Every sale made is fined to only one client.
* Multiple purchases by a business each generates a sale invoice number.
* One client can have zero or many deliveries due, but a delivery is only due to one
client.
* One supplier can hold zero or mary contracts, which supplies one to many products to
each branch.
* A product can only be supplied by one contract, and a contract can only be held by
one supplier.
* Each branch can have zero or many supply contracts.
* Many deliveries can be made by one driver.
* Feedback received from multiple customers whether compliments or complaints are
passed on to a single department and then resolved.
* A single branch can have many employees.
* A delivery vehicle can deliver multiple products.
* Date requirements for the database have been stipulated in section 4.2 of Phase 1.

<a name="18"></a>
### 1.2 Entity-Relationship diagram

For the sake of brevity, I will only include the final ERD we submitted, after normalisation:

<p align="center">
  <img width="825" src="https://github.com/nuclearcheesecake/DMDB/blob/main/misc/ERD.png">
</p>

The following elements can be seen in the ERD above:

* Optional/Mandatory relationships
  * We have certain optional relationships, such as in a poor year, a salesman
might not make any sales, and SALE is thus in an optional relationship with
SALESMAN.
  * Another optional relationship exists between a CLIENT and its
DELIVERIES_DUE, since at a given moment, a client may not require any
deliveries to be made, but the client details are stored to be able to propose
sales in the future.
  * A mandatory relationship exists between a BRANCH and their PRODUCTs,
since a branch would not exist without its inventory (a collection of
PRODUCTs).
* Weak / strong relationships
  * A BRANCH has a weak relationship with EMPLOYEE, since the EMP_NUM
does not depend on the BRANCH_NUM - this makes sense as an employee
is employed by Dunder Mifflin, and not a specific branch, thus their primary
key would not need to be identified by the branch they are in (see image on
next page).
  * BRANCH and SUPPLIER_CONTRACT has a strong relationship, since the
specific contract will be determined by the branch it needs to supply.
* Recursive relationships
  * EMPLOYEE is a recursive relationship, since a regional manager employee is
related to the delivery and sales employees by virtue of managing them - a regional manager can thus manage one or more employees, himself/herself
also being an employee.
* Weak entities
  * The NEXT_OF_KIN entity is weak, since it is existence-dependent on the
EMPLOYEE entity. Its primary key is derived from keys within the
EMPLOYEE entity as well.
  * In the same way, DELIVERIES_DUE is weak because the DEL_NUM will be
generated from the SALES_INVOICE_NUM, and its existence depends on a
sale being made.
* Multi-valued attributes
  * A CLIENT may have made more than one sale thus the SALE_INVOICE_NUM per client can be multi-valued. The same holds for
DEL_NUM - a client may be expecting more than one delivery.
  * In a SALE, a client may order more than one PRODUCT - thus MAT_NUM in
SALE can also be multi-valued (see above).
* Derived attributes
  * The total salary of both the salesman and the regional manager can be
derived from their employee salary and their commission/bonus.
  * The total amount due per sale can be derived by multiplying the quantity by
the price in the PRODUCT entity, and minussing the discount.

<a name="19"></a>
# Phase 3 - Physical design
<a name="20"></a>
## 1. Database objects
<a name="21"></a>
### 1.1 Physical data model

<p align="center">
  <img width="825" src="https://github.com/nuclearcheesecake/DMDB/blob/main/misc/physical.png">
</p>

<a name="22"></a>
### 1.2 Oracle physical data model
<p align="center">
  <img width="825" src="https://github.com/nuclearcheesecake/DMDB/blob/main/misc/oraclephysical.png">
</p>

<a name="23"></a>
### 1.3 Creating tables

```
CREATE TABLE "EMPLOYEE" (
"EMP_NUM" NUMBER(6),
"BRANCH_NUM" NUMBER(4),
"EMP_NAME" VARCHAR(100),
"EMP_SURNAME" VARCHAR(100),
PRIMARY KEY ("EMP_NUM")
);
```

```
CREATE TABLE "DELIVERY_STAFF" (
"EMP_NUM" NUMBER(6),
"BRANCH_NUM" NUMBER(4),
"DELV_HRS_TRVLD" NUMBER(5),
"DELV_WAGE" NUMBER(12,2),
PRIMARY KEY ("EMP_NUM")
);
```

```
CREATE TABLE "SALESMAN" (
"EMP_NUM" NUMBER(6),
"BRANCH_NUM" NUMBER(4),
"SLSMN_TRAVEL" CHAR,
"SLSMN_COMMISSION" NUMBER(3,2),
"SLSMN_TOTAL_SALARY" NUMBER(12,2),
PRIMARY KEY ("EMP_NUM")
);
```

```
CREATE TABLE "REGIONAL_MANAGER" (
"EMP_NUMBER" NUMBER(6),
"BRANCH_NUM" NUMBER(4),
"MAN_DATE_APPOINTED" DATE,
"MAN_BONUS" NUMBER(12,2),
"MAN_TOTAL_SALARY" NUMBER(12,2),
PRIMARY KEY ("EMP_NUMBER")
);
```

```
CREATE TABLE "SALE" (
"SALE_INVOICE_NUM" NUMBER(16),
"MAT_NUM" NUMBER(6),
"CLIENT_NUM" NUMBER(6),
"EMP_NUM" NUMBER(6),
"SALE_DISCOUNT" NUMBER(3,2),
"SALE_QUANTITY" NUMBER(9),
"SALE_TOTAL_DUE" NUMBER(12,2),
"SALE_TYPE" VARCHAR(100),
PRIMARY KEY ("SALE_INVOICE_NUM")
);
```

```
CREATE TABLE "CONTRACT_SALE" (
"SALE_INVOICE_NUM" NUMBER(16),
"MAT_NUM" NUMBER(6),
"CLIENT_NUM" NUMBER(6),
"EMP_NUM" NUMBER(6),
"CONTR_START_DATE" DATE,
"CONTR_EXPIRY_DATE" DATE,
PRIMARY KEY ("SALE_INVOICE_NUM")
);
```

```
CREATE TABLE "ONCE_OFF_SALE" (
"SALE_INVOICE_NUM" NUMBER(16),
"MAT_NUM" NUMBER(6),
"CLIENT_NUM" NUMBER(6),
"EMP_NUM" NUMBER(6),
"SALE_DATE" DATE,
"SALE_TIIME" DATE,
PRIMARY KEY ("SALE_INVOICE_NUM")
);
```

```
CREATE TABLE "BRANCH" (
"BRANCH_NUM" NUMBER(4),
"REG_MANAGER" VARCHAR(100),
"BRANCH_PHYS_ADRESS" VARCHAR(100),
"BRANCH_NUM_VEHICLES" NUMBER(4),
PRIMARY KEY ("BRANCH_NUM")
);
```

```
CREATE TABLE "NEXT_OF_KIN" (
"KIN_CONTACT, EMP_NUM" NUMBER(17),
"KIN_SURNAME" VARCHAR(100),
"KIN_NAME" VARCHAR(100)
);
```

```
CREATE TABLE "SUPPLIER_CONTRACT" (
"CONTR_INVOICE_NUM" NUMBER(16),
"BRANCH_NUM" NUMBER(4),
"MAT_NUM" NUMBER(6),
"VENDOR_NUM" NUMBER(5),
"CONTR_AMOUNT" NUMBER(12,2),
"CONTR_START_DATE" DATE,
"CONTR_EXPIRY_DATE" DATE,
"CONTR_DISCOUNT" NUMBER(3,2),
PRIMARY KEY ("CONTR_INVOICE_NUM")
);
```

```
CREATE TABLE "PRODUCT" (
"MAT_NUM" NUMBER(6),
"BRANCH_NUM" NUMBER(4),
"CONTR_INVOICE_NUM" VARCHAR(16),
"PROD_DESCR" VARCHAR(16),
"PROD_BIN_NUM" NUMBER(6),
"PROD_QUANTITY_STOCKED" NUMBER(9),
"PROD_QUALITY_CHECK" VARCHAR(100),
"PROD_CERTIFICATES" VARCHAR(1000),
"PROD_SPECIAL_INSTR" VARCHAR(100),
"PROD_REORDER_POINT" NUMBER(1000),
"PROD_MIN_ORDER_QUANT" NUMBER(9),
"PROD_PRICE" NUMBER(12,2),
PRIMARY KEY ("MAT_NUM")
);
```

```
CREATE TABLE "SUPPLIER" (
"VENDOR_NUM" NUMBER(5),
"VEND_NAME" VARCHAR(100),
"VEND_PHYS_ADDRESS" VARCHAR(100),
"VEN_PAY_TERMS" VARCHAR(1000),
"VEN_ACCRED" CHAR,
"VEN_TEL_NUM" NUMBER(11),
"VEN_EMAIL" VARCHAR(100),
"VEN_PERF_RATING" CHAR,
"VEN_ANNUAL_SPENDING" NUMBER(12,2),
PRIMARY KEY ("VENDOR_NUM")
);
```

```
CREATE TABLE "DELIVERY_VEHICLE" (
"VEC_VIN" Type,
"BRANCH_NUM" Type,
"VEC_PLATE" Type,
"VEC_MODL_NAME" Type,
"VEC_MODEL_YR" Type,
"VEC_SIZE" Type,
"VEC_LAST_SERVICE" Type,
"VEC_SERVICE_CODE" Type,
"VEC_AVAILABLE" Type,
PRIMARY KEY ("VEC_VIN")
);
```

```
CREATE TABLE "DELIVERIES_DUE" (
"SALE_INVOICE_NUM" NUMBER(16),
"DEL_NUM" NUMBER(7),
"MAT_NUM" NUMBER(6),
"DEL_LOCATION" VARCHAR(100),
"DEL_DATE" DATE,
PRIMARY KEY ("DEL_NUM")
);
```

```
CREATE TABLE "CLIENT" (
"CLIENT_NUM" NUMBER(6),
"CLIENT_NAME" VARCHAR(100),
"CLIENT_PHYS_ADRRESS" VARCHAR(100),
"CLIENT_TEL_NUM" NUMBER(11),
"CLIENT_EMAIL" VARCHAR(100),
"CLIENT_CONTRACT" VARCHAR(100),
PRIMARY KEY ("CLIENT_NUM")
);
```

```
CREATE TABLE "DELIVERY_VEHICLE" (
"VEC_VIN" Type,
"BRANCH_NUM" Type,
"VEC_PLATE" Type,
"VEC_MODL_NAME" Type,
"VEC_MODEL_YR" Type,
"VEC_SIZE" Type,
"VEC_LAST_SERVICE" Type,
"VEC_SERVICE_CODE" Type,
"VEC_AVAILABLE" Type,
PRIMARY KEY ("VEC_VIN")
);
```

<a name="24"></a>
### 1.4 Indexes 

```
CREATE INDEX "FK1" ON "REGIONAL_MANAGER" ("BRANCH_NUM");
```

```
CREATE INDEX "FK1" ON "SALE" ("MAT_NUM");
CREATE INDEX "FK2" ON "SALE" ("CLIENT_NUM");
CREATE INDEX "FK3" ON "SALE" ("EMP_NUM");
```

```
CREATE INDEX "FK1" ON "CONTRACT_SALE" ("MAT_NUM");
CREATE INDEX "FK2" ON "CONTRACT_SALE" ("CLIENT_NUM");
CREATE INDEX "FK3" ON "CONTRACT_SALE" ("EMP_NUM");
```

```
CREATE INDEX "FK1" ON "ONCE_OFF_SALE" ("MAT_NUM");
CREATE INDEX "FK2" ON "ONCE_OFF_SALE" ("CLIENT_NUM");
CREATE INDEX "FK3" ON "ONCE_OFF_SALE" ("EMP_NUM");
```

```
CREATE INDEX "FK1" ON "BRANCH" ("REG_MANAGER");
```

```
CREATE INDEX "PK,FK1" ON "NEXT_OF_KIN" ("KIN_CONTACT, EMP_NUM");
```

```
CREATE INDEX "PK,FK1" ON "SUPPLIER_CONTRACT" ("BRANCH_NUM");
CREATE INDEX "FK2" ON "SUPPLIER_CONTRACT" ("MAT_NUM");
CREATE INDEX "FK3" ON "SUPPLIER_CONTRACT" ("VENDOR_NUM");
```

```
CREATE INDEX "PK,FK1" ON "PRODUCT" ("BRANCH_NUM");
CREATE INDEX "FK2" ON "PRODUCT" ("CONTR_INVOICE_NUM");
```

```
CREATE INDEX "PK,FK1" ON "DELIVERIES_DUE" ("SALE_INVOICE_NUM");
CREATE INDEX "FK2" ON "DELIVERIES_DUE" ("MAT_NUM");
```

<a name="25"></a>
### 1.5 Constraints

Some columns have special requirements for the database to work properly, and thus need
constraints:

```
ALTER TABLE "BRANCH" MODIFY ("BRANCH_NUM" NOT NULL ENABLE);
ALTER TABLE "CLIENT" MODIFY ("CLIENT_NUM" NOT NULL ENABLE);
ALTER TABLE "CLIENT" ADD CONSTRAINT "UNIQUE_NAME" UNIQUE
("CLIENT_NAME");
ALTER TABLE "CONTRACT_SALE" MODIFY ("SALE_INVOICE_NUM" NOT NULL
ENABLE);
ALTER TABLE "CONTRACT_SALE" MODIFY ("PROD_NUM" NOT NULL ENABLE);
ALTER TABLE "CONTRACT_SALE" MODIFY ("CLIENT_NUM" NOT NULL ENABLE);
ALTER TABLE "DELIVERIES_DUE" MODIFY ("SALE_INVOICE_NUM" NOT NULL
ENABLE);
ALTER TABLE "DELIVERIES_DUE" MODIFY ("DEL_NUM" NOT NULL ENABLE);
ALTER TABLE "DELIVERY_STAFF" MODIFY ("EMP_NUM" NOT NULL ENABLE);
ALTER TABLE "EMPLOYEE" MODIFY ("EMP_NUM" NOT NULL ENABLE);
ALTER TABLE "NEXT_OF_KIN" MODIFY ("EMP_NUM" NOT NULL ENABLE);
ALTER TABLE "ONCE_OFF_SALE" MODIFY ("SALE_INVOICE_NUM" NOT NULL
ENABLE);
ALTER TABLE "PRODUCT" MODIFY ("MAT_NUM" NOT NULL ENABLE);
ALTER TABLE "PRODUCT" MODIFY ("BRANCH_NUM" NOT NULL ENABLE);
ALTER TABLE "PRODUCT" MODIFY ("CONTR_INVOICE_NUM" NOT NULL ENABLE);
ALTER TABLE "REGIONAL_MANAGER" MODIFY ("EMP_NUM" NOT NULL ENABLE);
ALTER TABLE "SALE" MODIFY ("SALE_INVOICE_NUM" NOT NULL ENABLE);
ALTER TABLE "SALE" MODIFY ("PROD_NUM" NOT NULL ENABLE);
ALTER TABLE "SALE" MODIFY ("CLIENT_NUM" NOT NULL ENABLE);
ALTER TABLE "SALE" MODIFY ("EMP_NUM" NOT NULL ENABLE);
ALTER TABLE "SALESMAN" MODIFY ("EMP_NUM" NOT NULL ENABLE);
ALTER TABLE "SUPPLIER" MODIFY ("VENDOR_NUM" NOT NULL ENABLE);
ALTER TABLE "SUPPLIER" ADD CONSTRAINT "UNIQUE_NAME_VEND" UNIQUE
("VEND_NAME");
ALTER TABLE "SUPPLIER_CONTRACT" MODIFY ("CONTR_INVOICE_NUM" NOT
NULL ENABLE);
```

<a name="26"></a>
# 1.6 Data entry

Data for each entity has been entered to test the functionality of the database as follows,
either by using the **DATA** tab in Oracle SQL Developer, or by using the queries explained in
the following sections.

* BRANCH 
<p align="center">
  <img width="625" src="https://github.com/nuclearcheesecake/DMDB/blob/main/misc/branch.png">
</p>

* CLIENT
<p align="center">
  <img width="625" src="https://github.com/nuclearcheesecake/DMDB/blob/main/misc/client.png">
</p>

* CONTRACT_SALE
<p align="center">
  <img width="625" src="https://github.com/nuclearcheesecake/DMDB/blob/main/misc/contract_sale.png">
</p>

* DELIVERIES_DUE
<p align="center">
  <img width="625" src="https://github.com/nuclearcheesecake/DMDB/blob/main/misc/deliveries_due.png">
</p>

* DELIVERY_STAFF
<p align="center">
  <img width="625" src="https://github.com/nuclearcheesecake/DMDB/blob/main/misc/delivery_staff.png">
</p>

* EMPLOYEE
<p align="center">
  <img width="625" src="https://github.com/nuclearcheesecake/DMDB/blob/main/misc/employee.png">
</p>

* NEXT_OF_KIN
<p align="center">
  <img width="625" src="https://github.com/nuclearcheesecake/DMDB/blob/main/misc/next_of_kin.png">
</p>

* ONCE_OFF_SALE
<p align="center">
  <img width="625" src="https://github.com/nuclearcheesecake/DMDB/blob/main/misc/once_off_sale.png">
</p>

* PRODUCT
<p align="center">
  <img width="625" src="https://github.com/nuclearcheesecake/DMDB/blob/main/misc/product.png">
</p>

* REGIONAL_MANAGER
<p align="center">
  <img width="625" src="https://github.com/nuclearcheesecake/DMDB/blob/main/misc/regional_manager.png">
</p>

* SALE
<p align="center">
  <img width="625" src="https://github.com/nuclearcheesecake/DMDB/blob/main/misc/sale.png">
</p>

* SALESMAN
<p align="center">
  <img width="625" src="https://github.com/nuclearcheesecake/DMDB/blob/main/misc/salesman.png">
</p>

* SUPPLIER
<p align="center">
  <img width="625" src="https://github.com/nuclearcheesecake/DMDB/blob/main/misc/supplier.png">
</p>

* SUPPLIER_CONTRACT
<p align="center">
  <img width="625" src="https://github.com/nuclearcheesecake/DMDB/blob/main/misc/supplier_contract.png">
</p>

<a name="27"></a>
## 1.7 Views

Firstly, we can create views for both the employees and the sales made by each individual
branch:

```
CREATE VIEW scranton_emp_view AS SELECT * FROM EMPLOYEE WHERE
BRANCH_NUM = 1702;
CREATE VIEW akron_emp_view AS SELECT * FROM EMPLOYEE WHERE
BRANCH_NUM = 1700;
CREATE VIEW albany_emp_view AS SELECT * FROM EMPLOYEE WHERE
BRANCH_NUM = 1704;
CREATE VIEW nashua_emp_view AS SELECT * FROM EMPLOYEE WHERE
BRANCH_NUM = 1703;
CREATE VIEW rochester_emp_view AS SELECT * FROM EMPLOYEE WHERE
BRANCH_NUM = 1705;
CREATE VIEW utica_emp_view AS SELECT * FROM EMPLOYEE WHERE
BRANCH_NUM = 1701;
CREATE VIEW syracuse_emp_view AS SELECT * FROM EMPLOYEE WHERE
BRANCH_NUM = 1706;

CREATE VIEW scranton_sales_view AS SELECT * FROM SALE WHERE EMP_NUM IN
(SELECT EMP_NUM FROM EMPLOYEE WHERE BRANCH_NUM = 1702);
CREATE VIEW akron_sales_view AS SELECT * FROM SALE WHERE EMP_NUM IN
(SELECT EMP_NUM FROM EMPLOYEE WHERE BRANCH_NUM = 1700);
CREATE VIEW albany_sales_view AS SELECT * FROM SALE WHERE EMP_NUM IN
(SELECT EMP_NUM FROM EMPLOYEE WHERE BRANCH_NUM = 1704);
CREATE VIEW nashua_sales_view AS SELECT * FROM SALE WHERE EMP_NUM IN
(SELECT EMP_NUM FROM EMPLOYEE WHERE BRANCH_NUM = 1703);
CREATE VIEW rochester_sales_view AS SELECT * FROM SALE WHERE EMP_NUM IN
(SELECT EMP_NUM FROM EMPLOYEE WHERE BRANCH_NUM = 1705);
CREATE VIEW utica_sales_view AS SELECT * FROM SALE WHERE EMP_NUM IN
(SELECT EMP_NUM FROM EMPLOYEE WHERE BRANCH_NUM = 1701);
CREATE VIEW syracuse_sales_view AS SELECT * FROM SALE WHERE EMP_NUM IN
(SELECT EMP_NUM FROM EMPLOYEE WHERE BRANCH_NUM = 1706);
```

We can see that, for example, the Scranton views, show only data of the Scranton branch:

<p align="center">
  <img width="625" src="https://github.com/nuclearcheesecake/DMDB/blob/main/misc/views.png">
</p>

But if we wish to see the company from an overall perspective, we can use the following
views:

```
CREATE VIEW dm_emp_view AS SELECT * FROM EMPLOYEE;
CREATE VIEW dm_sales_view AS SELECT * FROM SALE;
```

We can also get a more chronological view of the sales’ history, and which client bought
which product, using this view:

```
CREATE VIEW combsales_view
AS SELECT o.SALE_DATE_TIME, o.SALE_INVOICE_NUM, c.CLIENT_NAME,
p.PROD_DESCR
FROM ONCE_OFF_SALE o
JOIN CLIENT c USING(CLIENT_NUM)
JOIN PRODUCT p USING(PROD_NUM)
ORDER BY o.SALE_DATE_TIME ASC;
```

A similar view can be done for the contract sales, but this view can instead be used by a
salesman to check when a contract is close to expiring, and then using the view to contact
the clients closer to the top to try and sell a new contract to them, thus also calculating how
long the current contract is, to be able to personalise their call, sticking to the company’s
ethic of close relations:

```
CREATE VIEW contractsales_view
AS SELECT o.CONTR_EXPIRY_DATE, o.SALE_INVOICE_NUM, c.CLIENT_NAME,
p.PROD_DESCR, MONTHS_BETWEEN(o.CONTR_EXPIRY_DATE,
o.CONTR_START_DATE) as "Current contract's length (in MONTHS)"
FROM CONTRACT_SALE o
JOIN CLIENT c USING(CLIENT_NUM)
JOIN PRODUCT p USING(PROD_NUM)
ORDER BY o.CONTR_EXPIRY_DATE ASC;
```

We can create two views to see all the current salesmen who are either travelling or
in-branch:

```
-- Travelling salesmen view --

CREATE OR REPLACE VIEW travsales_view
AS SELECT e.BRANCH_NUM, e.EMP_NAME, e.EMP_SURNAME, s.SLSMN_TRAVEL
FROM EMPLOYEE e INNER JOIN SALESMAN s USING (EMP_NUM)
WHERE s.SLSMN_TRAVEL = 'Y';

-- In-branch salesmen view --

CREATE OR REPLACE VIEW officesales_view
AS SELECT e.BRANCH_NUM, e.EMP_NAME, e.EMP_SURNAME, s.SLSMN_TRAVEL
FROM EMPLOYEE e INNER JOIN SALESMAN s USING (EMP_NUM)
WHERE s.SLSMN_TRAVEL = 'N';
```

We can also create a view to see which materials are currently stocked using a contract with
a supplier:

```
CREATE VIEW prodcontract_view
AS SELECT p.MAT_NUM, p.BRANCH_NUM, p.PROD_DESCR, s.VENDOR_NUM,
s.CONTR_AMOUNT, s.CONTR_START_DATE, s.CONTR_EXPIRY_DATE,
s.CONTR_DISCOUNT
FROM PRODUCT p
INNER JOIN SUPPLIER_CONTRACT s USING (CONTR_INVOICE_NUM);
```

Another view which can be created is to be able to see all of the branch managers in a flash:

```
CREATE VIEW managers_view
AS SELECT e.BRANCH_NUM, CONCAT(CONCAT(e.EMP_NAME, ' '),
e.EMP_SURNAME) as "Manager details", r.MAN_DATE_APPOINTED,
r.MAN_TOTAL_SALARY
FROM EMPLOYEE e
INNER JOIN REGIONAL_MANAGER r USING (EMP_NUM);
```

Yet another view would be to list all suppliers and the number of contracts each of them
holds:

```
CREATE VIEW suppliers_view
AS SELECT s.VEND_NAME, s.VEND_PHYS_ADDRESS,
s.VEND_TEL_NUM, s.VEND_PERF_RATING, c.BRANCH_NUM,
COUNT(c.contr_invoice_num) as "NUMBER OF CONTRACTS",
SUM(c.CONTR_AMOUNT) as "TOTAL CONTRACTS AMOUNT"
FROM SUPPLIER s JOIN SUPPLIER_CONTRACT c
USING(vendor_num) GROUP BY
s.VEND_NAME, s.VEND_PHYS_ADDRESS,
s.VEND_TEL_NUM, s.VEND_PERF_RATING,
c.BRANCH_NUM;
```

<a name="28"></a>
## 2. Queries
<a name="29"></a>
### 2.1 Ensuring company specifications

According to the analysis of the company that we completed in Phase 1, we conclude that
Dunder Mifflin requires the following in the database, and thus also include the SQL code to
implement these requirements:

* Access restriction (corporate can see and edit data of all branches, and employees
will get access to their respective branch’s view)

```
-- Create views for specific branches --
-- For this section, we use the same views as defined in Section 1.4, to see the employees
and sales for each individual branch --

-- Create user for each branch and headquarters with password --
CREATE USER corporate_usr IDENTIFIED BY Corporate11111;
CREATE USER scranton_usr IDENTIFIED BY Scranton1111;
CREATE USER akron_usr IDENTIFIED BY Akron111111111;
CREATE USER albany_usr IDENTIFIED BY Albany111111111111;
CREATE USER nashua_usr IDENTIFIED BY Nashua11111111111111;
CREATE USER rochester_usr IDENTIFIED BY Rochester11111;
CREATE USER utica_usr IDENTIFIED BY Utica11111111111;
CREATE USER syracuse_usr IDENTIFIED BY Syracuse1111;

-- Create synonyms for all these views so that they can be used to give access --
CREATE public synonym SCRANEMP for scranton_emp_view;
CREATE public synonym SCRANSALE for scranton_sales_view;
CREATE public synonym AKEMP for akron_emp_view;
CREATE public synonym AKSALE for akron_sales_view;
CREATE public synonym ALEMP for albany_emp_view;
CREATE public synonym ALSALE for albany_sales_view;
CREATE public synonym NASHEMP for nashua_emp_view;
CREATE public synonym NASHSALE for nashua_sales_view;
CREATE public synonym ROEMP for rochester_emp_view;
CREATE public synonym ROSALE for rochester_sales_view;
CREATE public synonym UTEMP for utica_emp_view;
CREATE public synonym UTSALE for utica_sales_view;
CREATE public synonym SYEMP for syracuse_emp_view;
CREATE public synonym SYSALE for syracuse_sales_view;

-- Assign corporate access to each branch’s data --
GRANT ALL ON SCRANEMP to corporate_usr;
GRANT ALL ON SCRANSALE to corporate_usr;
GRANT ALL ON AKEMP to corporate_usr;
GRANT ALL ON AKSALE to corporate_usr;
GRANT ALL ON ALEMP to corporate_usr;
GRANT ALL ON ALSALE to corporate_usr;
GRANT ALL ON NASHEMP to corporate_usr;
GRANT ALL ON NASHSALE to corporate_usr;
GRANT ALL ON ROEMP to corporate_usr;
GRANT ALL ON ROSALE to corporate_usr;
GRANT ALL ON UTEMP to corporate_usr;
GRANT ALL ON UTSALE to corporate_usr;
GRANT ALL ON SYEMP to corporate_usr;
GRANT ALL ON SYSALE to corporate_usr;

-- Assign branch user access to see the date from their branch--
GRANT SELECT ON SCRANEMP to scranton_usr;
GRANT SELECT ON SCRANSALE to scranton_usr;
GRANT SELECT ON AKEMP to akron_usr;
GRANT SELECT ON AKSALE to akron_usr;
GRANT SELECT ON ALEMP to albany_usr;
GRANT SELECT ON ALSALE to albany_usr;
GRANT SELECT ON NASHEMP to nashua_usr;
GRANT SELECT ON NASHSALE to nashua_usr;
GRANT SELECT ON ROEMP to rochester_usr;
GRANT SELECT ON ROSALE to rochester_usr;
GRANT SELECT ON UTEMP to utica_usr;
GRANT SELECT ON UTSALE to utica_usr;
GRANT SELECT ON SYEMP to syracuse_usr;
GRANT SELECT ON SYSALE to syracuse_usr;
```

* Tallying compliments and complaints per salesman in the database.

```
accept x number prompt "Enter the employee number of the person you wish to report:";
accept y number prompt "Has this employee received a compliment (1) or complaint (2)?";
declare
emp number := &x;
choice number := &y;
BEGIN
IF(choice = 1) THEN
UPDATE EMPLOYEE SET EMP_COMPLMNTS = EMP_COMPLMNTS + 1
WHERE EMP_NUM = emp;
ELSIF(choice = 2) THEN
UPDATE EMPLOYEE SET EMP_COMPLAINTS = EMP_COMPLAINTS + 1
WHERE EMP_NUM = emp;
END IF;
END;
```

* Allow clerks to enter data when a sale is made.

```
ALTER SESSION SET NLS_DATE_FORMAT = 'DD-MON-YYYY HH24:MI:SS';
SET SERVEROUTPUT ON;
accept mat number prompt "Please enter material number of item purchased:"
accept clnt number prompt "Please enter client number of purchase:"
accept emp number prompt "Please enter employee number who facilitated purchase:"
accept discount number prompt "Please enter total amount of discount granted (in
Rands):"
accept quant number prompt "Please enter total quantity of item purchased:"
accept purchtype number prompt "Please enter type of purchase made (1 for once-off sale
and 2 for contract sale):"
declare
mat number := &mat;
clnt number := &clnt;
emp number := &emp;
discount number := &discount;
quant number := &quant;
purchtype number := &purchtype;
sale_total number;
invoice number := INVOICE_SEQ.NEXTVAL;
branch number;
prodnum varchar(8);
quantleft number;
BEGIN
SELECT BRANCH_NUM INTO branch FROM EMPLOYEE WHERE
EMP_NUM=emp;
prodnum := CONCAT(TO_CHAR(branch),TO_CHAR(mat));
SELECT PROD_PRICE INTO sale_total FROM PRODUCT WHERE PROD_NUM
= prodnum;
SELECT PROD_QUANTITY_STOCKED INTO quantleft FROM PRODUCT
WHERE PROD_NUM = prodnum;
IF(quantleft-quant < 0)THEN
dbms_output.put_line('NOT ENOUGH STOCK LEFT!');
return;
END IF;
sale_total := sale_total * quant;
sale_total := sale_total - discount;
IF(purchtype=1) THEN
INSERT INTO SALE(SALE_INVOICE_NUM, PROD_NUM, CLIENT_NUM,
EMP_NUM, SALE_DISCOUNT, SALE_QUANTITY, SALE_TOTAL_DUE, SALE_TYPE)
VALUES (invoice, prodnum, clnt, emp, discount, quant, sale_total, 'O');
INSERT INTO ONCE_OFF_SALE(SALE_INVOICE_NUM, PROD_NUM,
CLIENT_NUM, EMP_NUM, SALE_DATE_TIME) VALUES(invoice, prodnum, clnt, emp,
CURRENT_DATE);
ELSIF(purchtype=2) THEN
INSERT INTO SALE(SALE_INVOICE_NUM, PROD_NUM, CLIENT_NUM,
EMP_NUM, SALE_DISCOUNT, SALE_QUANTITY, SALE_TOTAL_DUE, SALE_TYPE)
VALUES (invoice, prodnum, clnt, emp, discount, quant, sale_total, 'C');
INSERT INTO CONTRACT_SALE(SALE_INVOICE_NUM, PROD_NUM,
CLIENT_NUM, EMP_NUM, CONTR_START_DATE, CONTR_EXPIRY_DATE)
VALUES(invoice, prodnum, clnt, emp, SYSDATE, add_months(SYSDATE,12));
END IF;
END;
```

* Sale triggers a delivery man to be assigned to the sale based on hours worked and
the branch where the order was placed, as well as automation of delivery due dates:

```
-- Execute immediately after clerk entry query --

create or replace TRIGGER DELV_TRIG
AFTER INSERT ON SALE
REFERENCING OLD AS OLD NEW AS NEW
FOR EACH ROW
BEGIN
declare
address varchar2(100);
branch number;
travelled number;
delvman number;
BEGIN
SELECT CLIENT_PHYS_ADRRESS INTO address FROM ADMIN.CLIENT
WHERE CLIENT_NUM = :new.CLIENT_NUM;
SELECT BRANCH_NUM INTO branch FROM ADMIN.EMPLOYEE WHERE
EMP_NUM = :new.emp_num;
SELECT DELV_HRS_TRVLD INTO travelled FROM (SELECT
BRANCH_NUM,MIN(DELV_HRS_TRVLD) AS DELV_HRS_TRVLD FROM
DELIVERY_STAFF GROUP BY BRANCH_NUM) WHERE BRANCH_NUM=branch;
SELECT emp_num INTO delvman FROM DELIVERY_STAFF WHERE
DELV_HRS_TRVLD = travelled AND BRANCH_NUM=branch;
INSERT INTO
ADMIN.DELIVERIES_DUE(SALE_INVOICE_NUM,DEL_NUM,PROD_NUM,DEL_LOCATI
ON,DEL_DATE,EMP_NUM) values
(:new.SALE_INVOICE_NUM,DEL_SEQ.NEXTVAL,:new.PROD_NUM,address,SYSDATE(
)+7,delvman);
END;
END;
```

* Automate inventory deductions when a sale is made.

```
-- Execute immediately after clerk entry query --

create or replace TRIGGER PRODMIN_TRIG
AFTER INSERT ON SALE
REFERENCING OLD AS OLD NEW AS NEW
FOR EACH ROW
BEGIN
UPDATE ADMIN.PRODUCT SET prod_quantity_stocked =
prod_quantity_stocked-:new.SALE_QUANTITY WHERE PROD_NUM =
:new.PROD_NUM;
END;
```

* Determining if the manager bonus is necessary, and then adding it to his total salary.

```
accept x number prompt "Enter branch number:"
accept y number prompt "Was your branch under budget? (Yes = 1, No = 2)"
declare
branch number := &x;
man number;
choice number := &y;
BEGIN
SELECT EMP_NUM INTO man FROM REGIONAL_MANAGER WHERE
BRANCH_NUM = branch;
IF(choice = 1) THEN
UPDATE REGIONAL_MANAGER SET MAN_BONUS = MAN_TOTAL_SALARY *
0.15 WHERE EMP_NUM = man;
UPDATE REGIONAL_MANAGER SET MAN_TOTAL_SALARY =
MAN_TOTAL_SALARY + MAN_BONUS WHERE EMP_NUM = man;
ELSIF(choice = 2) THEN
UPDATE REGIONAL_MANAGER SET MAN_TOTAL_SALARY =
MAN_TOTAL_SALARY - MAN_BONUS WHERE EMP_NUM = man;
UPDATE REGIONAL_MANAGER SET MAN_BONUS = 0 WHERE EMP_NUM =
man;
END IF;
END;
```

* Generate reports based on the efficiency of sales per employee and branch.

```
-- See how all employees are selling --
SELECT EMP_NUM AS "Employee Number", EMP_NAME AS "Employee Name",
EMP_SURNAME AS "Employee surname", COUNT(SALE_INVOICE_NUM) AS "Total
sales made"
FROM SALE JOIN EMPLOYEE
USING (EMP_NUM)
GROUP BY EMP_NUM, EMP_SURNAME, EMP_NAME;

-- See how all branches are selling --
SELECT B.BRANCH_NUM, B.BRANCH_PHYS_ADRESS AS "Branch name",
COUNT(SL.SALE_INVOICE_NUM) AS "Total sales made"
FROM BRANCH B
FULL OUTER JOIN EMPLOYEE EM
ON (B.BRANCH_NUM = EM.BRANCH_NUM)
FULL OUTER JOIN SALE SL
ON(SL.EMP_NUM = EM.EMP_NUM)
GROUP BY B.BRANCH_NUM, B.BRANCH_PHYS_ADRESS
ORDER BY COUNT(SL.SALE_INVOICE_NUM) DESC;

-- Calculate average sales per branch --
SELECT B.BRANCH_NUM, B.BRANCH_PHYS_ADRESS AS "Branch name",
ROUND(AVG(SL.SALE_TOTAL_DUE)) AS "Average of sales"
FROM BRANCH B
FULL OUTER JOIN EMPLOYEE EM
ON (B.BRANCH_NUM = EM.BRANCH_NUM)
FULL OUTER JOIN SALE SL
ON(SL.EMP_NUM = EM.EMP_NUM)
GROUP BY B.BRANCH_NUM, B.BRANCH_PHYS_ADRESS
ORDER BY COUNT(SL.SALE_INVOICE_NUM) DESC;
```

* Update inventory when new stock is delivered:

```
SET SERVEROUTPUT ON;
accept a number prompt "Enter branch number:"
accept x number prompt "Enter material number of product delivered:"
accept z number prompt "Enter quantity of product ordered:"

declare
branch number := &a;
mat number := &x;
quantity number := &z;
exist number;
prodnum varchar(8) := CONCAT(TO_CHAR(branch),TO_CHAR(mat));

BEGIN
SELECT COUNT(PROD_NUM) INTO exist FROM PRODUCT WHERE
PROD_NUM=prodnum;
IF(exist=1)THEN
UPDATE PRODUCT SET PROD_QUANTITY_STOCKED =
(PROD_QUANTITY_STOCKED + quantity) WHERE PROD_NUM=prodnum;
ELSIF(exist=0)THEN
dbms_output.put_line('No product found matching description. If this is the first
time this product has been delivered, please make sure that a supplier contract has been
created when the order was placed.');
END IF;
END;
```

* Create a new supplier contract (note that Dunder Mifflin only buys products via
contract):

```
accept a number prompt "Enter the material number:"
accept b number prompt "Enter branch number where to deliver:"
accept c number prompt "Enter supplier invoice number received:"
accept d char prompt "Enter product description:"
accept e number prompt "Enter product bin number:"
37
accept f char prompt "This product has passed the quality check (True/False):"
accept g char prompt "Enter special certificates for this product (otherwise None):"
accept h char prompt "Enter product special instructions (otherwise None):"
accept i number prompt "Enter product reorder point:"
accept j number prompt "Enter minimum order quantity of product:"
accept k number prompt "Enter price of one unit of this product:"
accept l number prompt "Enter the vendor number of the supplier:"
accept m number prompt "Enter total charged for order:"
accept o number prompt "Enter the duration of the contract in MONTHS:"
accept p number prompt "Enter discount received on contract:"

declare
quantity number := 0;
mat number := &a;
branch number := &b;
invoice number := &c;
descrip varchar2(100) := '&d';
bin number := &e;
quality varchar2(100) := '&f';
cert varchar2(100) := '&g';
instruct varchar2(100) := '&h';
reorder number := &i;
minquant number := &j;
price number := &k;
vendnum number := &l;
charge number := &m;
nummonths number := &o;
discount number := &p;
existvend number;
prodnum varchar(8) := CONCAT(TO_CHAR(branch),TO_CHAR(mat));

BEGIN
SELECT count(vendor_num) into existvend FROM SUPPLIER WHERE
vendor_num = vendnum;
IF(existvend = 1)THEN
INSERT INTO PRODUCT(MAT_NUM, BRANCH_NUM, CONTR_INVOICE_NUM,
PROD_DESCR, PROD_BIN_NUM, PROD_QUANTITY_STOCKED,
PROD_QUALITY_CHECK, PROD_CERTIFICATES, PROD_SPECIAL_INSTR,
PROD_REORDER_POINT, PROD_MIN_ORDER_QUANT, PROD_PRICE, PROD_NUM)
VALUES(mat, branch, to_char(invoice), descrip, bin, quantity, quality, cert, instruct,
reorder, minquant, price, prodnum);
INSERT INTO SUPPLIER_CONTRACT(CONTR_INVOICE_NUM,
BRANCH_NUM, MAT_NUM, VENDOR_NUM, CONTR_AMOUNT,
CONTR_START_DATE, CONTR_EXPIRY_DATE, CONTR_DISCOUNT)
VALUES(invoice, branch, mat, vendnum, charge, SYSDATE,
add_months(SYSDATE,nummonths), discount);
ELSIF(existvend = 0)THEN
dbms_output.put_line('No supplier found in our database to start this contract with.
Please first create a new supplier record.');
END IF;
END;
```

* Create a new supplier:

```
-- Create new supplier (done by clerk when ordering) --
accept b char prompt "Enter vendor name:"
accept c char prompt "Enter physical address of vendor:"
accept d char prompt "Enter pay terms of the vendor:"
accept e char prompt "This vendor is accredited (True/False):"
accept f char prompt "Enter telephone number of vendor:"
accept g char prompt "Enter email address of vendor:"
accept h number prompt "Enter performance rating of vendor (Out of 10):"

declare
vendnum number := VEND_SEQ.NEXTVAL;
vendname varchar2(100) := '&b';
address varchar2(100) := '&c';
pay varchar2(1000) := '&d';
cred varchar2(6) := '&e';
tel varchar2(10) := '&f';
email varchar2(100) := '&g';
perf number := &h;

BEGIN
INSERT INTO SUPPLIER(VENDOR_NUM, VEND_NAME,
VEND_PHYS_ADDRESS, VEND_PAY_TERMS, VEND_ACCRED, VEND_TEL_NUM,
VEND_EMAIL, VEND_PERF_RATING, VEND_ANNUAL_SPENDING)
VALUES (vendnum, vendname, address, pay, cred, tel, email, perf, 0);
END;
```
<a name="30"></a>
## 2.2 Sequences used

The following sequences were used to populate columns that needed incrementation, such
as where primary keys are generated whenever a record is added:

```
-- Material number sequence --

CREATE SEQUENCE "MATNUM_SEQ" MINVALUE 1 MAXVALUE
9999999999999999999999999999 INCREMENT BY 1 START WITH 1 CACHE 20
NOORDER
NOCYCLE ;

CREATE OR REPLACE TRIGGER "MATNUM_TRG"
BEFORE INSERT ON PRODUCT
FOR EACH ROW
BEGIN
<<COLUMN_SEQUENCES>>
BEGIN
IF INSERTING AND :NEW.MAT_NUM IS NULL THEN
SELECT MATNUM_SEQ.NEXTVAL INTO :NEW.MAT_NUM FROM SYS.DUAL;
END IF ;
END COLUMN_SEQUENCES;
END ;
/
ALTER TRIGGER "MATNUM_TRG" ENABLE ;

-- Invoice number sequence --

CREATE SEQUENCE "INVOICE_SEQ" MINVALUE 1 MAXVALUE
9999999999999999999999999999 INCREMENT BY 1 START WITH 1 CACHE 20
NOORDER
NOCYCLE ;

CREATE OR REPLACE TRIGGER "INVOICE_TRG"
BEFORE INSERT ON SALE
FOR EACH ROW
BEGIN
<<COLUMN_SEQUENCES>>
BEGIN
IF INSERTING AND :NEW.SALE_INVOICE_NUM IS NULL THEN
SELECT INVOICE_SEQ.NEXTVAL INTO :NEW.SALE_INVOICE_NUM FROM
SYS.DUAL;
END IF ;
END COLUMN_SEQUENCES;
END ;
/
ALTER TRIGGER "INVOICE_TRG" ENABLE ;

-- Delivery number sequence --

CREATE SEQUENCE "DELNUM_SEQ" MINVALUE 1 MAXVALUE
9999999999999999999999999999 INCREMENT BY 1 START WITH 1 CACHE 20
NOORDER
NOCYCLE ;

CREATE OR REPLACE TRIGGER "DELNUM_TRG"
BEFORE INSERT ON DELIVERIES_DUE
FOR EACH ROW
BEGIN
<<COLUMN_SEQUENCES>>
BEGIN
IF INSERTING AND :NEW.DEL_NUM IS NULL THEN
SELECT DELNUM_SEQ.NEXTVAL INTO :NEW.DEL_NUM FROM SYS.DUAL;
END IF ;
END COLUMN_SEQUENCES;
END ;
/
ALTER TRIGGER "DELNUM_TRG" ENABLE ;
```
<a name="31"></a>
### 2.3 Extra functionality

Other desired inferences that the company want to make from the database, but which was
not requested for us in our commission, includes (with their respective SQL code):

* Identify top-selling salesman, by summing the total revenue they have made for
Dunder Mifflin (run each block separately):

```
-- Top-selling employees (Top 10) --

CREATE TABLE sale_temp AS SELECT EMP_NUM AS EMP_NUM,
SUM(SALE_TOTAL_DUE) AS SALE_TOTAL
FROM SALE
GROUP BY EMP_NUM;

SELECT EMPLOYEE.EMP_NUM, CONCAT(CONCAT(EMPLOYEE.EMP_NAME, ' '),
EMPLOYEE.EMP_SURNAME) AS "Employee details", sale_temp.SALE_TOTAL AS
"Total of sales made"
FROM EMPLOYEE
INNER JOIN sale_temp
ON EMPLOYEE.EMP_NUM = sale_temp.EMP_NUM
ORDER BY sale_temp.SALE_TOTAL DESC
FETCH NEXT 10 ROWS ONLY;

DROP TABLE sale_temp PURGE;
```

* Identify salesmen who are performing poorly, by counting the number of sales they
have made (run each block separately):

```
accept x number prompt 'Enter the number of sales where, below this number of sales
made, an employee is considered as selling poorly:'

CREATE TABLE sale_temp AS SELECT EMP_NUM AS
EMP_NUM,COUNT(SALE_TOTAL_DUE) AS SALE_NUMBER
FROM SALE
GROUP BY EMP_NUM
HAVING COUNT(SALE_TOTAL_DUE) < &x;

SELECT EMPLOYEE.EMP_NUM, CONCAT(CONCAT(EMPLOYEE.EMP_NAME, ' '),
EMPLOYEE.EMP_SURNAME) AS "Employee details", sale_temp.SALE_NUMBER AS
"Total number of sales made"
FROM EMPLOYEE
INNER JOIN sale_temp
ON EMPLOYEE.EMP_NUM = sale_temp.EMP_NUM;

DROP TABLE sale_temp PURGE;
```

* Flag salesmen with a large amount of complaints or compliments (more than 10).

```
-- Employees with troubling amount of complaints --
SELECT EMP_NUM, CONCAT(CONCAT(EMP_NAME, ' '), EMP_SURNAME) AS
"Employees with more than 10 complaints", EMP_COMPLAINTS FROM EMPLOYEE
WHERE EMP_COMPLAINTS >= 10;

-- Employees with good amount of compliments
SELECT EMP_NUM, CONCAT(CONCAT(EMP_NAME, ' '), EMP_SURNAME) AS
"Employees with more than 10 compliments", EMP_COMPLMNTS FROM EMPLOYEE
WHERE EMP_COMPLMNTS >= 10;
```

* A clerk can run this daily to check which products have reached reorder point.

```
SELECT MAT_NUM, BRANCH_NUM, PROD_DESCR, PROD_QUANTITY_STOCKED
AS "Product on hand", PROD_REORDER_POINT AS "Reorder point"
FROM PRODUCT
WHERE PROD_QUANTITY_STOCKED <= PROD_REORDER_POINT;
```

* Update annual spending for the supplier of choice:

```
accept z number prompt 'Which supplier to you wish to update the annual spending for:'

declare
supp number := &z;

BEGIN
UPDATE SUPPLIER SET VEND_ANNUAL_SPENDING = (SELECT
SUM(CONTR_AMOUNT) FROM SUPPLIER_CONTRACT GROUP BY VENDOR_NUM
HAVING VENDOR_NUM = supp)
WHERE VENDOR_NUM = supp;
END;
```

* A salesman might want to search for a specific type of product, but can only
remember some of its name. Thus employee can search the database using this
query:

```
accept find_product prompt 'Give any part of the name of your product:'

SELECT * FROM PRODUCT WHERE PROD_DESCR LIKE '%'||'&find_product'||'%';
```

* Allow delivery staff to check vehicles in and out:

```
SET SERVEROUTPUT ON;
SELECT VEC_PLATE AS "Vehicles Available" FROM DELV_VEHICLE WHERE
VEC_AVAIL = 'Y' AND VEC_BRANCH = &branch;
accept x number prompt"Enter your employee number:"
accept y char prompt"Are you taking out (O) or returning (R) a vehicle?"
accept z char prompt"Enter vehicle license plate number:"

declare
emp number := &x;
choice varchar2(1) := '&y';
license varchar2(6) := '&z';
validemp number;
branch number;

BEGIN
SELECT count(emp_num) INTO validemp FROM DELIVERY_STAFF WHERE
EMP_NUM = emp;
IF(validemp=1 AND UPPER(choice)='O')THEN
UPDATE DELV_VEHICLE SET VEC_AVAIL = 'N' WHERE
VEC_PLATE=UPPER(license);
UPDATE DELV_VEHICLE SET EMP_NUM = emp WHERE
VEC_PLATE=UPPER(license);
ELSIF(validemp=1 AND UPPER(choice)='R')THEN
UPDATE DELV_VEHICLE SET VEC_AVAIL = 'Y' WHERE
VEC_PLATE=UPPER(license);
UPDATE DELV_VEHICLE SET EMP_NUM = null WHERE
VEC_PLATE=UPPER(license);
ELSIF(validemp=0)THEN
dbms_output.put_line('Invalid employee number!');
END IF;
END;
```

* A quality assurance officer might want to be able to quickly pull up which products
still need to pass the test, or which products need special handling:

```
SELECT MAT_NUM, BRANCH_NUM, PROD_DESCR, PROD_QUALITY_CHECK,
PROD_SPECIAL_INSTR, PROD_QUANTITY_STOCKED
FROM PRODUCT WHERE PROD_QUALITY_CHECK = 'False' OR NOT
PROD_SPECIAL_INSTR = 'None';
```
