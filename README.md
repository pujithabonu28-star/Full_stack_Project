# 🩸 Blood Donation Management System

A full-stack web application built with Django that connects blood donors with people in need, making the donation process faster, easier, and more accessible.

---

## 🌐 Live Demo

> [https://your-app-name.onrender.com](https://your-app-name.onrender.com) *(update after deployment)*

---

## 📌 Features

- 🏠 **Homepage** – Overview of available blood groups and donor counts
- 🔍 **Search Donors** – Browse donors filtered by blood group
- 👤 **Donor Registration** – Register as a donor with profile image upload
- 🩸 **Request Blood** – Submit a blood request with location and contact details
- 📋 **View All Requests** – See all active blood requests
- 🔐 **User Authentication** – Login / Logout for registered donors
- 📝 **Profile Management** – View and edit donor profile
- 🔄 **Availability Toggle** – Donors can update their ready-to-donate status
- 🛠️ **Admin Dashboard** – Django admin panel for managing all data

---

## 🛠️ Tech Stack

| Layer      | Technology                        |
|------------|-----------------------------------|
| Backend    | Python 3.8, Django 4.2            |
| REST API   | Django REST Framework 3.15        |
| Database   | SQLite (development)              |
| Frontend   | HTML, CSS, JavaScript (Django Templates) |
| Auth       | Django built-in authentication    |
| Media      | Pillow (image uploads)            |
| Deployment | Gunicorn + WhiteNoise + Render    |

---

## 📁 Project Structure

```
Full_stack_Project/
│
├── BloodDonation/          # Project config
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
│
├── home/                   # Main app
│   ├── models.py           # BloodGroup, Donor, RequestBlood
│   ├── views.py            # All view logic
│   ├── urls.py             # App URL routing
│   ├── templates/          # HTML templates
│   ├── static/             # CSS, JS, images
│   └── media/              # Uploaded donor images
│
├── manage.py
├── requirements.txt
├── build.sh                # Render deployment script
└── README.md
```

---

## 🗃️ Database Models

### `BloodGroup`
| Field | Type        |
|-------|-------------|
| name  | CharField   |

### `Donor`
| Field           | Type              |
|-----------------|-------------------|
| donor           | OneToOneField (User) |
| date_of_birth   | CharField         |
| phone           | CharField         |
| city            | CharField         |
| state           | CharField         |
| address         | TextField         |
| blood_group     | ForeignKey        |
| gender          | CharField         |
| image           | ImageField        |
| ready_to_donate | BooleanField      |

### `RequestBlood`
| Field       | Type        |
|-------------|-------------|
| name        | CharField   |
| email       | EmailField  |
| phone       | CharField   |
| state       | CharField   |
| city        | CharField   |
| address     | CharField   |
| blood_group | ForeignKey  |
| date        | CharField   |

---

## ⚙️ Local Setup

### Prerequisites
- Python 3.8+
- pip
- virtualenv (recommended)

### Steps

```bash
# 1. Clone the repository
git clone https://github.com/pujithabonu28-star/Full_stack_Project.git
cd Full_stack_Project

# 2. Create and activate virtual environment
python -m venv venv
source venv/bin/activate      # On Windows: venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Apply migrations
python manage.py migrate

# 5. Create a superuser (for admin access)
python manage.py createsuperuser

# 6. Run the development server
python manage.py runserver
```

Visit: [http://127.0.0.1:8000](http://127.0.0.1:8000)

---

## 🚀 Deployment (Render)

1. Push your code to GitHub
2. Go to [render.com](https://render.com) → New Web Service → Connect repo
3. Set the following:
   - **Build Command:** `./build.sh`
   - **Start Command:** `gunicorn BloodDonation.wsgi:application`
4. Add environment variables:

| Key            | Value                          |
|----------------|--------------------------------|
| `SECRET_KEY`   | Your secure Django secret key  |
| `DEBUG`        | `False`                        |
| `ALLOWED_HOSTS`| `your-app-name.onrender.com`   |

---

## 🔑 Environment Variables

Create a `.env` file in the project root for local development:

```env
SECRET_KEY=your-secret-key-here
DEBUG=True
ALLOWED_HOSTS=127.0.0.1,localhost
```

## 📸 Screenshots

> 

---
## 🤝 Contributing

Pull requests are welcome! For major changes, please open an issue first to discuss what you'd like to change.

---
## 👩‍💻 Author
**Bonu Pujitha**  
[GitHub](https://github.com/pujithabonu28-star) • [LinkedIn](https://linkedin.com/in/pujithabonu)
