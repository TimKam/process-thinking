# Process Thinking
*Exercises for the [FutureLearn "Process Thinking" course](https://www.futurelearn.com/courses/business-process-management)*


## 1.7: Share a process

A simple technical customer support process (email).


### Textual description

* A customer (collapsed pool) sends a support request (event).
* The CRM system (lane) responds with a generic 'Thank you for your request' email (task).
* A 1st level support engineer (lane) assesses the case (task).
* If they can handle the case themselves (data-based exclusive gateway), they resolve the issue and respond (task).
* Otherwise, they escalate the case to a specialist (task).
* Then, the specialist (lane) solves the case and responds (task).


### Diagram

![resolve technical issue](https://raw.githubusercontent.com/TimKam/process-thinking/master/Resolve%20technical%20issue%20(mail).png)

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


## 1.12: IT Help Desk Case Study

1. **Cases take too long**: There are 50 cases per day for five 1st level support workers. Let's assume they work eight hours a day. That means, a 1st level support worker uses on average 48 minutes per case. Consquently, we can assume that the cases are quite complex and need experience to solve. To speed the process up, we should hire less 1st level support workers and more 2nd level specialist. And to keep the customer from calling, we should send out regular autmatic status updates.
2. **Status of cases is unclear.**: Add the status `in progress by 2nd level support`, so the 1st level staff can see whether a ticket is waiting/stuck or about to be resolved.
3. **Requests with status `open` are actually already resolved**: Automate the solution confirmation. Every email with a proposed solution should contain a link button (a green button that says *Confirm the issue is resolved* or similar). When the user clicks the button, the case is automatically set to `resolved`. If a customer doesn't reply to a proposed solution for more than three weeks, the case is set to `expired`.
