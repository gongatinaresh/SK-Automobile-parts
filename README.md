# SK Automobile Parts — Django E-Commerce Platform

A full-stack motorcycle spare parts e-commerce application built using Python, Django, HTML, CSS, JavaScript, and database integration.

**Live Demo:** https://sk-automobile-parts.onrender.com  
**GitHub Repository:** https://github.com/gongatinaresh/SK-Automobile-parts

## Project Overview

SK Automobile Parts enables customers to browse motorcycle spare parts, manage shopping carts, place orders, and track delivery progress. The application includes an administrative dashboard for managing products, categories, inventory, customers, orders, payments, and delivery assignments.

A key feature is GPS-based delivery tracking, which allows customers to view the delivery person's latest reported location on an interactive map after an order goes out for delivery.

## Key Features

- Customer registration and login.
- Product browsing and category-based navigation.
- Shopping cart and checkout.
- Order history and order-status tracking.
- Payment method selection and payment record management.
- Admin dashboard for product, inventory, and order management.
- Delivery personnel dashboard and delivery assignment.
- Browser GPS integration and interactive delivery maps.
- Email notifications for supported order status changes.
- Role-based access and Django authentication.

## Technology Stack

| Layer | Technology |
|---|---|
| Frontend | HTML5, CSS3, JavaScript |
| Backend | Python, Django |
| Database | SQLite for local development; PostgreSQL supported through configuration |
| Database access | Django ORM |
| Authentication | Django Authentication System |
| Maps | Leaflet, CARTO map tiles |
| Location | Browser Geolocation API |
| Email | Gmail SMTP |
| Deployment | Render |
| Version control | Git and GitHub |

## How Frontend, Backend, and Database Connect

This application follows Django's Model-View-Template (MVT) architecture.

1. **Frontend:** HTML, CSS, and JavaScript provide the user interface. Forms and browser requests send data to Django URLs.
2. **URL routing:** Django maps each request to the appropriate view.
3. **Backend:** Django views validate input, enforce permissions, and execute business logic.
4. **Database:** Django models and the ORM create, retrieve, update, and delete records in the configured database.
5. **Response:** Django returns rendered HTML pages or JSON responses to the browser.

### Example: Checkout

The customer adds products to the cart and submits checkout details. Django validates the address and available stock, creates the order and order items through the ORM, and directs the customer to the payment page. Order and payment records are managed by their respective application models.

### Example: Live Delivery Tracking

The delivery person's browser obtains GPS coordinates through the Geolocation API. JavaScript sends the coordinates to a Django endpoint, which validates the delivery user's permissions and saves the latest location in the database. The customer tracking page periodically requests the latest coordinates and updates the delivery marker on a Leaflet map.

## Project Structure

```text
SK-Automobile-parts/
├── accounts/              # Authentication and user profiles
├── products/              # Products and categories
├── cart/                  # Shopping cart
├── orders/                # Orders and delivery tracking
├── payments/              # Payment records
├── dashboard/             # Admin dashboard
├── shops/                 # Shop management
├── delivery/              # Delivery personnel dashboard
├── sk_automobile_parts/   # Django configuration
├── templates/             # Shared templates
├── manage.py
├── requirements.txt
└── README.md
```

## Run Locally

### 1. Clone the repository

```bash
git clone https://github.com/gongatinaresh/SK-Automobile-parts.git
cd SK-Automobile-parts
```

### 2. Create and activate a virtual environment

```powershell
python -m venv venv
.\venv\Scripts\Activate.ps1
```

### 3. Install dependencies

```bash
python -m pip install -r requirements.txt
```

### 4. Configure environment variables

Create a `.env` file in the project root with your local settings:

```env
DJANGO_SECRET_KEY=your-local-secret-key
DEBUG=True
ALLOWED_HOSTS=localhost,127.0.0.1
EMAIL_HOST_USER=
EMAIL_HOST_PASSWORD=
```

Configure `DATABASE_URL` if using PostgreSQL. Never commit `.env` files or production secrets to GitHub.

### 5. Apply migrations and create an admin account

```bash
python manage.py migrate
python manage.py createsuperuser
```

### 6. Start the server

```bash
python manage.py runserver
```

Open http://127.0.0.1:8000/ in your browser.

## Main URLs

| Feature | Path |
|---|---|
| Customer and delivery login | `/login/` |
| Customer registration | `/register/` |
| Product shop | `/products/shop/` |
| Shopping cart | `/cart/` |
| Checkout | `/orders/checkout/` |
| My orders | `/orders/my-orders/` |
| Admin login | `/admin-login/` |
| Delivery dashboard | `/delivery/` |

## Deployment

The application is deployed on Render. Production configuration supports environment variables, Gunicorn, WhiteNoise, and PostgreSQL through `DATABASE_URL`.

Production deployment also requires correct database migrations, static-file configuration, email credentials, and suitable persistent media storage.

## Skills Demonstrated

- Django application development and MVT architecture.
- Frontend-to-backend integration.
- Relational data modeling and Django ORM.
- Authentication and role-based authorization.
- E-commerce and order-management workflows.
- JSON endpoints and browser geolocation.
- Interactive map integration.
- Git, GitHub, and cloud deployment.

## Author

**G. Naresh**

GitHub: https://github.com/gongatinaresh

