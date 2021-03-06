# Database
Dokumentation für unsere Datenbankenstruktur. Create Table Statements abgeleitet aus dem ER Diagramm https://github.com/Stonks2Moon/Geschaeftskundenbroker/blob/main/Documents/ER-Diagramm-Business-Broker.png.

## Create Table Statements
```sql
CREATE TABLE address(
    address_id INT(11) NOT NULL AUTO_INCREMENT,
    post_code VARCHAR(10) NOT NULL,
    city VARCHAR(255) NOT NULL,
    street VARCHAR(255) NOT NULL,
    house_number VARCHAR(10),
    PRIMARY KEY (address_id)
)

CREATE TABLE company(
    company_id VARCHAR(255) NOT NULL,
    company_code VARCHAR(255) NOT NULL,
    company_name VARCHAR(255) NOT NULL,
    address_id INT(11),
    PRIMARY KEY (company_id),
    FOREIGN KEY (address_id) REFERENCES address(address_id),
    CONSTRAINT unique_company_code UNIQUE (company_code)
)

CREATE TABLE bank_account(
    bank_account_id INT(11) NOT NULL AUTO_INCREMENT,
    company_id VARCHAR(255) NOT NULL,
    iban VARCHAR(255) NOT NULL,
    account_owner VARCHAR(255) NOT NULL,
    bank_name VARCHAR(255) NOT NULL,
    PRIMARY KEY (bank_account_id),
    FOREIGN KEY (company_id) REFERENCES company(company_id)
)

CREATE TABLE customer(
    customer_id VARCHAR(255) NOT NULL,
    first_name VARCHAR(255) NOT NULL,
    last_name VARCHAR(255) NOT NULL,
    email VARCHAR(255) NOT NULL,
    password_hash VARCHAR(255) NOT NULL,
    company_id VARCHAR(255) NOT NULL,
    PRIMARY KEY (customer_id),
    FOREIGN KEY (company_id) REFERENCES company(company_id)
)

CREATE TABLE depot(
    depot_id VARCHAR(255) NOT NULL,
    company_id VARCHAR(255) NOT NULL,
    PRIMARY KEY (depot_id),
    FOREIGN KEY (company_id) REFERENCES company(company_id)
)

CREATE TABLE share(
    share_id INT(11) NOT NULL AUTO_INCREMENT,
    isin VARCHAR(255) NOT NULL,
    wkn VARCHAR(255) NOT NULL,
    last_recorded_value DECIMAL NOT NULL DEFAULT 0,
    PRIMARY KEY (share_id)
)

CREATE TABLE depot_entry(
    entry_id INT(11) NOT NULL AUTO_INCREMENT,
    depot_id VARCHAR(255) NOT NULL,
    share_id INT(11) NOT NULL,
    amount DECIMAL NOT NULL,
    cost_value DECIMAL NOT NULL,
    created_at DATETIME DEFAULT NOW(),
    PRIMARY KEY (entry_id),
    FOREIGN KEY (depot_id) REFERENCES depot(depot_id),
    FOREIGN KEY (share_id) REFERENCES share(share_id)
)

CREATE TABLE share_order(
    order_id INT(11) AUTO_INCREMENT,
    depot_id VARCHAR(255) NOT NULL,
    share_id INT(11) NOT NULL,
    amount DECIMAL NOT NULL,
    order_type INT(11) NOT NULL,
    stop_buy DECIMAL,
    limit_1 DECIMAL,
    limit_2 DECIMAL,
    order_validity INT(11) NOT NULL,
    PRIMARY KEY (order_id),
    FOREIGN KEY (depot_id) REFERENCES depot(depot_id),
    FOREIGN KEY (share_id) REFERENCES share(share_id)
)

CREATE TABLE costumer_session(
    session_id VARCHAR(255) NOT NULL,
    customer_id VARCHAR(255) NOT NULL,
    expiration_date DATETIME NOT NULL,
    PRIMARY KEY (session_id),
    FOREIGN KEY (customer_id) REFERENCES customer(customer_id)
)

CREATE TABLE currency (
  iso_code varchar(3) NOT NULL DEFAULT '',
  currency_name varchar(200) NOT NULL,
  PRIMARY KEY (iso_code)
)

```
