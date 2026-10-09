# Back2Me – Lost and Found Item Management System

Back2Me is a comprehensive web-based application designed for campus communities to manage lost and found items efficiently. It enables users to report lost items, register found items, and search through listings to reunite people with their belongings.

## 🌟 Features

- **Lost Item Management:** Report and track lost items with detailed descriptions.
- **Found Item Management:** Register found items to help others recover their belongings.
- **Advanced Search:** Fuzzy search across multiple item attributes, including name, category, brand, color, and location.
- **User Authentication:** Secure user login and profile management.
- **Real-time Updates:** Track item status and manage submissions.
- **Responsive Design:** Modern, mobile-friendly interface built with React and Bootstrap.

## 🛠️ Technology Stack

### Backend
- **Framework:** Spring Boot
- **Language:** Java
- **Database:** MySQL

### Frontend
- **Framework:** React 19.1.1
- **Language:** JavaScript
- **Styling:** CSS, TailwindCSS, Bootstrap
- **Build Tool:** Vite

## 📁 Project Structure

```text
Back2Me/
├── CampusManagement/               # Backend (Spring Boot)
│   └── lostAndFoundApplication/
│       ├── src/main/java/edu/infosys/lostAndFoundApplication/
│       │   ├── controller/         # REST controllers
│       │   ├── model/              # Entity classes
│       │   ├── repository/         # JPA repositories
│       │   ├── security/           # Security configuration
│       │   └── service/            # Business logic
│       └── src/main/resources/     # Configuration files
│
├── campus-front/                   # Frontend (React)
│   ├── public/                     # Static files
│   └── src/
│       ├── components/             # Reusable React components
│       ├── pages/                  # Page components
│       ├── services/               # API service calls
│       ├── App.jsx                 # Main App component
│       └── main.jsx                # Entry point
│
└── README.md
```

## 🚀 Getting Started

### Prerequisites

Make sure you have the following installed:

- Java JDK 17 or higher
- Node.js 16 or higher
- npm or Yarn
- MySQL
- Maven

## ⚙️ Backend Setup

### 1. Navigate to the Backend Directory

```bash
cd CampusManagement/lostAndFoundApplication
```

### 2. Configure the Database

Create a MySQL database:

```sql
CREATE DATABASE lost_found_db;
```

Open `src/main/resources/application.properties` and configure your database credentials:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/lost_found_db
spring.datasource.username=your_username
spring.datasource.password=your_password
```

Replace `your_username` and `your_password` with your local MySQL credentials.

### 3. Build and Run the Backend

Run the following commands:

```bash
mvn clean install
mvn spring-boot:run
```

The backend API will be available at:

**http://localhost:8080**

## 💻 Frontend Setup

### 1. Navigate to the Frontend Directory

Open a new terminal and run:

```bash
cd campus-front
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Start the Development Server

```bash
npm run dev
```

The frontend will be available at:

**http://localhost:3939**

> If Vite starts on a different port, use the URL displayed in your terminal.

## 📡 API Endpoints

### Lost Items

| Method | Endpoint | Description |
|---|---|---|
| POST | `/lost-found/lost-items` | Submit a new lost item |
| GET | `/lost-found/lost-items` | Retrieve all lost items |
| GET | `/lost-found/lost-items/{id}` | Retrieve a lost item by ID |
| DELETE | `/lost-found/lost-items/{id}` | Delete a lost item |
| GET | `/lost-found/lost-items/user/{username}` | Retrieve lost items by username |

### Found Items

| Method | Endpoint | Description |
|---|---|---|
| POST | `/lost-found/found-items` | Submit a new found item |
| GET | `/lost-found/found-items` | Retrieve all found items |
| GET | `/lost-found/found-items/{id}` | Retrieve a found item by ID |
| DELETE | `/lost-found/found-items/{id}` | Delete a found item |
| GET | `/lost-found/found-items/user/{username}` | Retrieve found items by username |

### Search

| Method | Endpoint | Description |
|---|---|---|
| GET | `/lost-found/api/search/lost?q={query}` | Search lost items |
| GET | `/lost-found/api/search/found?q={query}` | Search found items |

## 🔍 Fuzzy Search

Back2Me provides fuzzy search functionality to help users find relevant listings, even when search terms are incomplete or approximate.

Key capabilities include:

- Searches item names, categories, brands, colors, and locations.
- Assigns weighted scores to matching fields.
- Sorts search results by relevance.
- Supports partial queries to improve item discovery.

## 🔐 Security

Back2Me includes user authentication and profile management.

For a secure deployment:

- Keep database credentials out of version control.
- Store sensitive configuration in environment variables.
- Protect endpoints according to user roles and permissions.
- Validate and sanitize user input.
- Use HTTPS in production.

## 🔮 Future Enhancements

Potential improvements include:

- Image uploads for lost and found items.
- Email or in-app notifications when matching items are posted.
- Automatic matching between lost and found listings.
- Item claim requests and ownership verification.
- Administrative dashboard for campus moderators.
- Pagination and filtering for large collections.

## 📄 License

This project was developed as part of an educational initiative.

---

**Back2Me — Helping lost belongings find their way home.**
