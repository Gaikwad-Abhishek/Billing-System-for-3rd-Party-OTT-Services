# Software Requirements Specification (SRS) for Billing System - 3rd Party Services

## Table of Contents
1. [Introduction](#1-introduction)
   1.1. [Purpose](#11-purpose)
   1.2. [Scope](#12-scope)
   1.3. [Definitions, Acronyms, and Abbreviations](#13-definitions-acronyms-and-abbreviations)

2. [Overall Description](#2-overall-description)
   2.1. [Product Perspective](#21-product-perspective)
   2.2. [Product Functions](#22-product-functions)
   2.3. [User Characteristics](#23-user-characteristics)
   2.4. [Constraints](#24-constraints)
   2.5. [Assumptions and Dependencies](#25-assumptions-and-dependencies)

3. [Specific Requirements](#3-specific-requirements)

   3.1. [Functional Requirements](#31-functional-requirements)
      - 3.1.1. [Create Customer Account Hierarchy](#311-create-customer-account-hierarchy)
      - 3.1.2. [Add 3rd Party Services](#312-add-3rd-party-services)
      - 3.1.3. [Monthly Invoice Processing](#313-monthly-invoice-processing)
      - 3.1.4. [Invoice Generation](#314-invoice-generation)
      - 3.1.5. [User Payment Processing](#315-user-payment-processing)
      - 3.1.6. [Service Activation/Deactivation](#316-service-activationdeactivation)

4. [References](#4-references)

## 1. Introduction

### 1.1. Purpose
The purpose of the Billing System for 3rd Party Services within the Family Mobile environment is to efficiently manage billing and payment processing for Family Mobile accounts that include multiple mobile services along with third-party services such as Disney Hotstar and Netflix subscriptions. This system aims to streamline the billing process, enhance user experience, and ensure seamless service provision.

### 1.2. Scope
The scope of this project includes creating a customer account hierarchy, adding 3rd party services (Disney Hotstar, Netflix subscriptions), monthly invoice processing, and user payment processing.

#### 1.3. Definitions, Acronyms, and Abbreviations

| Term  | Definition                         |
|-------|------------------------------------|
| B2C   | Business-to-Consumer               |
| API   | Application Programming Interface  |
| OTT   | Over-the-Top                       |
| CLI   | Command Line Interface             |

## 2. Overall Description

### 2.1. Product Perspective
The Billing System - 3rd Party Services interacts with 3rd party service providers to manage OTT subscriptions and billing for Family Mobile customers.

### 2.2. Product Functions
- Create a customer account hierarchy.
- Add stubs of 3rd party services to billing accounts.
- Process monthly invoices from 3rd party providers.
- Generate invoices for users.
- Enable users to view and pay invoices.
- Manage service activation/deactivation based on invoice payment.

### 2.3. User Characteristics
The system caters to Family Mobile customers, including family accounts with multiple mobile services.

### 2.4. Constraints
- 3rd party API stubs need to be created for integration.
- Billing system microservices: Bill run service, Invoice Generation, Collection.

#### 2.5. Assumptions and Dependencies

| Item        | Description                                           |
|-------------|-------------------------------------------------------|
| Assumption  | The project assumes 3rd party API stubs will be available. |
| Dependency  | Requires Spring Boot (version 3.1.4), Java (version 17), Angular CLI (version 16.2.2), Node (version 18.13.0), npm (version 9.2.0), and MySQL database. |
## 3. Specific Requirements

### 3.1. Functional Requirements

#### 3.1.1. Create Customer Account Hierarchy
- Implement a system for managing family mobile accounts with 4 to 5 mobile services under one billing account.

#### 3.1.2. Add 3rd Party Services
- Integrate 3rd party services like Disney Hotstar and Netflix subscriptions to billing accounts.

#### 3.1.3. Monthly Invoice Processing
- Receive bulk B2C invoices from 3rd party providers.
- Process invoice data and generate invoices for users.
- Send invoices via email to users.

#### 3.1.4. Invoice Generation
- Develop a microservice for invoice generation.

#### 3.1.5. User Payment Processing
- Allow users to view invoices within the app.
- Implement a stub for payment system for users to pay their total bills.

#### 3.1.6. Service Activation/Deactivation
- Enable service providers to activate or deactivate 3rd party services based on invoice payment status.
- Handle various scenarios:

| Scenario   | Description                                                   |
|------------|---------------------------------------------------------------| 
| Scenario 1 | User makes an on-time payment.                                |
| Scenario 2 | User does not make payment - Services disrupted.              |
| Scenario 3 | User makes payment post disruption, and services are resumed. |
| Scenario 4 | Long payment due - Services terminated.                       |


### 4. References
- https://www.myvi.in/postpaid/family-postpaid-plans
- https://www.jio.com/selfcare/plans/mobility/postpaid-plans-home/
