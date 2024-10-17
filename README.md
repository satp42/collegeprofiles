# **CollegeProfiles.com**

A web platform where high school students can purchase detailed college admission profiles from alumni, including essays, grades, extracurriculars, and awards. Alumni can submit their profiles and earn commissions on each sale. The platform features advanced search and filtering options to help students find the most relevant profiles.

---

## **Table of Contents**

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Architecture Overview](#architecture-overview)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Configuration](#configuration)
- [Running the Application](#running-the-application)
- [Project Structure](#project-structure)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

---

## **Features**

- **User Authentication**: Secure login and registration for students, alumni, and admin using Clerk.
- **Profile Management**: Alumni can create and edit profiles, subject to admin approval.
- **Advanced Search**: Students can filter profiles by various criteria like essays, extracurriculars, awards, and more.
- **Payment Processing**: Secure transactions using Stripe for purchasing profiles and handling alumni commissions.
- **Admin Dashboard**: Admin interface for approving profiles, monitoring transactions, and managing users.
- **Responsive UI**: A user-friendly interface built with React for seamless user experience.

---

## **Tech Stack**

- **Frontend**: React
- **Backend**: Go (Gin Framework)
- **Database**: Supabase (PostgreSQL)
- **Authentication**: Clerk
- **Payments**: Stripe
- **Deployment**: Docker, CI/CD with GitHub Actions
- **Others**: HTML5, CSS3, JavaScript (ES6+), RESTful APIs

---

## **Architecture Overview**

- **Frontend**: A React application that interacts with the backend API, handles authentication via Clerk, and integrates Stripe for payments.
- **Backend**: A RESTful API built with Go and the Gin framework, handling business logic, database interactions, and payment processing.
- **Database**: Supabase provides a hosted PostgreSQL database with real-time capabilities and storage.
- **Authentication**: Clerk manages user sessions and OAuth, providing secure authentication mechanisms.
- **Payments**: Stripe handles all payment processing, including student purchases and alumni payouts.

---

## **Getting Started**

### **Prerequisites**

Before you begin, ensure you have the following installed:

- **Go** (version 1.16 or higher)
- **Node.js** (version 14 or higher) and npm
- **Docker** (for containerization)
- **Git** (for version control)

### **Installation**

1. **Clone the Repository**

   ```bash
   git clone https://github.com/yourusername/alumni-profiles-marketplace.git
   cd alumni-profiles-marketplace
   ```
2. **Set Up the Backend**

   - Navigate to the backend directory:

     ```bash
     cd backend
     ```
   - Initialize Go modules:

     ```bash
     go mod download
     ```
3. **Set Up the Frontend**

   - Navigate to the frontend directory:

     ```bash
     cd ../frontend
     ```
   - Install npm dependencies:

     ```bash
     npm install
     ```

---

## **Configuration**

### **Environment Variables**

Create a `.env` file in both the `backend` and `frontend` directories with the following variables:

**Backend `.env` file:**

```env
# Supabase
SUPABASE_URL=your_supabase_url
SUPABASE_KEY=your_supabase_service_role_key

# Clerk
CLERK_SECRET_KEY=your_clerk_backend_api_key

# Stripe
STRIPE_SECRET_KEY=your_stripe_secret_key
STRIPE_WEBHOOK_SECRET=your_stripe_webhook_secret
```

**Frontend `.env` file:**

```env
# Clerk
REACT_APP_CLERK_PUBLISHABLE_KEY=your_clerk_frontend_api_key

# API Endpoint
REACT_APP_API_URL=http://localhost:8080/api
```

---

## **Running the Application**

### **Running the Backend**

1. **Navigate to the backend directory:**

   ```bash
   cd backend
   ```
2. **Run the application:**

   ```bash
   go run main.go
   ```

   The backend server will start on `http://localhost:8080`.

### **Running the Frontend**

1. **Navigate to the frontend directory:**

   ```bash
   cd ../frontend
   ```
2. **Start the React application:**

   ```bash
   npm start
   ```

   The frontend application will start on `http://localhost:3000`.

---

## **Project Structure**

```plaintext
alumni-profiles-marketplace/
├── backend/
│   ├── main.go
│   ├── go.mod
│   ├── controllers/
│   ├── models/
│   ├── routes/
│   ├── middlewares/
│   └── services/
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── App.js
│   │   └── index.js
│   ├── public/
│   ├── package.json
│   └── .env
├── docker-compose.yml
├── .gitignore
└── README.md
```

---

## **Contributing**

We welcome contributions! Please follow these steps:

1. Fork the repository.
2. Create a new feature branch: `git checkout -b feature/YourFeature`
3. Commit your changes: `git commit -m 'Add YourFeature'`
4. Push to the branch: `git push origin feature/YourFeature`
5. Open a pull request.

---

## **License**

This project is licensed under the **MIT License**. See the [LICENSE](LICENSE) file for details.
