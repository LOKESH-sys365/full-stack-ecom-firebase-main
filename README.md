# 🛒 Full Stack E-Commerce App

A full-featured **E-Commerce Web Application** built with **React**, **Firebase**, **Redux Toolkit**, and **Tailwind CSS**. It includes a complete shopping experience for users and a dedicated admin panel for product and order management.

---

## 🌐 Live Demo

> _Add your deployed link here (e.g., Vercel / Firebase Hosting)_

---

## ✨ Features

### 👤 User Side
- 🔐 Sign up & Login with Email/Password (Firebase Auth)
- 🏠 Home page with Hero banner, Categories, Collections, Blogs, and Newsletter
- 🛍️ Browse all products in the Shop
- 🔍 Search & filter products by name, category, color, and price
- 📄 View single product details
- 🛒 Add to Cart, increment/decrement quantity, remove items
- ✅ Checkout & Payment flow (protected routes)
- 📦 View personal order history

### 🛠️ Admin Panel (`/dashboard`)
- 📊 Admin Dashboard overview
- ➕ Add new products to Firestore
- ✏️ Update existing products
- 🗑️ Delete products
- 📋 View all orders
- 👥 View all registered users

---

## 🏗️ Tech Stack

| Technology | Purpose |
|---|---|
| **React 18** | Frontend UI library |
| **Vite** | Fast build tool & dev server |
| **Firebase Auth** | User authentication |
| **Firestore** | NoSQL cloud database |
| **Redux Toolkit** | Cart state management |
| **redux-persist** | Persist cart in localStorage |
| **React Router v6** | Client-side routing & protected routes |
| **Tailwind CSS** | Utility-first CSS styling |
| **Material UI (MUI)** | UI component library |
| **React Toastify** | Toast notifications |

---

## 📁 Project Structure

```
src/
├── App.jsx                    # Root component
├── main.jsx                   # Entry point
│
├── Firebase/
│   └── firebaseConfig.jsx     # Firebase initialization (Auth + Firestore)
│
├── Contexts/
│   └── ContextStore.jsx       # Global state (products, orders, users, filters)
│
├── redux/
│   ├── store.jsx              # Redux store with redux-persist
│   └── cartSlice.jsx          # Cart actions: add, remove, increment, decrement
│
├── Routers/
│   └── Routers.jsx            # All app routes
│
├── ProtectedRoute/
│   ├── UserProtectedRoute.jsx # Guards checkout, payment, orders
│   └── AdminProtectedRoute.jsx# Guards admin dashboard
│
├── Layout/
│   └── Layout.jsx             # Shared layout (Header + Footer wrapper)
│
├── componenets/
│   ├── Pages/
│   │   ├── Home/              # Landing page
│   │   ├── Shop/              # Product listing with filters
│   │   ├── SingleProduct/     # Product detail page
│   │   ├── Cart/              # Shopping cart
│   │   ├── Login/             # Login + Checkout pages
│   │   ├── Signup/            # User registration
│   │   ├── Payment/           # Payment page
│   │   ├── Order/             # User orders
│   │   └── Nopage/            # 404 page
│   │
│   ├── admin/
│   │   ├── Dashboard.jsx      # Admin home
│   │   ├── AddProduct.jsx     # Add product form
│   │   ├── UpdateProduct.jsx  # Update product form
│   │   ├── AllProducts.jsx    # Manage all products
│   │   ├── Orders.jsx         # All orders view
│   │   └── Users.jsx          # All users view
│   │
│   ├── home/                  # Home page sections (Hero, Categories, etc.)
│   ├── Filters/               # Search & filter components
│   ├── Card/                  # Product card component
│   ├── Header/                # Navbar
│   ├── Footer/                # Footer
│   ├── Loader/                # Loading spinner
│   └── common/                # Shared/reusable components
│
├── Data/
│   ├── products.js            # Static product seed data
│   └── blogdata.js            # Blog post data
│
└── assets/                    # Images and static files
```

---

## 🚀 Getting Started

### Prerequisites
- Node.js v16+ and npm installed
- A Firebase project with **Firestore** and **Authentication** enabled

### 1. Clone the Repository

```bash
git clone https://github.com/LOKESH-sys365/full-stack-ecom-firebase-main.git
cd full-stack-ecom-firebase-main/full-stack-ecom-firebase-main
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Configure Firebase

Open `src/Firebase/firebaseConfig.jsx` and replace the config values with your own Firebase project credentials:

```js
const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_AUTH_DOMAIN",
  projectId: "YOUR_PROJECT_ID",
  storageBucket: "YOUR_STORAGE_BUCKET",
  messagingSenderId: "YOUR_MESSAGING_SENDER_ID",
  appId: "YOUR_APP_ID",
}
```

> ⚠️ **Never commit your real Firebase credentials to a public repo.** Use environment variables (`.env`) for production.

### 4. Run the Development Server

```bash
npm run dev
```

Open [http://localhost:5173](http://localhost:5173) in your browser.

### 5. Build for Production

```bash
npm run build
```

---

## 🔐 Authentication Flow

- Users register with **email + password** via Firebase Auth
- On signup, user data is also saved to the **Firestore `users` collection**
- Auth state is stored in `localStorage` and used for protected route checks
- Protected routes (`/checkout`, `/payment`, `/order`) redirect to `/login` if not authenticated

---

## 🛒 Cart & State Management

- Cart state is managed with **Redux Toolkit** (`cartSlice`)
- Supports: `addToCart`, `removeItem`, `incrementQuantity`, `decrementQuantity`
- Cart is **persisted in `localStorage`** using `redux-persist` so it survives page refreshes

---

## 🔎 Product Filtering

Products in the Shop page can be filtered by:
- **Search** — real-time text filter on product title
- **Category** — filter by product category (via radio buttons)
- **Color / Price** — additional attribute filters (via buttons)

All filtering logic is handled inside `ContextStore.jsx`.

---

## 📦 Firestore Collections

| Collection | Description |
|---|---|
| `products` | All product documents (add/update/delete via admin) |
| `users` | Registered user profiles |
| `orders` | Customer order records |

---

## 🛣️ Routes Overview

| Route | Access | Description |
|---|---|---|
| `/` | Public | Home page |
| `/shop` | Public | Browse products |
| `/productdetails/:id` | Public | Single product view |
| `/cart` | Public | Shopping cart |
| `/login` | Public | Login |
| `/signup` | Public | Register |
| `/checkout` | 🔒 User | Checkout form |
| `/payment` | 🔒 User | Payment |
| `/order` | 🔒 User | Order history |
| `/dashboard` | Admin | Dashboard |
| `/dashboard/addproduct` | Admin | Add product |
| `/dashboard/updateproduct` | Admin | Update product |
| `/dashboard/allproducts` | Admin | Manage products |
| `/dashboard/orders` | Admin | View all orders |
| `/dashboard/users` | Admin | View all users |

---

## 🙌 Contributing

Contributions are welcome! Feel free to fork the repo, create a new branch, and submit a pull request.

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).

---

> Built with ❤️ using React + Firebase

