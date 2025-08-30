# Django REST Framework - Student API Project

This project is a simple implementation to learn the basics of **Django REST Framework (DRF)**.  
It demonstrates how to build an API in Django with authentication, serialization, and API testing using **Postman**.

---

## 📌 What I Learned
- Defining a **Django model** (`Student`).
- Creating a **ModelSerializer** to convert model data into JSON.
- Using **APIView** to handle `GET` and `POST` requests.
- Adding **Token Authentication** for securing APIs.
- Applying permissions with `IsAuthenticated`.
- Testing APIs with **Postman** (sending requests, headers, tokens).
- Understanding how to create and consume REST APIs.

---

## 🛠️ Features Implemented
- **Student Model**:
  - Fields: `name`, `age`, `description`, `date_enrolled`.
- **Serializer**:
  - `StudentSerializer` exposes only `name` and `age`.
- **API Endpoints**:
  - `GET /` → Returns the first student record.
  - `POST /` → Creates a new student from request data.
- **Authentication**:
  - Login/Logout using DRF (`/api-auth/`).
  - Token Authentication (`/api/token/`).

---

## 🚀 Running the Project
1. Clone the project:
   ```bash
   git clone https://github.com/singh-gauravv/django-RESTframework.git
   cd drfproj
   ```

2. Install dependencies:
   ```bash
   pip install django djangorestframework
   pip install djangorestframework-simplejwt
   ```

3. Apply migrations:
   ```bash
   python manage.py makemigrations
   python manage.py migrate
   ```

4. Create a superuser:
   ```bash
   python manage.py createsuperuser
   ```

5. Run the server:
   ```bash
   python manage.py runserver
   ```

---

## 📂 API Endpoints
- `GET /` → Returns the first student record.  
- `POST /` → Create a new student (JSON body required).  
- `GET /api-auth/` → Login/Logout (session-based).  
- `POST /api/token/` → Obtain authentication token.  

---

## 🔑 Example API Usage (Postman)

### 1. Obtain Token
**POST** `http://127.0.0.1:8000/api/token/`  
Body (form-data or raw JSON):
```json
{
  "username": "your_username",
  "password": "your_password"
}
```
Response:
```json
{
  "token": "generated_auth_token"
}
```

### 2. Create Student
**POST** `http://127.0.0.1:8000/`  
Headers:
```
Authorization: Token your_generated_token
Content-Type: application/json
```
Body:
```json
{
  "name": "John Doe",
  "age": 20
}
```
Response:
```json
{
  "name": "John Doe",
  "age": 20
}
```

### 3. Get Student
**GET** `http://127.0.0.1:8000/`  
Headers:
```
Authorization: Token your_generated_token
```
Response:
```json
{
  "name": "John Doe",
  "age": 20
}
```

---

## ✅ Next Steps
- Extend API with **list, update, and delete** operations.
- Use **ViewSets & Routers** for cleaner API structure.
- Add validation in serializers.
- Switch from TokenAuth to **JWT Authentication**.

---

💡 *This project helped me understand Django REST Framework, authentication, and how to test APIs effectively with Postman.*
