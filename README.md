# Ecommerce API  

A lightweight Ecommerce API built with **FastAPI**, featuring product management, user authentication, cart management, and more.

## Features  
- Product endpoints  
- User authentication  
- Cart management  
- Search and filter  
- Account management  
- Swagger integration  

## Technologies  
- FastAPI, PostgreSQL, JWT, Pydantic, Uvicorn, SQLAlchemy  

## API Endpoints



| Endpoint                          | HTTP Method | Path                                      | Description                                             | User Type       |
|-----------------------------------|-------------|-------------------------------------------|---------------------------------------------------------|-----------------|
| Product List                      | GET         | `/products/`                              | Get a list of all products                               | User            |
| Create Product                    | POST        | `/products/`                              | Create a new product                                     | Admin           |
| Retrieve Product by ID            | GET         | `/products/{id}/`                         | Get details of a specific product by ID                  | User            |
| Update Product by ID              | PUT         | `/products/{id}/`                         | Update details of a specific product by ID               | Admin           |
| Delete Product by ID              | DELETE      | `/products/{id}/`                         | Delete a specific product by ID                          | Admin           |
| Category List                     | GET         | `/categories/`                            | Get a list of all categories                             | User            |
| Create Category                   | POST        | `/categories/`                            | Create a new category                                    | Admin           |
| Retrieve Category by ID           | GET         | `/categories/{id}/`                       | Get details of a specific category by ID                 | User            |
| Update Category by ID             | PUT         | `/categories/{id}/`                       | Update details of a specific category by ID              | Admin           |
| Delete Category by ID             | DELETE      | `/categories/{id}/`                       | Delete a specific category by ID                         | Admin           |
| User List (Admin Only)            | GET         | `/users/`                                 | Get a list of all users (admin-only)                     | Admin           |
| Get User By ID (Admin Only)       | GET         | `/users/{user_id}/`                       | Get details of a specific user by ID (admin-only)       | Admin           |
| Create User (Admin Only)          | POST        | `/users/`                                 | Create a new user (admin-only)                           | Admin           |
| Update User By ID (Admin Only)    | PUT         | `/users/{user_id}/`                       | Update details of a specific user by ID (admin-only)    | Admin           |
| Delete User By ID (Admin Only)    | DELETE      | `/users/{user_id}/`                       | Delete a specific user by ID (admin-only)               | Admin           |
| Get My Account Info               | GET         | `/account/`                               | Get information about the authenticated user            | User            |
| Edit My Account Info              | PUT         | `/account/`                               | Edit the information of the authenticated user           | User            |
| Remove My Account                 | DELETE      | `/account/`                               | Remove the account of the authenticated user             | User            |
| User Signup                       | POST        | `/auth/signup/`                           | Register a new user                                      | User            |
| User Login                        | POST        | `/auth/login/`                            | Authenticate and generate access tokens for a user       | User            |
| Refresh Access Token              | POST        | `/auth/refresh/`                          | Refresh an access token using a refresh token             | User            |
| Swagger UI                        | -           | `/docs/`                                  | Swagger UI for API documentation                         | User            |
| Swagger JSON (without UI)         | -           | `/openapi.json`                           | OpenAPI JSON for API documentation without UI           | User            |
| ReDoc UI                          | -           | `/redoc/`                                | ReDoc UI for API documentation                           | User            |



## Screenshots 

![image](./docs//api-swagger-doc.png)



## Installation

1. **Clone the repository:**

   ```bash
   git clone https://github.com/FADHILI-Josue/fastapi-ecommerce.git
   ```

2. **Navigate to the project directory:**

   ```bash
   cd fastapi-ecommerce
   ```

3. **Create a virtual environment:**

   ```bash
   python3 -m venv venv
   ```

4. **Activate the virtual environment:**

   On Windows:

   ```bash
   venv\Scripts\activate
   ```

   On macOS and Linux:

   ```bash
   source venv/bin/activate
   ```

5. **Install dependencies:**

   ```bash
      pip install -r requirements.txt
   ```

## Usage

1. **Create database `fastapi_ecommerce` or other preferred name and update the Database connection string url in [alembic.ini](./alembic.ini)**  
   ```py
   sqlalchemy.url = postgresql://postgres:[password]@localhost:5432/[db_name]
   ```
2. **Rename the `.env.example` file to `.env` and fill required env variables**
   ```bash
      # Database Config
      DB_USERNAME=postgres
      DB_PASSWORD=password
      DB_HOSTNAME=localhost
      DB_PORT=5432
      DB_NAME=fastapi_ecommerce

      # JWT Config
      SECRET_KEY=secret_key
      ALGORITHM=HS256
      ACCESS_TOKEN_EXPIRE_MINUTES=30
   ```
3. **Run Alembic migrations:**
   ```bash
      alembic revision --autogenerate -m "Initial migration"
   ```

   This will apply any pending database migrations.

4. **migrate the created migrations**
   ```bash
      alembic upgrade head
   ```

5. **Run the FastAPI development server:**

   ```bash
   python run.py
   ```

   The API will be accessible at [http://127.0.0.1:8000/](http://127.0.0.1:8000/)

6. **Access the Swagger UI and ReDoc:**

   - Swagger UI: [http://127.0.0.1:8000/docs/](http://127.0.0.1:8000/docs/)
   - ReDoc: [http://127.0.0.1:8000/redoc/](http://127.0.0.1:8000/redoc/)




## Contributing

Feel free to contribute to the project. Fork the repository, make changes, and submit a pull request.



