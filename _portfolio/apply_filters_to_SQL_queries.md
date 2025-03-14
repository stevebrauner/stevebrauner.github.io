---
layout: single
title: "Apply Filters to SQL Queries"
excerpt: "Applying filters to SQL queries"
classes: wide
---

# Apply filters to SQL queries

## Project description

The scenario is:

> You are a security professional at a large organization. Part of your
> job is to investigate security issues to help keep the system secure.
> You recently discovered some potential security issues that involve
> login attempts and employee machines.
>
> Your task is to examine the organization's data in their employees and
> log_in_attempts tables. You'll need to use SQL filters to retrieve
> records from different datasets and investigate the potential security
> issues.

The filters will include WHERE, NOT, AND, OR, and LIKE.

## Retrieve after hours failed login attempts

You recently discovered a potential security incident that occurred
after business hours. To investigate this, you need to query the
log_in_attempts table and review after hours login activity. Use filters
in SQL to create a query that identifies all failed login attempts that
occurred after 18:00. (The time of the login attempt is found in the
login_time column. The success column contains a value of 0 when a login
attempt failed; you can use either a value of 0 or FALSE in your query
to identify failed login attempts.)

```
SELECT *
FROM log_in_attempts
WHERE login_time > '18:00' AND success = 0;
```

This will list all columns of log_in_attempts table where the login_time
is after '18:00' and failed.

## Retrieve login attempts on specific dates

A suspicious event occurred on 2022-05-09. To investigate this event,
you want to review all login attempts which occurred on this day and the
day before. Use filters in SQL to create a query that identifies all
login attempts that occurred on 2022-05-09 or 2022-05-08. (The date of
the login attempt is found in the login_date column.)

```
SELECT *
FROM log_in_attempts
WHERE login_date = '2022-05-09' OR login_date = '2022-05-08';
```

This will list all columns of log_in_attempts table where the login_date
was '2022-05-09' or '2022-05-08'.

## Retrieve login attempts outside of Mexico

There's been suspicious activity with login attempts, but the team has
determined that this activity didn\'t originate in Mexico. Now, you need
to investigate login attempts that occurred outside of Mexico. Use
filters in SQL to create a query that identifies all login attempts that
occurred outside of Mexico. (When referring to Mexico, the country
column contains values of both MEX and MEXICO, and you need to use the
LIKE keyword with % to make sure your query reflects this.)

```
SELECT *
FROM log_in_attempts
WHERE NOT country LIKE 'MEX%';
```

The lists all columns of log_in_attempts table where the country is not
like the filter 'MEX' with any other characters following.

## Retrieve employees in Marketing

Your team wants to perform security updates on specific employee
machines in the Marketing department. You're responsible for getting
information on these employee machines and will need to query the
employees table. Use filters in SQL to create a query that identifies
all employees in the Marketing department for all offices in the East
building.

(The department of the employee is found in the department column, which
contains values that include Marketing. The office is found in the
office column. Some examples of values in this column are East-170,
East-320, and North-434. You'll need to use the LIKE keyword with % to
filter for the East building.)

```
SELECT *
FROM employees
WHERE department = 'Marketing' AND office LIKE 'East%';
```

This lists all columns of employees table where the department is
'Marketing' and the office is like the filter 'East' followed by any
characters (all offices in the East building).

## Retrieve employees in Finance or Sales

Your team now needs to perform a different security update on machines
for employees in the Sales and Finance departments. Use filters in SQL
to create a query that identifies all employees in the Sales or Finance
departments. (The department of the employee is found in the department
column, which contains values that include Sales and Finance.)

```
SELECT *
FROM employees
WHERE department = 'Sales' OR department = 'Finance';
```

This lists all columns of the employees table where the department is
'Sales' or 'Finance'.

## Retrieve all employees not in IT

Your team needs to make one more update to employee machines. The
employees who are in the Information Technology department already had
this update, but employees in all other departments need it. Use filters
in SQL to create a query which identifies all employees not in the IT
department. (The department of the employee is found in the department
column, which contains values that include Information Technology.)

```
SELECT *
FROM employees
WHERE NOT department = 'Information Technology';
```

This lists all columns of the employees table where the department is
not 'Information Technology'.

## Summary

SQL queries are powerful ways to get specific types of data from the
table. SELECT and FROM commands are always present. To filter use WHERE,
NOT, AND, OR, LIKE to get only the data of interest.
