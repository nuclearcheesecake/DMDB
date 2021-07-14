# DMDB (the *Dunder Mifflin* Database)

This entry won't be as serious or instructional as other entries may be - this is just a bit of fun that I had at university that I would like to share. My team and I worked on this during the first semester of our third year, and it was a blast trying to fit the world of NBC's *The Office* into a system that makes sense. The show gives a lot of attention to detail to the company, usually used as a foil against characters, but this allowed us to extract some important information about *Dunder Mifflin* as a whole.

Here follows the analysis that my team and I did on the Dunder Mifflin company and their need for a database.

# Phase 1 - Database initial study

<p align="center">
  <img width="825" src="https://github.com/nuclearcheesecake/wickusgoogledataanalyticscertificate2021/blob/main/Misc/course.png">
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
  <img width="825" src="https://github.com/nuclearcheesecake/wickusgoogledataanalyticscertificate2021/blob/main/Misc/course.png">
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
  <img width="825" src="https://github.com/nuclearcheesecake/wickusgoogledataanalyticscertificate2021/blob/main/Misc/course.png">
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
