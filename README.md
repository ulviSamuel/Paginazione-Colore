# Color Pagination

![PHP](https://img.shields.io/badge/PHP-application-777BB4?style=flat&logo=php&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-database-4479A1?style=flat&logo=mysql&logoColor=white)
![Web application](https://img.shields.io/badge/Type-web%20application-2F80ED?style=flat)
![Year](https://img.shields.io/badge/Year-2024-6c757d?style=flat)

Paginazione Colore is a PHP web application that displays color records from a MySQL table with asynchronous pagination and configurable page sizes.

## Overview

The application reads `idColore` and `codiceColore` values from the `tColore` table and renders them as an HTML table. JavaScript requests subsequent or previous pages without reloading the document, and the interface can display 10, 25, or 50 records per page.

## Features

- Displays color identifiers and hexadecimal color codes in a tabular view.
- Renders each color code as a visual color cell.
- Navigates forward and backward through result pages with `XMLHttpRequest`.
- Hides pagination controls when no adjacent page exists.
- Supports page sizes of 10, 25, and 50 records.
- Shows the configured maximum page size and the currently displayed record range.

## Technology stack

- **PHP** for server-side rendering and database queries.
- **MySQL** accessed through PHP's `mysqli` extension.
- **HTML and CSS** for the interface.
- **Vanilla JavaScript** and `XMLHttpRequest` for asynchronous pagination.

## Project structure

```text
.
├── index.php
├── crea_tabella.php
├── verifica_esistenza_elementi.php
├── var_conn.php
└── css/
    └── index_style.css
```

- `index.php` is the browser entry point and contains the pagination controls and client-side requests.
- `crea_tabella.php` queries and renders a page of color records.
- `verifica_esistenza_elementi.php` checks whether a requested page contains records.
- `var_conn.php` opens the MySQL connection.
- `css/index_style.css` defines the table, controls, and page-size selector styles.

## Requirements

- PHP with the `mysqli` extension.
- A running MySQL server.
- A database containing a `tColore` table with the columns `idColore` and `codiceColore`.

The repository does not include the database schema or seed data. The connection file currently expects a local database configuration, so the database and its connection settings must be prepared for the local environment before running the application.

## Running locally

1. Prepare the required MySQL database and `tColore` table.
2. Review the connection settings in `var_conn.php` and configure them for the local database. Do not commit credentials.
3. From the repository root, start PHP's development server:

   ```bash
   php -S 127.0.0.1:8000
   ```

4. Open <http://127.0.0.1:8000/> in a browser.

The application uses `index.php` as the default document and sends requests to the PHP endpoints in the repository root.

## Testing and build status

No automated tests, dependency manifest, build configuration, or continuous-integration workflow is included in the repository. Validation therefore requires running the application against a configured MySQL database and exercising the pagination controls in a browser.

## License

This project is shared for educational and portfolio purposes. All rights reserved unless otherwise stated.
