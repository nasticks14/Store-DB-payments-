# Store-DB-payments-
CREATE TABLE products (
    store_id INTEGER NOT NULL,
    product_id INTEGER PRIMARY KEY AUTOINCREMENT,
    visible TINYINT NOT NULL DEFAULT 1,
    height INTEGER NULL,
    weight INTEGER NULL,
    currency VARCHAR(3) NULL,
    price DECIMAL(9, 3) NULL,
    product_name VARCHAR(50) NOT NULL,
    sold INTEGER NULL,
    image_url VARCHAR(255) NULL,
    notes VARCHAR(255) NULL,
    quality INTEGER NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
INSERT INTO products (store_id, visible, height, weight, currency, price, product_name, sold, image_url, notes, quality, created_at) VALUES 
(1, 1, 270, 700, 'UA', 45.000, 'Rice', 40, 'https://www.jabko/image/rice.jpg', 'Довгозерний сорт', 1, '2024-10-13 12:17:51'),
(1, 1, 310, 400, 'UA', 29.500, 'Apples', 220, 'https://www.jabko/image/apples.jpg', 'Золотий сорт', 1, '2024-10-13 12:17:51'),
(1, 1, 260, 200, 'UA', 14.000, 'Tomatoes', 180, 'https://www.jabko/image/tomatoes.jpg', 'Вирощено в теплиці', 1, '2024-10-13 12:17:51'),
(1, 1, 500, 1500, 'UA', 85.500, 'Potatoes', 350, 'https://www.jabko/image/potatoes.jpg', 'Свіжі картоплі', 1, '2024-10-13 12:17:51'),
(1, 1, 200, 300, 'UA', 22.000, 'Carrots', 120, 'https://www.jabko/image/carrots.jpg', 'Органічні моркви', 1, '2024-10-13 12:17:51'),
(1, 1, 400, 600, 'UA', 15.000, 'Cabbage', 80, 'https://www.jabko/image/cabbage.jpg', 'Вітамінний продукт', 1, '2024-10-13 12:17:51'),
(1, 1, 150, 450, 'UA', 10.500, 'Grapes', 200, 'https://www.jabko/image/grapes.jpg', 'Свіжі виногради', 1, '2024-10-13 12:17:51'),
(1, 1, 350, 700, 'UA', 28.900, 'Oranges', 150, 'https://www.jabko/image/oranges.jpg', 'Солодкі апельсини', 1, '2024-10-13 12:17:51');
