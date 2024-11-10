
# Project Analysis

## Project Objective:
This project aims to develop an information system for managing warehouse data and rental processes. The system allows warehouse owners and agents to carry out warehouse rental and management operations, while enabling administrators to create user accounts.

## Project Scope:
- The system involves three main user roles: Administrator, Warehouse Owner, and Warehouse Agent.
- Users have different levels of access based on their roles.
- The system provides users with notifications and detailed reports.

## Functional Requirements

### 1. User Operations

#### Administrator Functions:
- Create warehouse owner and agent accounts.
- Edit existing user profiles.
- Provide performance evaluations by rating warehouse agents.

#### Warehouse Owner Functions:
- Add new warehouses with details such as warehouse size, climate conditions, warehouse type, and category.
- Rent out warehouses by selecting warehouse agents.
- Access reports about the warehouses they own (including date, status, address, and type of warehouse).
- View contract details and manage rental information.

#### Warehouse Agent Functions:
- Access information about available warehouses for rent.
- View rental history with details about past rentals.
- View information about active rental contracts.

### 2. System Notifications
- A notification is sent to the warehouse agent when a new rental request is made.
- A notification is sent to the warehouse owner when a warehouse is rented.
- A notification is sent to both the owner and warehouse agent when a contract is nearing its expiration.

## Tables Description

### 1. Users
Contains all users in the system (administrator, warehouse owner, warehouse agent).

- **user_id**  Unique identifier for the user.
- **username**  Username for login.
- **password**  Password for login.
- **email**  User's email address.
- **role**  User's role (admin, owner, agent).
- **created_at**  Date when the user account was created.

### 2. Warehouses
Contains warehouse information and basic attributes.

- **warehouse_id**  Warehouse identifier.
- **owner_id**  User ID of the warehouse owner.
- **location**  Address of the warehouse.
- **dimensions**  Dimensions of the warehouse (e.g., m²).
- **climate_conditions**  Climate conditions (cold, humid, etc.).
- **warehouse_type**  Type of the warehouse (e.g., food warehouse).
- **category**  Category of the warehouse (private, public, etc.).
- **status**  Status of the warehouse (available, rented, under maintenance).
- **created_at**  Date when the warehouse was added.

### 3. Warehouse_Agents
Establishes a relationship between warehouses and warehouse agents, allowing multiple agents to work with a warehouse.

- **warehouse_agent_id**  Record identifier.
- **warehouse_id**  Warehouse ID.
- **agent_id**  Agent ID.
- **assigned_at**  Date when the agent was assigned to the warehouse.

### 4. RentalContracts
Contains warehouse rental contracts and related information.

- **contract_id**  Contract identifier.
- **warehouse_id**  Rented warehouse ID.
- **agent_id**  Warehouse agent ID.
- **start_date**  Rental start date.
- **end_date**  Rental end date.
- **rental_price**  Rental price.
- **status**  Contract status (active, expired).
- **created_at**  Date when the contract was created.

### 5. Ratings
Holds performance ratings for warehouse agents.

- **rating_id**  Rating identifier.
- **agent_id**  User ID of the rated agent.
- **rating**  Rating score (between 1 and 5).
- **review**  Review description.
- **created_at**  Date when the rating was given.

### 6. Notifications
Contains user-specific notifications.

- **notification_id**  Notification identifier.
- **user_id**  User receiving the notification.
- **message**  Notification message.
- **type**  Notification type (rental request, contract expiring, etc.).
- **status**  Notification status (unread, read).
- **created_at**  Date when the notification was created.

## Note
These definitions or ideas can be changed over the time by needs so in the next weeks we could change some.
