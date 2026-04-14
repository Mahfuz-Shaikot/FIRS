🔫 FIRS — Firearm Inventory & Repository System










📌 Overview

FIRS is a role-based inventory and order management system built with Spring Boot and a vanilla JavaScript frontend.

It simulates a restricted-access catalog system with tiered permissions, dealer inventory control, and full order lifecycle management.

⚠️ This project is strictly for educational and portfolio demonstration purposes. No real-world weapon transactions occur.

⚙️ Core Features
🔐 Authentication & Authorization
Role-based access control:
Customer
Government / Military
Licensed Dealer
Administrator
Secure login & registration system
Tiered product visibility based on role permissions
🛒 Catalog & Shopping System
Dynamic product catalog
Filtering by category, brand, caliber, rating, and price
Cart system with persistent state (localStorage)
Simulated checkout flow with backend order creation
📦 Order Management
Order creation and history tracking
Status lifecycle: Processing → Shipped → Delivered
Admin-level order oversight
🏢 Dealer Dashboard
Inventory CRUD operations
CSV bulk import support
Stock monitoring with low-stock alerts
Inventory analytics (basic visualization support)
🎨 Frontend
Pure HTML, CSS, Vanilla JavaScript (ES6)
Responsive dark tactical UI
No external frontend frameworks
Fetch-based API integration
🧱 Tech Stack
Layer	Stack
Backend	Java 17, Spring Boot 3.3.2, Spring Data JPA, Hibernate
Frontend	HTML5, CSS3, JavaScript (ES6), Fetch API
Database	MySQL 8+
Build Tool	Maven
Tools	Postman, VS Code, MySQL Workbench / XAMPP
📁 Project Structure
firs-project/
├── src/main/java/com/firs/project/
│   ├── config/          # Data initialization
│   ├── controller/      # REST controllers
│   ├── model/           # JPA entities
│   ├── repository/      # Data access layer
│   ├── service/         # Business logic
│
├── src/main/resources/
│   ├── static/          # Frontend (HTML/CSS/JS)
│   └── application.properties
│
├── database/
│   └── firs_db.sql      # Schema + seed data
│
├── pom.xml
└── README.md
🚀 Getting Started
1️⃣ Prerequisites
Java 17+
Maven 3.6+
MySQL 8+ (or XAMPP)
2️⃣ Clone Repository
git clone https://github.com/your-username/firs-project.git
cd firs-project
3️⃣ Configure Database

Edit:

src/main/resources/application.properties
spring.datasource.url=jdbc:mysql://localhost:3306/firs_db?createDatabaseIfNotExist=true&useSSL=false&serverTimezone=UTC
spring.datasource.username=root
spring.datasource.password=your_password
4️⃣ Run Backend
mvn spring-boot:run

API runs at:

http://localhost:8080
5️⃣ Run Frontend

Serve /src/main/resources/static using Live Server or any HTTP server.

Ensure:

API_BASE = http://localhost:8080/api
🔑 Demo Accounts
Role	Email	Password	Access
Customer	customer@firs.com
	customer123	Limited catalog
Government	gov@firs.com
	gov123	Full catalog
Dealer	dealer@firs.com
	dealer123	Inventory control
Admin	admin@firs.com
	admin123	Full system access
📡 API Reference
Method	Endpoint	Description
POST	/api/register	Register user
POST	/api/login	Authenticate user
GET	/api/products	Fetch products
GET	/api/orders	Fetch orders
POST	/api/orders	Create order

Example request:

{
  "email": "customer@firs.com",
  "password": "customer123"
}
🐞 Known Issues / Notes
Ensure MySQL service is running before backend startup
Use CORS-enabled local server for frontend
Avoid direct file opening (file://) for frontend
Use @JsonIgnore for bidirectional JPA relationships to prevent recursion
🤝 Contributing
Fork repo
Create feature branch
Commit changes
Push branch
Open PR
📄 License

MIT License — free to use and modify.
