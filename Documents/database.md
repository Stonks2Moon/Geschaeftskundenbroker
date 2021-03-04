# Database
Documentation for our database structure. Create Table statements taken from the ER Diagram.

## Create Table Statements
```sql
CREATE TABLE address(
    address_id INT(11) NOT NULL AUTO_INCREMENT,
    post_code VARCHAR(10) NOT NULL,
    city VARCHAR(255) NOT NULL,
    street VARCHAR(255) NOT NULL,
    house_number VARCHAR(255),
    Primary Key (address_id)
)

CREATE TABLE customer(
    customer_id VARCHAR(255) NOT NULL,
    first_name VARCHAR(255) NOT NULL,
    last_name VARCHAR(255) NOT NULL,
    email VARCHAR(255) NOT NULL,
    password_hash VARCHAR(255) NOT NULL,
    company_name VARCHAR(255) NOT NULL,
    address_id INT(11) NOT NULL,
    depot_id VARCHAR(255) NOT NULL,
    Primary Key (customer_id),
    Foreign Key (address_id) REFERENCES address(address_id),
    CONSTRAINT unique_depot UNIQUE (depot_id)
)

CREATE TABLE share(
    share_id int(11) NOT NULL AUTO_INCREMENT,
    isin VARCHAR(255) NOT NULL,
    WKN VARCHAR(255) NOT NULL,
    last_recorded_value DECIMAL NOT NULL DEFAULT 0,
    Primary Key (share_id)
)

CREATE TABLE depot_entry(
    depot_id VARCHAR(255) NOT NULL,
    share_id VARCHAR(255) NOT NULL,
    amount DECIMAL NOT NULL,
    cost_value DECIMAL NOT NULL 
)

```