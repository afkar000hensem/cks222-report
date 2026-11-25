# 1.1 SPEM 2.0 Modeling and Notion EPG — Maybank Secure2u
## Introduction
### Analysis of MAE Transaction with Secure2u
In a banking app system like MAE produced by Maybank, one of the core features required are money transfers between users or interbank transfers. Therefore, it is
important that a transaction requires heavy security to prevent data theft or the user's money being stolen. To resolve this issue, Maybank employs a system called
secure2u as a way to mend these problems, one of which is to bind every transaction onto one registered device set by the user, so that any unauthorized transactions
made on an unregistered device is immediately rejected and is notified to the user.

These features require a complex software system process, in which critical operational failures will lead to major loss of profits or mass stolen data theft by
unathorized third parties. One of the identified critical failures is when the system accidentally transfers RM 5,000.00 instead of RM 500.00 set by the user, in
which it will cause an issue where the user experiences a huge profit loss.

Therefore, a revised Software Process Model is needed to minimize the amount of errors that may occur within the development team, in which the processes, flow,
responsibilities and resources used are specified, defined and standardised so that every member of the project know their roles, responsibilities and guide on how
should the standard operating procedure be executed for each processes.

### Suggested Process Metamodel Standard
In this case, we will use the Objective Management Group (OMG) Software & Systems Process Engineering Metamodel (SPEM) 2.0 Version where every role, task and work
products are highly defined and specified. Each role, task, and work products are then used by the Method Content to define a step-by-step explanations that describes how specific development goals are achieved by which roles with which resources.

## Brief Theoretical Explanation
To start, let us define briefly what is Role, Task, Work Product in SPEM 2.0 Version. 

- Role\
A Role usually defines who (a person) is responsible for a specific set of functions, skills and competencies.
For example, someone is assigned as a Tester or a Software Architect.

- Task\
Work that is being performed by Roles, usually divided in sequential steps for Roles to follow accordingly.
One example is Tester performs test, where Performs Test is the Task.

- Work Product\
Documents or artefacts are either produced or consumed by Roles performing Tasks.
In other words, it is essentially the reports, codes, documents, diagrams and such being produced or used to complete a task or perform a task.

## Implementation of SPEM 2.0 using Notion EPG
We will create the SPEM 2.0 Model using a software called Notion where the model will be created in a relational Notion database.\
Active Notion share link: https://app.notion.com/p/SPEM-2-0-Method-Content-Library-Maybank-s-Online-Transaction-Features-with-Secure2u-42266e625e9180dc9ed9ce707ccffd93?source=copy_link

# 1.2 RACI Responsibility Matrix - Maybank Secure2u
| Engineering Deliverable | Business Analyst | Software Architect | Software Developer | Quality Assurance | DevSecOps Engineer |
| :---: | :---: | :---: | :---: | :---: | :---: |
| Software Requirements Specification | A/R | C | C | C | C |
| Architecture Design | C | A/R | C | I | C |
| Secure2u Integration Design | C | A | R | C | R |
| Implementation of Source Code | I | C | A/R | C | C |
| Quality and Security Report | I | C | C | A/R | R |
| Testing and Verification Report | C | I | C | A/R | C |
## Guide on How to Read the RACI Chart
- R stands for Responsible where specialized roles are assigned to complete the task of the deliverable\
- A stands for Accountable where a role owns the final outcome of a deliverable and has final decision-making\
- C stands for Consulted where input is needed before a task is finished or a decision is finalized\
- I stands for Informed where roles are kept updated on progress, decision, or outcomes
