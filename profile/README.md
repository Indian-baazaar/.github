# 🛒 Indian Baazaar — Full-Stack E-Commerce Platform

Indian Baazaar is a modern, full-stack **multi-vendor E-Commerce platform** built for the Indian market with:

- ✅ Product buy/sell flow  
- ✅ Razorpay payment integration  
- ✅ Shiprocket shipping & tracking integration  
- ✅ Multi-role RBAC (SUPER_ADMIN, ADMIN, RETAILER, USER)  
- ✅ Scalable backend (Express + MongoDB)  
- ✅ Modern frontend (React + Vite)

---

## 📚 Table of Contents

1. [Overview](#-overview)  
2. [Tech Stack](#-tech-stack)  
3. [Core Features](#-core-features)  
4. [Architecture](#-architecture)  
5. [Environment Variables](#-environment-variables)  
6. [Setup & Installation](#-setup--installation)  
7. [Frontend Structure](#-frontend-structure)  
8. [Backend Structure](#-backend-structure)  
9. [Authentication & RBAC](#-authentication--rbac)  
10. [E-Commerce Flow](#-e-commerce-flow)  
11. [Razorpay Integration](#-razorpay-integration)  
12. [Shiprocket Integration](#-shiprocket-integration)  
13. [API Overview](#-api-overview)  
14. [Future Roadmap](#-future-roadmap)  
15. [Contributing](#-contributing)  
16. [License](#-license)

---

## 🔍 Overview

Indian Baazaar is a **production-ready E-Commerce system** where:

- Users can **browse, search, and buy products**.  
- Retailers can **register, manage warehouses, and sell products**.  
- Admins can **manage users, products, orders, and logistics**.  
- The system integrates with **Razorpay** for secure online payments and **Shiprocket** for automated shipping, pickup, and tracking.

---

## 🧰 Tech Stack

### 🖥 Frontend

- React + Vite  
- React Router  
- Context API / Redux (configurable)  
- TailwindCSS / MUI components  
- Axios / Fetch for API calls

### 🖧 Backend

- Node.js + Express  
- MongoDB + Mongoose  
- JWT for Authentication  
- Bcrypt for Password Hashing  
- Cookie + HTTP-only tokens (optional)  

### 💳 Payments & Shipping

- Razorpay (Order & Payment Capture)  
- Shiprocket (Warehouse, Shipment, Tracking)

### 🛠 DevOps (optional / in progress)

- Docker-ready folder structure  
- Environment-based config (`.env`)  
- Ready for deployment on AWS / Render / Railway

---

## ✨ Core Features

### 👥 User Features

- User Registration & Login (email / mobile)
- Profile & Address Management
- Browse Products (categories, filters, search)
- Add to Cart / Remove from Cart
- Wishlist / My List
- Place Order (COD / Online via Razorpay)
- View Order History & Tracking Status
- Notifications (Order placed, shipped, delivered, etc.)

### 🧑‍💼 Retailer / Seller Features

- Retailer Registration & KYC (basic fields)
- Create & Manage Warehouse (integrated with Shiprocket pickup address)
- Create & Manage Products:
  - Name, description, images, price, stock, variants
- View Orders for Their Products
- Update Order Status (Packed, Ready to Ship, Dispatched)

### 🛡 Admin Features

- Admin Dashboard
- Manage Users, Retailers, and Roles
- Approve / Reject Retailer Requests
- Manage Categories, Banners, Homepage Sliders
- Global Order Management
- Trigger/Verify Shiprocket Shipments
- View Payment Status (via Razorpay)
- Manage Blog/Content (optional module)

---

## 🏗 Architecture

Basic high-level architecture:

```text
+---------------------------+
|        Frontend           |
|  React + Vite (SPA)       |
|  - User App               |
|  - Admin / Retailer App   |
+-------------+-------------+
              |
              v
+---------------------------+
|         Backend           |
|   Node.js + Express       |
|                           |
|  Auth / User Service      |
|  Product Service          |
|  Cart & Order Service     |
|  Razorpay Service         |
|  Shiprocket Service       |
|  RBAC & Permission Layer  |
+-------------+-------------+
              |
              v
+---------------------------+
|         Database          |
|        MongoDB           |
+---------------------------+



## Frontend Structure

- Example frontend/src structure:

src/
├─ App.jsx
├─ main.jsx
├─ routes/
│  ├─ UserRoutes.jsx
│  ├─ AdminRoutes.jsx
│  └─ RetailerRoutes.jsx
├─ pages/
│  ├─ Home/
│  ├─ Product/
│  ├─ Cart/
│  ├─ Checkout/
│  ├─ Orders/
│  ├─ Login/
│  ├─ Signup/
│  ├─ AdminDashboard/
│  └─ RetailerDashboard/
├─ components/
│  ├─ Header/
│  ├─ Footer/
│  ├─ ProductCard/
│  ├─ CategorySlider/
│  ├─ Banner/
│  └─ OrderStatusBadge/
├─ context/
│  └─ AuthContext.jsx
├─ utils/
│  ├─ api.js
│  ├─ auth.js
│  └─ formatPrice.js
└─ styles/
   └─ index.css


## Backend Structure

- Example frontend/src structure:

backend/
├─ index.js
├─ config/
│  ├─ connectDb.js
│  ├─ env.js
│  └─ shiprocketToken.js
├─ middleware/
│  ├─ auth.middleware.js
│  ├─ role.middleware.js
│  └─ error.middleware.js
├─ models/
│  ├─ user.model.js
│  ├─ product.model.js
│  ├─ category.model.js
│  ├─ order.model.js
│  ├─ cart.model.js
│  ├─ address.model.js
│  ├─ retailer.model.js
│  └─ warehouse.model.js
├─ routes/
│  ├─ auth.route.js
│  ├─ user.route.js
│  ├─ product.route.js
│  ├─ cart.route.js
│  ├─ order.route.js
│  ├─ payment.route.js
│  └─ shiprocket.route.js
└─ controllers/
   ├─ auth.controller.js
   ├─ user.controller.js
   ├─ product.controller.js
   ├─ cart.controller.js
   ├─ order.controller.js
   ├─ payment.controller.js
   └─ shiprocket.controller.js
