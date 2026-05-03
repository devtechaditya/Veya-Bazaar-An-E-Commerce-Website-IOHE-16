# 🛍️ Veya Bazaar
### *Your Modern Marketplace — Shop Smart, Shop Seamlessly.*

<p align="center">
  <img src="https://img.shields.io/badge/React.js-20232A?style=for-the-badge&logo=react&logoColor=61DAFB" />
  <img src="https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white" />
  <img src="https://img.shields.io/badge/Django-092E20?style=for-the-badge&logo=django&logoColor=white" />
  <img src="https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white" />
  <img src="https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Status-Active-brightgreen?style=flat-square" />
  <img src="https://img.shields.io/badge/Academic-Final%20Year%20Project-blue?style=flat-square" />
  <img src="https://img.shields.io/badge/University-Chitkara%20University-orange?style=flat-square" />
  <img src="https://img.shields.io/badge/Copyright-Registered-red?style=flat-square" />
</p>

---

## 📌 Introduction / Overview

**Veya Bazaar** is a full-stack, modern e-commerce web application designed to deliver a smooth and intuitive online shopping experience. Built with a powerful combination of **React.js** on the frontend and **Django REST Framework** on the backend, Veya Bazaar bridges the gap between elegant UI design and robust server-side performance.

The platform enables users to browse products across multiple categories, manage their shopping cart, place orders, and track purchases — all within a fast, responsive interface optimized for both desktop and mobile devices. On the administrative side, sellers and admins can manage product listings, inventory, and orders through a clean, purpose-built dashboard.

Veya Bazaar was conceived, designed, and developed as a **Final Year Project** for the subject **IOHE-16** at **Chitkara University, Rajpura**, representing a culmination of the team's academic learning in software engineering, full-stack web development, and system design.

> 💡 *"Veya" — inspired by the concept of exchange and value — reflects our mission to build a trustworthy digital marketplace for everyone.*

---

## 🚀 Features

### 🧑‍💻 User-Facing Features
- **User Authentication** — Secure registration, login, and JWT-based session management.
- **Product Catalog** — Browse products with rich details including images, descriptions, pricing, and ratings.
- **Advanced Search & Filters** — Search by keyword, filter by category, price range, and availability.
- **Shopping Cart** — Add, update, and remove items from a persistent cart with real-time total calculation.
- **Order Management** — Place orders, view order history, and track current order status.
- **Product Reviews & Ratings** — Authenticated users can leave reviews and star ratings on purchased items.
- **Wishlist** — Save products for later with a personal wishlist feature.
- **Responsive Design** — Fully optimized UI that works seamlessly on mobile, tablet, and desktop screens.

### 🛠️ Admin / Seller Features
- **Admin Dashboard** — Overview of total sales, active users, product count, and recent orders.
- **Product Management** — Add, edit, and delete product listings with image uploads.
- **Order Processing** — Update order statuses (Pending → Shipped → Delivered) directly from the panel.
- **User Management** — View registered users and manage access permissions.
- **Inventory Tracking** — Monitor stock levels and receive low-stock alerts.

### ⚙️ Technical Features
- **RESTful API** — Clean, well-documented REST API built with Django REST Framework.
- **JWT Authentication** — Stateless, token-based authentication for secure API communication.
- **Pagination & Lazy Loading** — Efficient data loading to handle large product catalogs gracefully.
- **CORS Support** — Properly configured cross-origin resource sharing between frontend and backend.
- **Environment-based Configuration** — Separate settings for development and production environments.

---

## 🛠️ Tech Stack

### 🌐 Frontend
| Technology | Purpose |
|---|---|
| **React.js** | Component-based UI library for building the SPA |
| **Tailwind CSS** | Utility-first CSS framework for rapid, responsive styling |
| **React Router DOM** | Client-side routing and navigation |
| **Axios** | HTTP client for communicating with the Django REST API |
| **React Context API** | Global state management for cart, auth, and user data |

### ⚙️ Backend
| Technology | Purpose |
|---|---|
| **Django** | High-level Python web framework for backend logic |
| **Django REST Framework** | Toolkit for building clean, scalable REST APIs |
| **SimpleJWT** | JSON Web Token authentication for Django |
| **Pillow** | Image handling for product photo uploads |
| **django-cors-headers** | CORS management for frontend-backend communication |

### 🗄️ Database & Infrastructure
| Technology | Purpose |
|---|---|
| **PostgreSQL** | Relational database for persistent, structured data storage |
| **psycopg2** | PostgreSQL adapter for Python/Django |

### 🧰 Developer Tools
| Tool | Purpose |
|---|---|
| **Git & GitHub** | Version control and collaborative development |
| **Postman** | API testing and documentation |
| **VS Code** | Primary code editor |
| **npm / pip** | Package managers for frontend and backend respectively |

---

## 🧩 System Architecture

Veya Bazaar follows a **decoupled client-server architecture**, where the frontend and backend operate as independent services that communicate via a well-defined REST API.

```
┌─────────────────────────────────────────────────────────┐
│                     CLIENT LAYER                        │
│   React.js (SPA) + Tailwind CSS + React Router DOM      │
│   Runs in the user's browser on Port 5173 (Vite/CRA)   │
└─────────────────────┬───────────────────────────────────┘
                      │  HTTP Requests (JSON / JWT Auth)
                      │  via Axios
                      ▼
┌─────────────────────────────────────────────────────────┐
│                     API GATEWAY                         │
│         Django REST Framework (Port 8000)               │
│   ┌─────────────┐  ┌──────────────┐  ┌──────────────┐  │
│   │  Auth API   │  │ Products API │  │  Orders API  │  │
│   │ /api/auth/  │  │ /api/products│  │ /api/orders/ │  │
│   └─────────────┘  └──────────────┘  └──────────────┘  │
└─────────────────────┬───────────────────────────────────┘
                      │  Django ORM Queries
                      ▼
┌─────────────────────────────────────────────────────────┐
│                   DATA LAYER                            │
│            PostgreSQL Database                          │
│   [Users] [Products] [Orders] [Reviews] [Cart Items]   │
└─────────────────────────────────────────────────────────┘
```

**Flow Summary:**
1. The React.js frontend sends HTTP requests to the Django backend via **Axios**.
2. Django REST Framework processes the request, applies business logic, and queries **PostgreSQL** through Django's ORM.
3. Data is serialized into **JSON** and returned to the React frontend, which updates the UI reactively.
4. **JWT tokens** are issued on login and sent with every protected request in the `Authorization` header.

---

## 📂 Folder Structure

```
veya-bazaar/
│
├── 📁 frontend/                   # React.js Application
│   ├── public/
│   │   └── index.html
│   ├── src/
│   │   ├── 📁 assets/             # Images, icons, and static files
│   │   ├── 📁 components/         # Reusable UI components
│   │   │   ├── Navbar.jsx
│   │   │   ├── Footer.jsx
│   │   │   ├── ProductCard.jsx
│   │   │   └── CartItem.jsx
│   │   ├── 📁 pages/              # Route-level page components
│   │   │   ├── HomePage.jsx
│   │   │   ├── ProductPage.jsx
│   │   │   ├── CartPage.jsx
│   │   │   ├── CheckoutPage.jsx
│   │   │   ├── LoginPage.jsx
│   │   │   └── AdminDashboard.jsx
│   │   ├── 📁 context/            # Global state (Auth, Cart)
│   │   │   ├── AuthContext.jsx
│   │   │   └── CartContext.jsx
│   │   ├── 📁 services/           # Axios API call functions
│   │   │   └── api.js
│   │   ├── App.jsx
│   │   └── main.jsx
│   ├── tailwind.config.js
│   └── package.json
│
├── 📁 backend/                    # Django Application
│   ├── 📁 veya_bazaar/            # Django project settings
│   │   ├── settings.py
│   │   ├── urls.py
│   │   └── wsgi.py
│   ├── 📁 users/                  # User auth app
│   │   ├── models.py
│   │   ├── serializers.py
│   │   ├── views.py
│   │   └── urls.py
│   ├── 📁 products/               # Products app
│   │   ├── models.py
│   │   ├── serializers.py
│   │   ├── views.py
│   │   └── urls.py
│   ├── 📁 orders/                 # Orders app
│   │   ├── models.py
│   │   ├── serializers.py
│   │   ├── views.py
│   │   └── urls.py
│   ├── 📁 media/                  # Uploaded product images
│   ├── manage.py
│   └── requirements.txt
│
├── .gitignore
├── README.md
└── LICENSE
```

---

## ⚙️ Installation & Setup Instructions

Follow the steps below to get Veya Bazaar running on your local machine.

### ✅ Prerequisites

Make sure you have the following installed:
- **Node.js** (v18 or above) & **npm**
- **Python** (v3.10 or above) & **pip**
- **PostgreSQL** (v14 or above)
- **Git**

---

### 🔧 Step 1 — Clone the Repository

```bash
git clone https://github.com/your-username/veya-bazaar.git
cd veya-bazaar
```

---

### 🗄️ Step 2 — Database Setup (PostgreSQL)

Open the PostgreSQL shell and run:

```sql
CREATE DATABASE veya_bazaar_db;
CREATE USER veya_user WITH PASSWORD 'yourpassword';
GRANT ALL PRIVILEGES ON DATABASE veya_bazaar_db TO veya_user;
```

---

### ⚙️ Step 3 — Backend Setup (Django)

```bash
# Navigate to backend directory
cd backend

# Create and activate a virtual environment
python -m venv venv
source venv/bin/activate        # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Configure environment variables
# Create a .env file in /backend and add:
# SECRET_KEY=your_django_secret_key
# DB_NAME=veya_bazaar_db
# DB_USER=veya_user
# DB_PASSWORD=yourpassword
# DB_HOST=localhost
# DB_PORT=5432

# Apply database migrations
python manage.py makemigrations
python manage.py migrate

# Create a superuser for admin access
python manage.py createsuperuser

# Start the backend development server
python manage.py runserver
```

The Django API will be live at: `http://127.0.0.1:8000/`

---

### 🌐 Step 4 — Frontend Setup (React.js)

```bash
# Open a new terminal and navigate to the frontend directory
cd frontend

# Install all Node dependencies
npm install

# Start the React development server
npm run dev
```

The React app will be live at: `http://localhost:5173/`

---

## ▶️ Usage Instructions

Once both the backend and frontend servers are running:

1. **Open your browser** and navigate to `http://localhost:5173/`
2. **Register a new account** or log in with existing credentials.
3. **Browse products** on the homepage — use the search bar or category filters to find items.
4. **Click on a product** to view its full detail page including description, ratings, and reviews.
5. **Add items to your cart** and navigate to the Cart page to review your selections.
6. **Proceed to Checkout** and fill in your delivery details to place an order.
7. **View your orders** under the "My Orders" section in your profile.
8. **Admin users** can access the admin panel at `http://127.0.0.1:8000/admin/` or the custom dashboard to manage products and orders.

> 💡 **Tip:** Use the superuser account created during setup to access the Django admin panel and seed initial product data.

---

## 👥 Team Members

This project was designed and developed collaboratively by the following team members:

| 👤 Name | 🎓 Roll Number | 🔧 Role |
|---|---|---|
| **Aditya Jaiswal** | 2210990990 | Frontend Developer & UI/UX Designer | 
| **Simran Dora** | 2210990851 | Full Stack Developer & Project Lead |
| **Ramandeep Singh** | 2210992137 | Backend Developer & Database Administrator |
| **Chinar Gupta** | 2210994778 | API Integration & Quality Assurance |

---

## 🎓 Academic Context

| Detail | Information |
|---|---|
| 📚 **Subject** | IOHE-16 |
| 🏫 **Institution** | Chitkara University, Rajpura |
| 🎓 **Program** | Bachelor of Engineering (Computer Science) |
| 📅 **Academic Year** | 2022–2026 |
| 📝 **Project Type** | Final Year Group Project |

This project was undertaken as part of the final-year curriculum under subject **IOHE-16** at **Chitkara University, Rajpura**. It demonstrates the practical application of software engineering principles including full-stack development, RESTful API design, database management, responsive UI design, and collaborative development workflows.

---

## 🛡️ Intellectual Property / Copyright

> ⚠️ **This project is officially copyright-protected. Unauthorized reproduction, distribution, or use is strictly prohibited.**

The software, source code, design assets, and all associated documentation of **Veya Bazaar** have been officially registered under the **Copyright Act** with the Government of India through the Copyright Office.

| Field | Details |
|---|---|
| 📋 **Work Title** | Veya Bazaar |
| 🗂️ **Nature of Work** | Computer Software / Literary Work |
| 📁 **Diary Number** | **SW-13984/2026-CO** |
| 🌐 **Registration Portal** | [copyright.gov.in](https://copyright.gov.in) |
| 👥 **Copyright Holders** | Aditya Jaiswal, Simran Dora, Ramandeep Singh, Chinar Gupta |
| 🏛️ **Institution** | Chitkara University, Rajpura |

### Legal Notice

All intellectual property rights in and to the Veya Bazaar software — including but not limited to the source code, architecture design, user interface, and documentation — are the exclusive property of the authors and are protected under applicable copyright laws of India. Reproduction, redistribution, modification, or commercial use of any part of this work without the explicit written permission of the copyright holders is strictly prohibited and may be subject to legal action.

For licensing enquiries or permissions, please contact the development team directly.

---

## 🔮 Future Enhancements

The following features are planned for upcoming versions of Veya Bazaar:

- 💳 **Payment Gateway Integration** — Support for Razorpay, Stripe, and UPI-based payments for real transactions.
- 🤖 **AI-Powered Recommendations** — Personalized product suggestions using collaborative filtering and machine learning.
- 📦 **Real-Time Order Tracking** — Live shipment status updates using WebSockets or third-party logistics APIs.
- 🌍 **Multi-Language Support** — Internationalization (i18n) to support Hindi and regional Indian languages.
- 📱 **Progressive Web App (PWA)** — Convert the frontend into a PWA for native-like mobile experience without an app store.
- 📊 **Advanced Analytics Dashboard** — Sales trend charts, revenue breakdowns, and customer behavior analytics for admins.
- 🔔 **Push Notifications** — Real-time alerts for order updates, flash sales, and wishlist price drops.
- ⭐ **Loyalty Points System** — Reward repeat customers with redeemable points on future purchases.
- 🧾 **Invoice Generation** — Automatic PDF invoice generation for completed orders.
- 🔍 **Elasticsearch Integration** — High-performance full-text search for large product catalogs.

---

## 🤝 Contribution Guidelines

We welcome contributions from the community! To contribute to Veya Bazaar, please follow these steps:

1. **Fork** the repository to your own GitHub account.
2. **Clone** your forked repository locally:
   ```bash
   git clone https://github.com/your-username/veya-bazaar.git
   ```
3. **Create a new branch** for your feature or bug fix:
   ```bash
   git checkout -b feature/your-feature-name
   ```
4. **Make your changes** with clear, well-commented code.
5. **Test your changes** thoroughly before committing.
6. **Commit** with a descriptive message:
   ```bash
   git commit -m "feat: add product comparison feature"
   ```
7. **Push** your branch and open a **Pull Request** against the `main` branch.

### 📋 Code Standards
- Follow **PEP 8** for Python/Django code.
- Follow **ESLint + Prettier** conventions for JavaScript/React code.
- Write meaningful commit messages following [Conventional Commits](https://www.conventionalcommits.org/).
- Ensure all new features include appropriate comments and documentation updates.

> ⚠️ All pull requests are subject to review. Please ensure your changes do not break existing functionality.

---

## 📜 License

```
MIT License

Copyright (c) 2026 Aditya Jaiswal, Simran Dora, Ramandeep Singh, Chinar Gupta
Chitkara University, Rajpura

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
```

> 📌 Note: The MIT License applies to the open-source usage of this codebase. For commercial use or redistribution, please refer to the [Copyright Section](#️-intellectual-property--copyright) above and contact the authors.

---

## 🙌 Acknowledgements

We would like to express our sincere gratitude to the following:

- 🏫 **Chitkara University, Rajpura** — for providing us with the academic foundation, infrastructure, and platform to undertake this project.
- 👨‍🏫 **Faculty of IOHE-16** — for their invaluable guidance, mentorship, and constructive feedback throughout the project lifecycle.
- 🌐 **The Open Source Community** — for the incredible tools and libraries that made this project possible, including React.js, Django, Tailwind CSS, and PostgreSQL.
- 🤝 **Our Peers and Reviewers** — for their honest feedback during testing and evaluation phases.
- 💡 **Stack Overflow & GitHub Discussions** — for countless solutions and community wisdom that helped us overcome technical challenges.

---

<p align="center">
  Made with Love By Team Veya Bazaar &nbsp;|&nbsp; Chitkara University, Rajpura &nbsp;|&nbsp; 2022–2026
</p>

<p align="center">
  <a href="#️-veya-bazaar">⬆️ Back to Top</a>
</p>
