# Instructions

- Clone or download this repository.
- Import the database `myapp.sql` or create a new one with these tables.
- `users` table with the following columns:
    - `id` (int)
    - `name` (string)
- `notes` table with the following columns:
    - `id` (int)
    - `user_id` (int)
    - `body` (text)
  
- Or run the following SQL commands:
```sql
CREATE TABLE `notes` (
  `id` int NOT NULL AUTO_INCREMENT,
  `body` text,
  `user_id` int DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `user_id` (`user_id`),
  CONSTRAINT `notes_ibfk_1` FOREIGN KEY (`user_id`) REFERENCES `users` (`id`) ON DELETE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=3 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;

CREATE TABLE `users` (
  `id` int NOT NULL AUTO_INCREMENT,
  `name` varchar(255) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=2 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;

INSERT INTO `notes` (`id`, `body`, `user_id`) VALUES
(1, 'ntoe 1', 1),
(2, 'note 2', 1);

INSERT INTO `users` (`id`, `name`) VALUES
(1, 'leemon');
```
- Give your database credentials in the `config` file.
- Run the server with 
```php
php -S localhost:8000
```