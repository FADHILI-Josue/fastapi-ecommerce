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