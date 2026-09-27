# 🛍️ ShopSphere - Full-Stack E-Commerce Platform

[![Django](https://img.shields.io/badge/Django-6.0-092E20?style=for-the-badge&logo=django&logoColor=white)](https://www.djangoproject.com/)
[![Python](https://img.shields.io/badge/Python-3.13-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![AI Chatbot](https://img.shields.io/badge/SphereAI-Shopping_Assistant-7c3aed?style=for-the-badge&logo=openai&logoColor=white)](https://www.djangoproject.com/)
[![REST API](https://img.shields.io/badge/REST_API-Django_Rest_Framework-red?style=for-the-badge&logo=fastapi&logoColor=white)](https://www.django-rest-framework.org/)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/)
[![CSS3](https://img.shields.io/badge/CSS3-Modern_Responsive-1572B6?style=for-the-badge&logo=css3&logoColor=white)](https://developer.mozilla.org/)
[![Whitenoise](https://img.shields.io/badge/Whitenoise-Static_Hosting-green?style=for-the-badge)](http://whitenoise.evans.io/)
[![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)](LICENSE)

**ShopSphere** is a modern, high-performance, full-stack e-commerce web application inspired by the best of **Amazon** and **Flipkart**. It is powered by **Django & Python** with rich, dynamic **JSON REST API** endpoints, allowing product rotation on every refresh, a built-in **AI Shopping Assistant & Chatbot (SphereAI)**, lightning deals countdown, AJAX instant cart operations, quick view modal, and seamless 1-click cloud deployment.

---

## 🌟 Key Highlights & Features

### 1. 🤖 SphereAI - Intelligent E-Commerce Shopping Assistant
- **Site-Wide Floating AI Chatbot**: Inspired by Amazon Rufus and Flipkart AI, a glowing floating widget (`✨ Ask SphereAI`) is available across every page.
- **Natural Language Product Search**: Understands budgets (*"laptops under 70k"*, *"phones below 50,000"*), categories (*"smartphones"*, *"running shoes"*), and features (*"gaming"*, *"ANC"*).
- **In-Chat Interactive Product Cards**: Recommends real catalog items embedded right into the chat bubble with image, rating, price, discount badge, and direct "Add to Cart" button!
- **Store Policy & Orders Helper**: Instantly answers questions regarding delivery times, return policies, UPI/COD payments, and cart contents.
- **Dual Intelligence Architecture**:
  - Works **100% out of the box** without any third-party keys using its built-in rule and semantic catalog search engine.
  - Can optionally be enhanced with **Google Gemini Generative AI** by adding `GEMINI_API_KEY` to your environment variables.
- **Dedicated AI Hub Page**: Visit `/ai-assistant/` for a full-screen shopping copilot experience.

### 2. 🔄 Dynamic JSON API & Fresh Data on Refresh
- **Dynamic Live Deals Rotation**: On every page reload or click of **"Refresh Live Deals (API)"**, the store serves randomized hot deals and fresh product selections from the JSON REST API.
- **Dedicated JSON Datasets**:
  - `base/data/products.json` - 50+ diverse e-commerce products across 8 categories with high-res photography, star ratings, discounts, and reviews.
  - `base/data/deals.json` - Promotional event banners and carousel slides.
  - `base/data/categories.json` - Department slugs, icons, and colors.
- **Auto-seeding & Management Command**: Includes `python manage.py seed_products` to populate SQLite/PostgreSQL with products instantly.

### 3. 🎨 Amazon & Flipkart Style UI/UX
- **Iconic Amazon/Flipkart Navbar**:
  - Multi-department search bar with category dropdown filter (`All`, `Mobiles`, `Laptops`, `Audio`, `Fashion`, `Home & Kitchen`, `Fitness`, `Gaming`).
  - Delivery location widget with PIN code / city updater.
  - User account dropdown menu with Profile, Orders, Password Reset, and Sign Out.
  - Real-time cart counter badge with bounce animation.
- **Flipkart Category Bubbles**: Horizontal scrollable circular category bubbles with badges.
- **Hero Promotional Carousel**: 5-second automatic sliding banners with next/prev arrows and indicator dots.
- **⚡ Lightning Deals Bar**: Live ticking countdown timer (`04h : 22m : 18s`) and instant "Refresh Live Deals" button.
- **Product Cards**:
  - Flipkart Assured / Amazon's Choice badge.
  - High-res product images with smooth zoom hover.
  - Star ratings (`★★★★☆ 4.6 (3,420)`).
  - Discount pills (`-45% OFF`), bold current price, and strikethrough M.R.P.
  - Free 1-Day Delivery note.
  - "Quick View" overlay button and "Add to Cart" button.

### 4. ⚡ Modern Interactive JavaScript Features
- **AJAX Add to Cart**: Add products instantly to cart without full page reload, displaying real-time slide-in **Toast Notifications** and updating the navbar cart badge.
- **Quick View Modal**: Inspect product specifications, high-res images, pricing breakdown, and add directly to cart in a sleek modal popup.
- **Password Visibility Toggles**: Interactive eye icon to show/hide passwords on authentication screens.

### 5. 🛒 Amazon & Flipkart 2-Column Cart System
- **Left Column**: Cart items list with product thumbnail, title, category tag, in-stock badge, quantity stepper (`-` `qty` `+`), and "Delete" button.
- **Free Delivery Meter**: Dynamic progress bar calculating how much more to add for free shipping.
- **Right Column**: Flipkart-style "Price Details" card breaking down Subtotal, Discount Savings, Delivery charges, and Grand Total.

### 6. 🔐 Complete Authentication & Profile Dashboard
- Secure Django user authentication with password complexity verification.
- Profile dashboard showing user stats, items in cart, order status, and profile updates.
- Password change, password reset, and forgot password assistance.

### 7. 🚀 Production & Deployment Ready
- Configured with **WhiteNoise** for serving static files in production without Nginx complexity.
- Prepared `Procfile`, `runtime.txt`, `requirements.txt`, `.gitignore`, and `.env.example`.
- Compatible with free hosting on **Render**, **Railway**, **PythonAnywhere**, or **Heroku**.

---

## 📡 REST API Documentation

ShopSphere includes built-in REST API endpoints returning clean JSON data:

| Endpoint | Method | Query / Payload | Description |
| :--- | :--- | :--- | :--- |
| `/api/ai/chat/` | `POST` | `{"message": "query"}` | **SphereAI Chatbot endpoint** returning conversational answers and matching product cards |
| `/api/products/` | `GET` | `q`, `category`, `offer`, `trending`, `sort`, `limit`, `randomize` | Fetch all products with search, filter, and sorting |
| `/api/products/random/` | `GET` | `count` (default: 8) | Returns a randomized batch of products on every call |
| `/api/products/<id>/` | `GET` | — | Fetch single product detail by ID |
| `/api/deals/` | `GET` | — | Fetch promotional banners & lightning deals from `deals.json` |
| `/api/categories/` | `GET` | — | Fetch categories list with icons and live product counts |
| `/api/cart/add/<id>/` | `POST` | — | AJAX endpoint to add item to authenticated user's cart |

---

## 📁 Project Directory Structure

```text
myproject/
├── manage.py
├── db.sqlite3
├── Procfile                  # Render / Railway web process
├── runtime.txt               # Python runtime version
├── requirements.txt          # Python dependencies
├── .env.example              # Environment variables template
├── .gitignore                # Git ignore rules
│
├── myproject/                # Django core project configuration
│   ├── __init__.py
│   ├── settings.py           # Whitenoise, static, media & production settings
│   ├── urls.py               # Main URL router
│   ├── wsgi.py
│   └── asgi.py
│
├── base/                     # Core Store Application
│   ├── models.py             # Products & CartModel
│   ├── views.py              # Home, Product Detail, Cart, Checkout, AI Hub
│   ├── api_views.py          # JSON REST API endpoints
│   ├── ai_assistant.py       # SphereAI Chatbot Engine
│   ├── urls.py               # Store, AI & API routes
│   ├── data/                 # JSON Datasets
│   │   ├── products.json     # 50+ rich e-commerce products
│   │   ├── deals.json        # Promotional banner events
│   │   └── categories.json   # Category icons & slugs
│   ├── management/commands/  # Management Commands
│   │   └── seed_products.py  # python manage.py seed_products
│   └── templates/            # Store templates
│       ├── home.html
│       ├── cart.html
│       ├── product_detail.html
│       ├── checkout.html
│       ├── order_success.html
│       └── ai_assistant.html
│
├── authen/                   # Authentication & User Application
│   ├── views.py              # Login, Register, Profile, Password Reset
│   ├── urls.py
│   └── templates/
│       ├── login_.html
│       ├── register.html
│       ├── profile.html
│       ├── reset.html
│       ├── forget_pasw.html
│       ├── new_pasw.html
│       └── update.html
│
├── static/                   # Static assets
│   ├── styles.css            # Amazon & Flipkart responsive stylesheet
│   ├── js/
│   │   └── app.js            # SphereAI Chatbot, API live refresh, slider, AJAX cart
│   └── images/               # Media & uploads fallback
│
└── templates/                # Base & Layout templates
    ├── main.html             # Base layout (SphereAI widget, toasts, modals)
    └── nav.html              # Amazon/Flipkart navigation header
```

---

## 🛠️ Local Installation & Setup

### 1. Clone the Repository
```bash
git clone https://github.com/<your-username>/shopsphere.git
cd shopsphere/myproject
```

### 2. Create and Activate Virtual Environment
- **On Windows (PowerShell):**
  ```powershell
  python -m venv env
  .\env\Scripts\activate
  ```
- **On macOS / Linux:**
  ```bash
  python3 -m venv env
  source env/bin/activate
  ```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Run Migrations
```bash
python manage.py migrate
```

### 5. Seed the Database from JSON API Data
```bash
python manage.py seed_products
```

### 6. Start Development Server
```bash
python manage.py runserver
```

Open your browser and navigate to:
👉 **`http://127.0.0.1:8000/`**

---

## 📤 How to Share & Push to GitHub

Follow these exact steps to push this project to your GitHub account:

### Step 1: Initialize Git Repository
In your terminal, navigate to the project directory:
```bash
cd "D:\Django\Class Projects\Project\Shopsphere\myproject"
git init
```

### Step 2: Stage and Commit All Files
```bash
git add .
git commit -m "feat: complete ShopSphere e-commerce with Amazon/Flipkart UI, SphereAI Chatbot and dynamic JSON API"
```

### Step 3: Rename Branch to `main`
```bash
git branch -M main
```

### Step 4: Link Your Remote GitHub Repository
1. Go to [GitHub.com](https://github.com/) and create a new public repository (e.g. `shopsphere`).
2. Copy your repository URL, then run:
```bash
git remote add origin https://github.com/<YOUR_GITHUB_USERNAME>/shopsphere.git
```

### Step 5: Push Code to GitHub
```bash
git push -u origin main
```

---

## ☁️ Free Cloud Deployment Guide (Render.com)

Deploying ShopSphere online for free takes less than 3 minutes:

1. Create a free account at [Render.com](https://render.com/).
2. Click **New +** → **Web Service**.
3. Connect your GitHub repository `shopsphere`.
4. Configure the settings:
   - **Name**: `shopsphere`
   - **Environment**: `Python 3`
   - **Root Directory**: `myproject` (or leave blank if repository root has `manage.py`)
   - **Build Command**:
     ```bash
     pip install -r requirements.txt && python manage.py collectstatic --noinput && python manage.py migrate && python manage.py seed_products
     ```
   - **Start Command**:
     ```bash
     gunicorn myproject.wsgi:application
     ```
5. In **Environment Variables**, add:
   - `SECRET_KEY` = `your-custom-secret-key`
   - `DEBUG` = `False`
   - `ALLOWED_HOSTS` = `*`
   - *(Optional)* `GEMINI_API_KEY` = `your-gemini-api-key`
6. Click **Deploy Web Service** — Render will build and host your site with a live HTTPS URL!

---

## 🤝 Contributing & License
Contributions, feedback, and star ratings are welcome!
Licensed under the [MIT License](LICENSE).
