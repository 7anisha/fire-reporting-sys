
# Online Reporting System

This is a Django-based web application for managing online reports. The project includes a Django app for handling reporting features and an integrated deployment setup using Render.

## Project Structure

- `firereport/`: This is a Django app within the project.
  - `migrations/`: Contains database migrations for the `firereport` app.
  - `static/`: Contains static files such as CSS, JS, and images.
  - `templates/`: Contains HTML templates for the `firereport` app.
  - `__init__.py`: Makes this directory a Python package.
  - `admin.py`: Configuration for the Django admin interface for this app.
  - `apps.py`: Configuration for the app itself.
  - `models.py`: Contains database models for this app.
  - `tests.py`: Contains test cases for this app.
  - `views.py`: Contains views (logic for processing requests) for this app.

- `onlinereporting/`: This is the main project directory.
  - `__init__.py`: Makes this directory a Python package.
  - `asgi.py`: ASGI configuration for asynchronous support.
  - `settings.py`: The main settings for your Django project.
  - `urls.py`: URL declarations for your project.
  - `wsgi.py`: WSGI configuration for deployment.

- `db.sqlite3`: SQLite database file for storing all your data.

- `manage.py`: Command-line utility for interacting with this Django project.

## Installation

### Prerequisites

- Python 3.x
- `pip`

### Steps

1. **Clone the Repository**

   ```bash
   git clone https://github.com/7anisha/fire-reporting-sys.git
 
   ```

2. **Create a Virtual Environment**

   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. **Install Dependencies**

   ```bash
   pip install -r requirements.txt
   ```

4. **Apply Migrations**

   ```bash
   python manage.py migrate
   ```

5. **Collect Static Files**

   ```bash
   python manage.py collectstatic
   ```

6. **Run the Development Server**

   ```bash
   python manage.py runserver
   ```

   Access the app at `http://127.0.0.1:8000/`.

## Deployment

This project is configured for deployment on [Render](https://render.com/). Follow these steps to deploy:

1. **Push Code to GitHub**

   ```bash
   git add .
   git commit -m "Prepare for deployment"
   git push origin master
   ```

2. **Create a New Web Service on Render**

   - Log in to Render and create a new web service.
   - Connect your GitHub repository.
   - Set the build command:

     ```bash
     pip install -r requirements.txt
     ```

   - Set the start command:

     ```bash
     gunicorn onlinereporting.wsgi:application --log-file -
     ```

   - Set environment variables as needed (e.g., `SECRET_KEY`, `DATABASE_URL`).

3. **Deploy**

   - Click "Create Web Service" on Render to deploy your app.

## Environment Variables

Ensure the following environment variables are set in your production environment:

- `SECRET_KEY`: Django secret key.
- `DATABASE_URL`: URL for the database (if using PostgreSQL or another database).
- Any other necessary environment variables.

## Contributing

1. Fork the repository.
2. Create a feature branch (`git checkout -b feature-branch`).
3. Commit your changes (`git commit -am 'Add new feature'`).
4. Push to the branch (`git push origin feature-branch`).
5. Open a Pull Request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

- [Django](https://www.djangoproject.com/) - The web framework used.
- [Gunicorn](https://gunicorn.org/) - WSGI server used for deployment.

---

