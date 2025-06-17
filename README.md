# Company Database Design - Case Study 1

## Overview

This project involves designing a relational database schema for a large company to manage its employees, departments, projects, and dependents. The goal is to ensure all relevant data is structured efficiently for use within the organization.

## Requirements

### Employees
- Each employee has:
  - SSN (unique)
  - First Name and Last Name
  - Gender
  - Birth Date
- Each employee:
  - Works in **one** department
  - Can work on **multiple** projects
  - Has a recorded number of **working hours** per project
  - May have **dependents**
  - Has a **supervisor** (another employee)

### Departments
- Each department has:
  - A unique Department Number (DNUM)
  - Department Name (DName)
  - One or more **locations**
- Each department:
  - Is managed by **one employee**
  - Has a **manager's hiring date**
  - Can have multiple employees
  - Can manage multiple projects

### Projects
- Each project has:
  - A unique Project Number (PNumber)
  - Project Name (PName)
  - Location and City
- Each project:
  - Belongs to **one department**
  - Involves **multiple employees**

### Dependents
- Each dependent is linked to **one employee**
- Each dependent has:
  - A unique Dependent Name
  - Gender
  - Birth Date
- Dependent information is **not stored** if the employee leaves the company

## Relationships Summary
- **One-to-many**: Departments to Employees, Departments to Projects
- **Many-to-many**: Employees to Projects (with working hours)
- **One-to-one**: Department to Manager
- **Recursive**: Employee to Supervisor
- **Conditional**: Dependents exist only if the employee is active

## Notes
- The system ensures all data integrity rules, such as uniqueness and referential dependencies, are respected.
- The E-R diagram reflects these relationships visually.

