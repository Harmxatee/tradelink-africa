# 🌍 TradeLink Africa

> **Buy. Sell. Connect.**
> Africa's modern online marketplace — connecting buyers and sellers across every state.

---

## 📁 Project Structure

```
tradelink-africa/
├── backend/                  # Node.js + Express API
│   ├── config/
│   │   └── cloudinary.js     # Cloudinary image upload config
│   ├── middleware/
│   │   └── auth.js           # JWT auth middleware
│   ├── models/
│   │   ├── User.js           # User schema
│   │   ├── Product.js        # Product schema
│   │   └── Payment.js        # Payment schema
│   ├── routes/
│   │   ├── auth.js           # Register, Login, /me
│   │   ├── users.js          # Profiles, dashboard
│   │   ├── products.js       # CRUD products
│   │   ├── payments.js       # Paystack integration
│   │   └── admin.js          # Admin panel routes
│   ├── scripts/
│   │   └── seedAdmin.js      # Create first admin user
│   ├── server.js             # Main entry point
│   ├── render.yaml           # Render deployment config
│   ├── .env.example          # Environment variables template
│   └── package.json
│
└── frontend/                 # React app
    ├── public/
    │   └── index.html
    ├── src/
    │   ├── components/
    │   │   ├── Navbar.js / .css
    │   │   ├── Footer.js / .css
    │   │   └── ProductCard.js / .css
    │   ├── context/
    │   │   └── AuthContext.js    # JWT auth state
    │   ├── pages/
    │   │   ├── Home.js / .css           # Landing page
    │   │   ├── Register.js / Auth.css   # Registration
    │   │   ├── Login.js                 # Login
    │   │   ├── SellerActivation.js      # Paystack activation
    │   │   ├── PaymentVerify.js         # Post-payment verify
    │   │   ├── Dashboard.js / .css      # Seller dashboard
    │   │   ├── Marketplace.js / .css    # Product listings
    │   │   ├── ProductDetail.js / .css  # Single product
    │   │   ├── SellerProfile.js / .css  # Public seller page
    │   │   ├── AdminDashboard.js / .css # Admin panel
    │   │   └── NotFound.js              # 404
    │   ├── utils/
    │   │   └── api.js            # Axios instance
    │   ├── App.js                # Routes
    │   ├── index.js              # Entry point
    │   └── index.css             # Global styles
    ├── vercel.json               # Vercel deployment config
    ├── .env.example
    └── package.json
```

---

## ⚙️ Prerequisites

- Node.js v18+
- npm v9+
- MongoDB Atlas account (free tier works)
- Cloudinary account (free tier works)
- Paystack account (test or live keys)
- Vercel account (frontend)
- Render account (backend)

---

## 🚀 Local Installation

### 1. Clone the repo

```bash
git clone https://github.com/yourusername/tradelink-africa.git
cd tradelink-africa
```

---

### 2. Set up the Backend

```bash
cd backend
npm install
cp .env.example .env
```

Edit `.env` with your real credentials:

```env
PORT=5000
NODE_ENV=development
MONGODB_URI=mongodb+srv://<user>:<pass>@cluster0.xxxxx.mongodb.net/tradelink-africa
JWT_SECRET=make_this_a_long_random_string_at_least_64_chars
JWT_EXPIRE=7d
CLOUDINARY_CLOUD_NAME=your_cloudinary_name
CLOUDINARY_API_KEY=your_cloudinary_key
CLOUDINARY_API_SECRET=your_cloudinary_secret
PAYSTACK_SECRET_KEY=sk_test_your_paystack_secret
PAYSTACK_PUBLIC_KEY=pk_test_your_paystack_public
FRONTEND_URL=http://localhost:3000
ADMIN_EMAIL=admin@tradelinkafrica.com
ADMIN_PASSWORD=Admin@TradeLink2025
```

**Seed the admin account:**

```bash
node scripts/seedAdmin.js
```

**Start the backend server:**

```bash
npm run dev
# Server runs on http://localhost:5000
```

---

### 3. Set up the Frontend

```bash
cd ../frontend
npm install
cp .env.example .env
```

Edit `.env`:

```env
REACT_APP_API_URL=http://localhost:5000/api
REACT_APP_PAYSTACK_PUBLIC_KEY=pk_test_your_paystack_public_key
REACT_APP_SITE_URL=http://localhost:3000
```

**Start the frontend:**

```bash
npm start
# App runs on http://localhost:3000
```

---

## 🌐 API Routes Reference

### Auth
| Method | Route | Description | Auth |
|--------|-------|-------------|------|
| POST | `/api/auth/register` | Register new user | ❌ |
| POST | `/api/auth/login` | Login | ❌ |
| GET | `/api/auth/me` | Get current user | ✅ |

### Products
| Method | Route | Description | Auth |
|--------|-------|-------------|------|
| GET | `/api/products` | Browse marketplace | ❌ |
| GET | `/api/products/:id` | Single product | ❌ |
| GET | `/api/products/categories` | List categories | ❌ |
| POST | `/api/products` | Create product | ✅ Seller |
| PUT | `/api/products/:id` | Edit product | ✅ Seller |
| DELETE | `/api/products/:id` | Delete product | ✅ Seller |
| GET | `/api/products/seller/my-products` | My products | ✅ Seller |

### Users
| Method | Route | Description | Auth |
|--------|-------|-------------|------|
| GET | `/api/users/seller/:username` | Public seller profile | ❌ |
| GET | `/api/users/dashboard` | Dashboard stats | ✅ |
| PUT | `/api/users/profile` | Update profile | ✅ |

### Payments
| Method | Route | Description | Auth |
|--------|-------|-------------|------|
| POST | `/api/payments/initialize` | Start Paystack payment | ✅ |
| GET | `/api/payments/verify/:reference` | Verify payment | ✅ |
| POST | `/api/payments/webhook` | Paystack webhook | ❌ |
| GET | `/api/payments/history` | Payment history | ✅ |

### Admin (Admin only)
| Method | Route | Description |
|--------|-------|-------------|
| GET | `/api/admin/stats` | Platform stats |
| GET | `/api/admin/users` | All users |
| PATCH | `/api/admin/users/:id/suspend` | Suspend/unsuspend |
| PATCH | `/api/admin/users/:id/verify-seller` | Verify seller |
| GET | `/api/admin/products` | All products |
| DELETE | `/api/admin/products/:id` | Remove product |
| GET | `/api/admin/payments` | All payments |

---

## 🚢 Deployment Guide

### Backend → Render

1. Push your code to GitHub
2. Go to [render.com](https://render.com) → **New Web Service**
3. Connect your GitHub repo → select the `backend/` folder
4. Set **Build Command**: `npm install`
5. Set **Start Command**: `node server.js`
6. Add all environment variables from `.env.example`
7. Click **Deploy**
8. Copy the Render URL: `https://tradelink-africa-api.onrender.com`

**After deploying**, seed the admin:
```bash
# In Render shell or locally with production MONGODB_URI
node scripts/seedAdmin.js
```

---

### Frontend → Vercel

1. Go to [vercel.com](https://vercel.com) → **New Project**
2. Import your GitHub repo → set **Root Directory** to `frontend`
3. Add environment variables:
   ```
   REACT_APP_API_URL = https://tradelink-africa-api.onrender.com/api
   REACT_APP_PAYSTACK_PUBLIC_KEY = pk_live_your_key
   REACT_APP_SITE_URL = https://your-app.vercel.app
   ```
4. Click **Deploy**

---

### Database → MongoDB Atlas

1. Go to [mongodb.com/cloud/atlas](https://mongodb.com/cloud/atlas)
2. Create a free cluster
3. Create a database user (username + password)
4. Whitelist IP: `0.0.0.0/0` (allow all — required for Render)
5. Get connection string and set as `MONGODB_URI`

---

### Cloudinary Setup

1. Go to [cloudinary.com](https://cloudinary.com) → Sign up free
2. Dashboard → copy **Cloud Name**, **API Key**, **API Secret**
3. Add to both local `.env` and Render environment variables

---

### Paystack Setup

1. Go to [paystack.com](https://paystack.com) → Sign up
2. Dashboard → Settings → API Keys
3. Copy **Secret Key** and **Public Key**
4. For testing use `sk_test_` / `pk_test_` keys
5. For production use `sk_live_` / `pk_live_` keys
6. Add Paystack webhook URL in their dashboard:
   ```
   https://tradelink-africa-api.onrender.com/api/payments/webhook
   ```

---

## 🔒 Security Features

- ✅ Passwords hashed with bcryptjs (12 salt rounds)
- ✅ JWT authentication with 7-day expiry
- ✅ Rate limiting (100 req/15min global, 20 req/15min auth)
- ✅ Helmet.js security headers
- ✅ Input validation with express-validator
- ✅ CORS restricted to frontend domain
- ✅ No sensitive data in public API responses
- ✅ Paystack webhook signature verification
- ✅ Admin routes require admin role
- ✅ Seller routes require activated seller account

---

## 🎯 Key Features Summary

| Feature | Status |
|---------|--------|
| User Registration & Login | ✅ |
| Profile Photo Upload (Cloudinary) | ✅ |
| Seller Activation via Paystack | ✅ |
| Payment Receipt Generation | ✅ |
| Product CRUD with Images | ✅ |
| Marketplace Search & Filters | ✅ |
| Filter by Category & State | ✅ |
| Seller Public Profile Link | ✅ |
| Dashboard with Stats | ✅ |
| Admin Panel | ✅ |
| Suspend Users | ✅ |
| Verify Sellers | ✅ |
| Paystack Webhook | ✅ |
| Mobile Responsive | ✅ |
| JWT Authentication | ✅ |
| Rate Limiting | ✅ |

---

## 📞 Support

Email: support@tradelinkafrica.com
Built with ❤️ for Africa.
