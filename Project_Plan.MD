Mizan

A simple Point of Sale system for small retail stores.
Introduction
SimplePOS is an open-source POS system designed for small retail stores, offering flexibility for both on-premise (local) and cloud-based deployments. It can run as a web application on a local network (Windows or Linux) or be hosted on a cloud server for remote access. Version 0.1 is a minimal viable product (MVP) focusing on essential features: a sales interface, product management, and transaction logging. The system is developed using a vertical approach, building database, backend, and frontend in small, testable iterations for rapid progress.
Features (Version 0.1)

Sales Interface: Allows cashiers to select products, add them to a cart, calculate the total, and record sales.
Product Management: Enables adding, editing, and deleting products through an admin interface.
Transaction Logging: Stores transaction details (timestamp, total amount, and items) in a database.

Why These Functions?
The sales interface, product management, and transaction logging were chosen for version 0.1 because they form the core of any POS system. The sales interface enables cashiers to process transactions, the primary function of a POS, ensuring immediate usability for small stores. Product management provides a catalog of items to sell, essential for operations. Transaction logging ensures records are kept for accountability and future analysis, such as sales trends. This minimal scope allows developers to deliver a functional prototype quickly, aligning with the vertical development approach where each iteration includes database, backend, and frontend components.
Technology Stack
SimplePOS uses a modern web-based stack optimized for both on-premise and cloud deployments, compatible with Windows and Linux.

Frontend Technology: Vue.js - A lightweight JavaScript framework, chosen for its seamless integration with Laravel, ease of use, and component-based architecture, ideal for building the sales interface.
Backend Technology: Laravel - A PHP web framework with elegant syntax, Eloquent ORM for database management, and built-in tools like Laravel Breeze for rapid development.
Database: PostgreSQL - Robust and scalable, suitable for both development and production to handle concurrent transactions.
Frameworks and Languages:
JavaScript: For frontend interactivity and API calls (via Vue.js).
PHP: For backend logic and API development (via Laravel).
HTML/CSS: For frontend markup and styling.


Build Tool: Laravel Mix - Simplifies frontend asset compilation (e.g., JavaScript, CSS) for Vue.js integration.

Why Vue.js with Laravel?
Vue.js is the preferred frontend technology for SimplePOS due to its tight integration with Laravel (e.g., Laravel Mix and pre-configured Vue support), making it easy to set up and maintain. Its lightweight nature and beginner-friendly syntax reduce the learning curve, while its component-based structure suits the modular needs of a POS sales interface. Laravel’s robust backend features, such as Eloquent ORM and built-in API support, complement Vue.js, ensuring a cohesive development experience.
Deployment Considerations

On-Premise: Run the Laravel server locally on Windows (via XAMPP/WAMP) or Linux (via PHP and Apache/Nginx), accessible via browsers. Ideal for stores with limited internet or preferring local control.
Cloud-Based: Host on a cloud platform (e.g., Laravel Forge, AWS, Heroku) for remote access, supporting both operating systems via browser compatibility.
Desktop Option: For future versions, consider packaging the web app with Electron for a desktop application (cross-platform), though version 0.1 focuses on web deployment.

Getting Started
Prerequisites

PHP 8.x: For running Laravel.
Composer: For managing PHP dependencies.
Node.js and npm: For Vue.js and Laravel Mix.
Git: For cloning the repository.
PostgreSQL: For the database.
Operating Systems: Windows or Linux for local deployment.

Installation

Clone the Repository:
git clone https://github.com/yourusername/simplepos.git
cd simplepos


Set Up the Backend:

Install PHP dependencies:composer install


Copy the environment file and configure PostgreSQL:cp .env.example .env

Update .env with your PostgreSQL database credentials:DB_CONNECTION=pgsql
DB_HOST=127.0.0.1
DB_PORT=5432
DB_DATABASE=simplepos
DB_USERNAME=your_username
DB_PASSWORD=your_password


Generate an application key:php artisan key:generate


Run database migrations:php artisan migrate


Create a user for admin access (optional, via Laravel Breeze or custom routes):php artisan make:auth




Set Up the Frontend:

Install Node.js dependencies:npm install


Compile frontend assets with Laravel Mix:npm run dev




Run the Development Server:

Start the Laravel server:php artisan serve


The application will be accessible at http://localhost:8000.


Access the Application:

Frontend: http://localhost:8000
Admin interface: http://localhost:8000/admin (configure routes as needed).



Initial Pages and Functions
Sales Page

Functionality: Fetches products from the Laravel API, allows cashiers to select products and quantities, calculates the total, and submits transactions.
Implementation: Vue.js components for product display and cart management, using Axios or Fetch for API calls to Laravel endpoints.

Product Management

Functionality: Add, edit, and delete products (name, price) via a custom Laravel admin interface or Laravel’s built-in tools.
Implementation: Uses Laravel’s Eloquent ORM for database operations and custom routes for admin functionality.

Transaction Logging

Functionality: Records transactions with timestamp, total amount, and items sold.
Implementation: Uses Eloquent models (Product, Transaction, TransactionItem) and API endpoints to store transaction data.

Database Schema



Table
Fields
Description



Product
id, name, price
Stores product details.


Transaction
id, timestamp, total_amount
Logs sales transactions.


TransactionItem
id, transaction_id, product_id, qty
Links products to transactions with qty.


Development Roadmap for Version 0.1

 Set up Laravel project with models and routes for products and transactions.
 Define Eloquent models for Product, Transaction, and TransactionItem.
 Create API endpoints for listing products and creating transactions.
 Set up Vue.js project with components for the sales page.
 Implement product fetching and display in Vue.js.
 Implement cart functionality for selecting products and quantities.
 Implement sale submission to record transactions.
 Test the end-to-end sales flow.

Future Iterations

Add user authentication for cashiers (e.g., via Laravel Breeze).
Implement inventory tracking for stock management.
Develop sales reporting (e.g., daily/weekly reports).
Support additional payment methods (e.g., credit cards via Stripe).
Explore desktop app packaging with Electron for on-premise use.

Contributing
Contributions are welcome! Fork the repository, create a feature branch, and submit pull requests with your changes. Ensure code follows the project’s standards and includes tests where applicable.
License
This project is licensed under the MIT License.
