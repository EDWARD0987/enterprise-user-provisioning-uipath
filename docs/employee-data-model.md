# Employee Data Model

## Purpose

This document defines the employee object used throughout the User Provisioning Automation.

The employee object represents the information received from the HR system before provisioning begins.


| Field      | Type   | Required | Description                      |
| ---------- | ------ | -------- | -------------------------------- |
| EmployeeID | String | Yes      | Unique employee identifier       |
| FirstName  | String | Yes      | Employee first name              |
| LastName   | String | Yes      | Employee last name               |
| Department | String | Yes      | Department assigned by HR        |
| Role       | String | Yes      | Job role used for access mapping |
| Manager    | String | Yes      | Reporting manager                |
| StartDate  | Date   | Yes      | Employee start date              |
| Location   | String | No       | Office location                  |
| License    | String | No       | Microsoft 365 license            |



