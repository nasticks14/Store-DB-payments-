# Store-DB-payments-
CREATE TABLE stores (
    store_code VARCHAR(50) PRIMARY KEY,
    store_name VARCHAR(255),
    store_url VARCHAR(255),
    store_country VARCHAR(100),
    phone VARCHAR(20),
    email VARCHAR(100),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE TABLE transactions (
    transaction_id SERIAL PRIMARY KEY,
    store_code VARCHAR(50),
    transaction_type VARCHAR(50),
    amount DECIMAL(10, 2),
    total DECIMAL(10, 2),
    tax DECIMAL(10, 2),
    error_code VARCHAR(50),
    ip_address VARCHAR(45),
    postal_code VARCHAR(20),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (store_code) REFERENCES stores(store_code)
);

CREATE TABLE customers (
    customer_id SERIAL PRIMARY KEY,
    store_code VARCHAR(50),
    customer_name VARCHAR(255),
    credit_card_num VARCHAR(20),
    credit_card_date DATE,
    credit_card_cvv VARCHAR(4),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (store_code) REFERENCES stores(store_code)
);

CREATE TABLE products (
    product_id SERIAL PRIMARY KEY,
    store_code VARCHAR(50),
    product_name VARCHAR(255),
    visible BOOLEAN,
    weight DECIMAL(10, 2),
    height DECIMAL(10, 2),
    sold INT,
    currency VARCHAR(10),
    payment_status VARCHAR(50),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (store_code) REFERENCES stores(store_code)
);

CREATE TABLE orders (
    order_id SERIAL PRIMARY KEY,
    store_code VARCHAR(50),
    order_date TIMESTAMP,
    shipping_cost DECIMAL(10, 2),
    price DECIMAL(10, 2),
    image_url VARCHAR(255),
    quantity INT,
    status VARCHAR(50),
    notes TEXT,
    billing_country VARCHAR(100),
    billing_city VARCHAR(100),
    state_province VARCHAR(100),
    country VARCHAR(100),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (store_code) REFERENCES stores(store_code)
);
