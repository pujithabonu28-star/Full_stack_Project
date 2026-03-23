# 🩸 Blood Donation Management System

A full-stack web application built with Django that connects blood donors with people in need, making the donation process faster, easier, and more accessible.

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
---
## 📸 Screenshots

<img width="1920" height="1080" alt="Screenshot (5)" src="https://github.com/user-attachments/assets/6400d6e4-3791-4de2-9f94-1b7eb3b3b4ea" />
<img width="1920" height="1080" alt="Screenshot (4)" src="https://github.com/user-attachments/assets/0b184310-72f4-47f1-9dde-1caa2e8fa638" />
<img width="1920" height="1080" alt="Screenshot (3)" src="https://github.com/user-attachments/assets/a4d626db-cd9f-420e-816e-b2d1bd7f87b2" />
<img width="1920" height="1080" alt="Screenshot (1)" src="https://github.com/user-attachments/assets/acc67598-f7e4-4aba-80a0-d293fdb5bdb5" />
<img width="1920" height="1080" alt="Screenshot (2)" src="https://github.com/user-attachments/assets/6fb80d49-2ddd-4413-9057-17fee63adb4f" />

---
## 🤝 Contributing

Pull requests are welcome! For major changes, please open an issue first to discuss what you'd like to change.

---
## 👩‍💻 Author
**Bonu Pujitha**  
[GitHub](https://github.com/pujithabonu28-star) • [LinkedIn](https://linkedin.com/in/pujithabonu)
