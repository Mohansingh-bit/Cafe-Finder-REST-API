# Cafe-Finder-REST-API
REST API built with Flask &amp; SQLAlchemy — CRUD operations, JSON responses, API key auth, and SQLite database
# ☕ Cafe Finder REST API

A fully functional **REST API** built with Flask and SQLAlchemy that allows users to manage a database of cafes — including their location, amenities, and coffee prices.

This project demonstrates backend development skills including REST API design, database management with ORM, JSON serialization, and API key authentication.

---

## 🚀 Features

- Get a **random cafe** from the database
- Get **all cafes** sorted alphabetically
- **Search cafes** by location
- **Add** a new cafe via POST request
- **Update** a cafe's coffee price via PATCH request
- **Delete** a cafe via DELETE request (protected by API key)
- Proper HTTP status codes — 200, 403, 404
- JSON responses for all endpoints

---

## 🛠️ Technologies Used

- **Python**
- **Flask** — web framework
- **SQLAlchemy** — ORM for database management
- **SQLite** — lightweight local database
- **Postman** — for API testing

---

## 📁 Project Structure

```
cafe-api/
│
├── main.py              # All Flask routes and API logic
├── instance/
│   └── cafes.db         # SQLite database (auto-created)
├── requirements.txt     # Project dependencies
└── README.md            # Project documentation
```

---

## ⚙️ How to Run Locally

### 1. Clone the repository
```
git clone github.com/Mohansingh-bit/Cafe-Finder-REST-API
cd cafe-api
```

### 2. Install dependencies
```
pip install -r requirements.txt
```

### 3. Run the app
```
python main.py
```

The API will start at: `http://127.0.0.1:5000`

---

## 📡 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/random` | Returns a random cafe |
| GET | `/all` | Returns all cafes |
| GET | `/search?loc=Peckham` | Search cafes by location |
| POST | `/add` | Add a new cafe |
| PATCH | `/update-price/<id>?new_price=£3.50` | Update coffee price |
| DELETE | `/report-closed/<id>?api-key=YOUR_KEY` | Delete a cafe |

---

## 🧪 Testing with Postman

### GET — Random cafe
```
GET http://127.0.0.1:5000/random
```

### GET — All cafes
```
GET http://127.0.0.1:5000/all
```

### GET — Search by location
```
GET http://127.0.0.1:5000/search?loc=Peckham
```

### POST — Add a cafe
```
POST http://127.0.0.1:5000/add
Body → x-www-form-urlencoded:
  name         = Blue Bottle Coffee
  map_url      = https://maps.google.com/?q=...
  img_url      = https://example.com/image.jpg
  loc          = Shoreditch
  seats        = 30
  wifi         = True
  toilet       = True
  sockets      = True
  calls        = False
  coffee_price = £3.50
```

### PATCH — Update coffee price
```
PATCH http://127.0.0.1:5000/update-price/1?new_price=£4.00
```

### DELETE — Remove a cafe
```
DELETE http://127.0.0.1:5000/report-closed/1?api-key=YOUR_API_KEY
    ```

---

## 🔐 Authentication

The DELETE endpoint is protected by an API key. Pass it as a query parameter:
```
?api-key=YOUR_API_KEY
```
Wrong or missing key returns `403 Forbidden`.

---

## 📊 Sample JSON Response

```json
{
  "cafe": {
    "id": 1,
    "name": "Blue Bottle Coffee",
    "location": "Shoreditch",
    "seats": "30",
    "has_wifi": true,
    "has_toilet": true,
    "has_sockets": true,
    "can_take_calls": false,
    "coffee_price": "£3.50",
    "map_url": "https://maps.google.com/...",
    "img_url": "https://example.com/image.jpg"
  }
}
```

---

## 🧠 What I Learned

- Designing and building a REST API from scratch
- Using SQLAlchemy ORM with modern mapped_column syntax
- Handling HTTP methods — GET, POST, PATCH, DELETE
- Returning proper JSON responses and HTTP status codes
- Protecting endpoints with API key authentication

---

## 🔮 Future Enhancements

- Add user authentication with JWT tokens
- Migrate from SQLite to PostgreSQL for production
- Build a frontend UI to consume the API
- Deploy to Render or Railway

---

## 📬 Connect With Me

- LinkedIn: [Mohan Singh](https://www.linkedin.com/in/mohan-singh-8b8a612a6)
- GitHub: [Mohansingh-bit](https://github.com/Mohansingh-bit)

⭐ If you found this project useful, please star the repository!
