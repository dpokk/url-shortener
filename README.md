# Linklytics - URL Shortener

A full-stack URL shortening platform built using React and Spring Boot to transform long links into clean, memorable URLs. It delivers rich, real-time analytics to track engagement, clicks, and overall performance.

## 🚀 Features

- **URL Shortening**: Generate short, memorable URLs instantly
- **Analytics Dashboard**: Track clicks, geographical data, and referral sources
- **Link Management**: Create, view, edit, and manage your shortened URLs
- **Real-time Analytics**: View click statistics with interactive charts


## 🛠️ Tech Stack

- **Spring Boot 3.4** - Java framework
- **Spring Security** - Authentication and authorization
- **Spring Data JPA** - Database ORM
- **PostgreSQL** - Primary database
- **Maven** - Dependency management
- **Frontend** - React.js with TailwindCSS
- **Material-UI** - Component library
- **Framer Motion** - Animation library
- **Chart.js** - Data visualization
- **Axios** - HTTP client
- **React Query** - Data fetching and caching


## 📋 Prerequisites

Before running this application, ensure you have:

- **Java Development Kit (JDK) 23** or higher
- **Node.js 16+** and npm
- **PostgreSQL** database server
- **Maven** (or use included Maven wrapper)
- **Git** (optional, for cloning)

## 🔧 Installation & Setup

### 1. Clone the Repository

```bash
git clone <your-repository-url>
cd url-shortener-project
```

### 2. Database Setup

Create a PostgreSQL database:

```sql
CREATE DATABASE urlshortener;
```

### 3. Backend Configuration

Navigate to the backend directory:

```bash
cd url-shortener-sb
```

Create environment variables (or set them in your system):

**Linux/Mac:**
```bash
export DATABASE_URL="jdbc:postgresql://localhost:5432/urlshortener"
export DATABASE_USERNAME="your_db_username"
export DATABASE_PASSWORD="your_db_password"
export DATABASE_DIALECT="org.hibernate.dialect.PostgreSQLDialect"
export JWT_SECRET="your-secret-key-at-least-256-bits-long"
export FRONTEND_URL="http://localhost:5173"
```

**Windows (PowerShell):**
```powershell
$env:DATABASE_URL="jdbc:postgresql://localhost:5432/urlshortener"
$env:DATABASE_USERNAME="your_db_username"
$env:DATABASE_PASSWORD="your_db_password"
$env:DATABASE_DIALECT="org.hibernate.dialect.PostgreSQLDialect"
$env:JWT_SECRET="your-secret-key-at-least-256-bits-long"
$env:FRONTEND_URL="http://localhost:5173"
```

**Windows (CMD):**
```cmd
set DATABASE_URL=jdbc:postgresql://localhost:5432/urlshortener
set DATABASE_USERNAME=your_db_username
set DATABASE_PASSWORD=your_db_password
set DATABASE_DIALECT=org.hibernate.dialect.PostgreSQLDialect
set JWT_SECRET=your-secret-key-at-least-256-bits-long
set FRONTEND_URL=http://localhost:5173
```

Install dependencies and run:

```bash
# Using Maven wrapper (recommended)
./mvnw spring-boot:run

# OR build and run JAR
./mvnw clean package
java -jar target/url-shortener-sb-0.0.1-SNAPSHOT.jar
```

The backend will start on `http://localhost:8080`

### 4. Frontend Configuration

Navigate to the frontend directory:

```bash
cd ../url-shortener-react
```

Create/update `.env` file:

```env
VITE_BACKEND_URL=http://localhost:8080
VITE_REACT_FRONT_END_URL=http://localhost:5173
VITE_REACT_SUBDOMAIN=http://url.localhost:5173
```

Install dependencies and run:

```bash
npm install
npm run dev
```

The frontend will start on `http://localhost:5173`

## 🎯 Usage

1. **Register an Account**: Create a new account from the registration page
2. **Login**: Sign in with your credentials
3. **Create Short URLs**: Navigate to the dashboard and create new shortened links
4. **View Analytics**: Track clicks and performance metrics for your links
5. **Manage Links**: Edit or delete your shortened URLs as needed

## 📁 Project Structure

```
url-shortener-project/
├── url-shortener-react/          # Frontend React application
│   ├── src/
│   │   ├── components/           # React components
│   │   ├── api/                  # API integration
│   │   ├── contextApi/           # Context API for state management
│   │   ├── hooks/                # Custom React hooks
│   │   └── utils/                # Utility functions
│   ├── public/                   # Static assets
│   └── package.json
│
└── url-shortener-sb/             # Backend Spring Boot application
    ├── src/
    │   ├── main/
    │   │   ├── java/com/url/shortener/
    │   │   │   ├── controller/   # REST controllers
    │   │   │   ├── models/       # Entity models
    │   │   │   ├── repository/   # JPA repositories
    │   │   │   ├── service/      # Business logic
    │   │   │   ├── security/     # Security configuration
    │   │   │   └── dtos/         # Data transfer objects
    │   │   └── resources/
    │   │       └── application.properties
    │   └── test/
    └── pom.xml
```

## 🔒 Security

- JWT-based authentication for secure API access
- Password encryption using Spring Security
- SQL injection protection via JPA/Hibernate

## 🐛 Troubleshooting

**Database Connection Issues:**
- Verify PostgreSQL is running
- Check database credentials in environment variables
- Ensure database exists

**Port Already in Use:**
- Backend: Change port in `application.properties` with `server.port=8081`

## 📝 API Endpoints

### Authentication
- `POST /auth/register` - Register new user
- `POST /auth/login` - User login

### URL Management
- `POST /api/shorten` - Create shortened URL
- `GET /api/urls` - Get user's URLs
- `GET /{shortCode}` - Redirect to original URL
- `DELETE /api/urls/{id}` - Delete URL

### Analytics
- `GET /api/analytics/{id}` - Get URL analytics

## 📄 License

This project is open source and available under the MIT License.

---

