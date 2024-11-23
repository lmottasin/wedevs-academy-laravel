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
- Give your database credentials in the `config` file.
- Run the server with `php -S localhost:8000`.