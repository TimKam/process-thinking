# Process Thinking
*Exercises for the [FutureLearn "Process Thinking" course](https://www.futurelearn.com/courses/business-process-management)*

This document provides solution examples for all exercises of the [FutureLearn "Process Thinking" course](https://www.futurelearn.com/courses/business-process-management), listed by lesson number (not all lessons contain exercises).


## 1.3: [Redesigning a business process – Ford Motor Company](https://www.futurelearn.com/courses/business-process-management/1/steps/104174/)

The goal of this exercise is to suggests process improvements for the *Ford* case study.

To fix the purchase & payment issue: Track the states of purchase orders, shipping receipts and invoices in a central relational database and have a computer system reporting the discrepancies. Establish troubleshooting processes for the most common issues that occur.
To lower production costs: Analyze all production steps and states and identify bottlenecks, unnecessary waiting times and unnecessary stock piles. Re-engineer the processes to be more efficient and lean.


## 1.5: [What is a process?](https://www.futurelearn.com/courses/business-process-management/1/steps/104176/)

The goal of this exercise is to identify processes based on a set of activities.

Based on the activities in the video, we can identify two processes.

### Customer arrival-to-cash

**Textual description**
One or multiple waiters carry out the following activities in sequential order:
- Greet and seat
- Bring menu
- Take order
- Serve meal
- Present bill
- Collect payment

**Diagram**

![Customer arrival to cash](restaurant_customer_arrival_to_cash.png)

To add more details, we can add **intermediate message events** (for example: *Payment request comes in*) and model the customer as a **collapsed pool**.

### Clean kitchen (or, in end-to-end style: Kitchen: dirty-to-clean)
This is not a well-structured process, so we need *adaptive case management* here.
When modeling the process in BPMN, we could use an ad-hoc subprocess:

![kitchen: dirty to clean](kitchen_dirty_to_clean.png)

Or we could model the process in [CMMN](http://www.omg.org/spec/CMMN/1.0/).

As you can see above, modeling this process as more than a simple check list of activities is over-engineering and produces rather ridiculous results.

## 1.6: [Our definition of a business process](https://www.futurelearn.com/courses/business-process-management/1/steps/104178/)

The goal of this exercise is to provide an example of *weak links* in processes.

An extreme example for weak links are customer support processes gone bad.
As a customer, I sometimes call a customer support number and wait around 10 minutes in a loop before getting access to a human who then just tells me to call a different customer support number to reach the department that can address my issue.
My personal high score was calling four different numbers before reaching a person who actually handled my complaint.

## 1.7: [Share a process](https://www.futurelearn.com/courses/business-process-management/1/steps/104177)

The goal of this exercise is to provide an example of a business process and to specify
* triggers,
* participants,
* IT systems,
* customer value.

A simple technical customer support process (email).

### Textual description

* A customer (collapsed pool) sends a support request (event).
* The CRM system (lane) responds with a generic 'Thank you for your request' email (task).
* A 1st level support engineer (lane) assesses the case (task).
* If they can handle the case themselves (data-based exclusive gateway), they resolve the issue and respond (task).
* Otherwise, they escalate the case to a specialist (task).
* Then, the specialist (lane) solves the case and responds (task).


### Diagram

![resolve technical issue](resolve_technical_issue_mail.png)

### Key facts

**Trigger**:

Request comes in

**Actors**:

* Customer
* 1st level support engineer
* 2nd level support engineer
* (CRM system)

**Customer**:

For example, a customer of a Internet service provider

**Value**:

* Resolves technical issue for the customer
* Enables Internet service provide to provide (more) value to the customer


## 1.8: [What would you do?](https://www.futurelearn.com/courses/business-process-management/1/steps/104179)

The goal of this exercise is to reflect on one's experiences as a service a product consumer from a BPM perspective.

Some airlines have poor processes when you miss connecting flights. Here's one example of a non-budget airline:

I missed a connecting flight (it was the airline's fault) and I needed to stay in an expensive but unappealing city over night.
The airline issued a food coupon and sent me to a hotel where I could stay for free.
However, the food coupon wasn't enough to get a decent meal at the airport.
At the hotel, I was told I needed to wait until dinner (several hours) before I could get free access to food or even beverages (water). I didn't have the means to pay for anything in this country (I didn't expect to leave the airport there), so I needed to wait some hours before I got access to drinking water.
The next morning, the cab that picked me up (they managed the timing) got stuck in a traffic jam. I was lucky to be able to catch the flight then.

The airline could improve the process :
- Issue a more generous food coupon.
- Offer free beverages (water) in the hotel.
- Book hotels closer to the airport to avoid problems with traffic jams.

The costs of the new process are higher on first glance, but lead to increased customer satisfaction and consequently less complaints and less churn.

## 1.10: [Process improvement](https://www.futurelearn.com/courses/business-process-management/1/steps/104181)

The goal of this exercise is to describe the strategic goal behind a set of process change options and to develop further process improvement suggestions.

* **Increase operational efficiency**
  Automate, re#sequence, standardize (although the latter is categorized as *Increase cost efficiency* in the video)

* **Improve customer experience**
  Build infrastructure

* **Increase cost efficiency**
  Outsource to customer, standardize, eliminate cooking, eliminate waiters

Further examples are:
* Increase operational efficiency and customer experience through allowing the customer to pre-order from home.
* Increase cost efficiency through a optimizing the variety of the menu based on a restricted set of ingredients (less waste).


## 1.12: [IT Help Desk Case Study](https://www.futurelearn.com/courses/business-process-management/1/steps/104184)

The goal of this exercise is to resolve the issues the case study presents through re-engineering the *IT help desk* process.

1. **Cases take too long**: There are 50 cases per day for five 1st level support workers. Let's assume they work eight hours a day. That means, a 1st level support worker uses on average 48 minutes per case. Consequently, we can assume that the cases are complex and need experience to solve. To speed the process up, we should hire less 1st level support workers and more 2nd level specialist. And to keep the customer from calling, we should send out regular automatic status updates.
2. **Status of cases is unclear**: Add the status `in progress by 2nd level support`, so the 1st level staff can see whether a ticket is waiting/stuck or about to be resolved.
3. **Requests with status `open` are actually already resolved**: Automate the solution confirmation. Every email with a proposed solution should contain a link button (a green button that says *Confirm the issue is resolved* or similar). When the user clicks the button, the case is automatically set to `resolved`. If a customer doesn't reply to a proposed solution for more than three weeks, the system sets the case status to `expired`.


## 1.14: [What else besides transparency?](https://www.futurelearn.com/courses/business-process-management/1/steps/104186/)

The goal of this exercise is to explain how the items in each tuple of process characteristics as explained in the video relate to each other.

The values are organized in pairs, because each pair represents two ends of a spectrum.
Typically, you must...
* ...sacrifice quality (cut costs) to increase efficiency.
* ...sacrifice compliance (e.g. follow a standardized procedure) to gain agility.
* ...sacrifice networking (making it harder for a customer to reach a specific person) to streamline communication structures (integration).


## 1.15: [Which values matter most?](https://www.futurelearn.com/courses/business-process-management/1/steps/104187)

The goal of this exercise is to explain why the process characteristics (values) as explained in the video matter.

From a theoretical business perspective, efficiency (that means: return on investment) is the top priority. All other attributes impose requirements you need to take into account to be able to optimize efficiency.

Practically, the attributes are equally important.
For example:
* On the long term, you (hopefully) can't run a business without being compliant.
* Your business might depend on top-notch knowledge workers, who will leave if you don't enable them to deliver high-quality work.
* Your customers will leave to a faster moving competitor if you are not agile enough.


## 1.18: [Identifying a process](https://www.futurelearn.com/courses/business-process-management/1/steps/104189/)

The goal of this exercise is to identify and evaluate a process from a customer's perspective.

Patient onboarding at a medical specialist practice (in Germany):
You typically have to provide your health insurance card AND fill out a paper-based form with your general personal data and some important health specifica.
Of course, the data provides value (i.e. prevents incorrect treatment).
However, it wasn't necessary (could be done more easily) if we had properly working electronic health records.
On the other hand, electronic health records have serious data security and privacy implications.


## 2.2: What is process identification?

The goal of the exercise is to describe and argue for a process identification approach.

First, map out the process landscape. If possible, all high-level processes and their relations.
Then, create a roadmap for process documentation. Where does it make sense to start? Typically, you want to start with "low hanging fruits" - processes that are clearly worth documenting, but not very complex. Then, you can apply your lessons learned when identifying complex core processes.


## 2.4: Scenario – The family business

The goal of this exercise is to identify and prioritize the core processes of the scenario.

The two core end-to-end processes are purchase-to-pay and order-to-cash.
In the information text, we learn there are new products in the market that support a order-to-cash process that is probably significantly more convenient during winter (I know, "significantly" is technically not a good term to use without having the actual data).
Accordingly, we should prioritize the order-to-cash process.
Drilling further down into the process and focussing on just a part of the process doesn't make sense. Home ordering with on premise delivery or vice versa won't help to increase orders.


## 2.6: Scenario – Student enrollment

The goal of this exercise is to identify the artifacts of the example process:

* Pre-enrollment form
* Online access account
* Course requirements
* Offer + terms and conditions
* Offer acceptance document
* Enrollment plan + majors and minor
* Timetable
* Database
*

## 2.9: Simple Process Modelling

**Scenario 1**

The following diagram depicts the *Order book* process (not the order-to-delivery process) from a customer's perspective:

![order book](order_book.png)

I kept the diagram rather simple.
One could add, for example:
* A collapsed pool that represents the online book store. However, modeling each request with messages/message flows would go too far.
* More deviations from the most common paths (invalid login, adjust payment details, etc.).


## 2.10: Introduction to qualitative analysis

The goal of this exercise is to describe the role of the issue register.

An issue register for a process (or a set of processes) is like a bug tracker for an IT system.
Once somebody identifies a problem (or an enhancement possibility), a ticket is created in the issue register.
The process owners are continuously managing the issues in the register and ensure important issues get resolved.

## 2.16: Reflecting on value-added analysis

The goal of this exercise is to identify any value-adding, business value-adding and non-value adding steps of an example process.

I only consider steps that are explicitly modeled:

* Set up online access: technical necessity -> non-value adding step
* Make offer: -> necessary for the university, not for the student -> business value adding step
* Accept offer and T&C: T&C are legal requirement -> business value adding step
* Plan enrollment: Allows student to decide which courses to take -> value adding step
* Enroll: the core activity -> value adding step
* Register for classes: let's assume this step provides the students with different options to manage their timetables in accordance with their individual plans -> value adding step

One can argue that "Set up online access" is actually a business value adding step. Technically, it's probably possible to have the student enroll without an online account, but this would be an organizational mess.


## 2.18: What are the key benefits?

The goal of this exercise is to identify two key benefits of business process analysis.

To put business process analysis into context with business process identification:
Business process identification allows you to explicitly document existing processes and to continue operations ceteris paribus, while business process analysis allows you to adjust your processes to operate better (benefit 1) and to operate in a changing environment (benefit 2).


## 3.3: When processes turn bad

The goal of the exercise is to describe one process turned bad, as well as one
process the helped the organization gain a competitive advantage.

A process turned bad is the Android update process.
On a typical linux system, you can update the operating system (or any other program) yourself as soon as a release is available somewhere. When Google launched Android, they put the hardware manufacturers between software provider and users and disempowered the users to take full control over their phones without bigger hassles. While this might make sense to ensure software updates support specific hardware, it's a disaster from a security perspective.

As an example for gaining a competitive advantage through process innovation,
we can have a look at the gaming company Valve and their distribution platform Steam.
Already in 2002, Valve discovered that most of their users had access
to high-speed (by then-standards) Internet.
Making the data-driven(!) decision to develop an Internet-based game distribution platform back
when online gaming was still only a thing for a couple of geeks enabled them to create a multi-billion,
market leading company that serves as a role model for both employee and customer empowerment.


## 3.5: Overview of redesign approaches

The goal of this exercise is to explain the difference between transformative
and transactional process redesign.
Transformative process redesign is obvious to customers,
while transactional redesign is often transparent to them.

An example for transformative process redesign is online groceries shopping.
As a grocery store chain, I can't simply implement small changes step-by-step.
Instead, I need to develop a whole new set of processes,
implement them and once the first pilot runs,
I need to rapidly re-engineer if I encounter unexpected problems.

Transactional process redesign should be a continuous effort in any organization.
You should empower every employee to trigger a change in a process
if they detect a problem or improvement potential.
Let's take a growing sales team's processes as an example for transactional
process redesign. When starting with a handful of people, you're often not able
to establish verticals, but with a growing team, you better allow team
members to develop expert knowledge, e.g. of specific industries.


## 3.6: Process automation: Let’s start the conversation

The goal of this exercise is to discuss process automation.

Some questions you often need to consider when automating (part of) a process:
* Is it about automating non-value adding tasks or automating the whole process? It's basically improving your employees lives versus removing their jobs.
* Do you want to employ a process execution engine, introduce off-the-shelf applications or custom software?
* Can you reduce the risk of failure through moving forward incrementally without stoping your operations?
* Can you get process participants to collaborate? For example, if you can promise that helping automate a dull set of tasks (copy & paste, email forwarding) of a process will not result in cuts but in more interesting work/quality improvements, more people will provide honest information. This also facilitates process awareness on the long term.


## 3.8: Scenario – Process automation

The goal of this exercise is to provide an example for successful process automation.

Document approval processes are often low hanging fruits to automate.
You can manage the whole process with an BPX system and automated grunt work like document archiving.
Moreover, you can improve the assignment of approval tasks:
Instead of the approval seeker writing emails to people who might or might not be available/eligible,
the BPX system can select a candidate based on a list of eligible employees
and their schedules/calendars and send out reminders if the approval takes too long.

## 3.9: When to apply process automation

The goal of this exercise is to provide an example of process automation causing disastrous results.

Automating biased, discriminative processes is disastrous, first of all from an ethical perspective.
Let's look at an application process.
In the past, biased HR employees filtered applications in a first manual screening and excluded applicants because of their names (which indicate ethnicity and gender) without being aware of their bias.
If we now let a system derive business rules from historical decision data, we facilitate the bias.
This hurts the discriminated applicants and our organization.
Cathy O'Neil wrote an interesting book about this fallacy:
"Weapons of Math Destruction".


## 3.12: The Internet of Things (IoTs) and BPME

The goal of this exercise is to discuss Business Process Management Everywhere (BPME).

BPME is an approach to manage the Internet of Things (IoT).
Many people who introduce the Internet of things use a smart fridge (to be clear: as a B2C product) as an example.
The fridge informs you when your food is about to expire and re-orders groceries when you run out of stock.
Although the first time I heard about such a fridge was in 2009,
we still seem to be far away from consumer adoption,
in contrast to smart watches, tablets, smart TVs, smart cars and so on.
A smart fridge that supports the aforementioned use case is simply a logistical nightmare and currently hardly practicable from a BPM perspective:
* Even in developed countries, home delivery of groceries is still not widely adopted.
* If I frequently need to re-stock all groceries that don't belong into the fridge, an auto-refilling fridge solves only half of the problem.
These issues become evident when looking at the IoT from a BPM perspective.
From this perspective, the value of a smart car that measures driving behavior and facilitates safe and environmental friendly driving is far greater.
BPME allows us to detect and implement the scenarios that matter out of all scenarios that are technically possible.
