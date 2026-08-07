# Functional Requirements

- Import employee information
- Validate employee data
- Generate usernames
- Generate email addresses
- Create Active Directory accounts
- Assign security groups
- Provision Microsoft 365
- Send welcome email
- Log every action

# Non-functional Requirements

- Retry failed operations
- Log all errors
- Support future integrations



# System Requirements

## 1. Purpose

The purpose of this project is to automate employee user provisioning using UiPath.

The automation will process employee information received from an HR system and provision the required user accounts and access.

## 2. Functional Requirements

### FR-01: Employee Data Intake

The system shall read employee records from the HR input source.

For the initial version, the HR input source will be a CSV file.

### FR-02: Employee Validation

The system shall validate employee records before provisioning.

The system shall verify:

- EmployeeID is present
- EmployeeID is unique
- FirstName is present
- LastName is present
- Department is valid
- Role is valid
- Manager is present
- StartDate is present

Invalid records shall not proceed to provisioning.

### FR-03: Username Generation

The system shall generate a unique username based on the employee's name.

Example:

John Smith → jsmith

If the username already exists:

jsmith → jsmith1 → jsmith2

### FR-04: Email Generation

The system shall generate a corporate email address.

Example:

jsmith@company.com

### FR-05: Active Directory Provisioning

The system shall:

- Check whether the user already exists
- Create the user account
- Enable the account
- Assign the appropriate Organizational Unit
- Assign security groups

### FR-06: Microsoft 365 Provisioning

The system shall provision the appropriate Microsoft 365 license based on the employee's role.

### FR-07: Notifications

The system shall notify the appropriate parties when provisioning succeeds or fails.

### FR-08: Logging

The system shall record provisioning actions and outcomes.

### FR-09: Exception Handling

The system shall handle business and system exceptions.

System failures should be retried where appropriate.

## 3. Non-Functional Requirements

### Security

- Credentials shall not be stored in workflows.
- Sensitive credentials shall be stored using secure credential management.
- No real employee information shall be stored in the public repository.

### Reliability

- Failed system operations should be retried.
- Errors shall be logged.
- Failed records shall be identifiable.

### Maintainability

- Workflows should be modular.
- Configuration should be separated from business logic.
- Reusable workflows should be used where appropriate.

### Auditability

The system shall maintain a record of provisioning actions, including:

- Employee ID
- Action performed
- Timestamp
- Status
- Error information when applicable

## 4. Initial Scope

The first version of the project will focus on:

1. Reading employee data
2. Validating employee data
3. Generating usernames
4. Generating email addresses
5. Simulating/provisioning user accounts
6. Logging results

Additional enterprise integrations will be added incrementally.

## 5. Future Scope

Future versions may include:

- Microsoft Entra ID
- Microsoft 365
- ServiceNow
- VPN provisioning
- Employee offboarding
- Role changes
- Access reviews
- UiPath Orchestrator
