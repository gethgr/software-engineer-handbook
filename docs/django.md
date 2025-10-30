# ⚙️ Django Commands Cheat Sheet

> Practical guide for most common and usefull commands for Django (manage.py).

---

## 🧩️ Development

```bash
python manage.py runserver
# Starts the local server at the default port.

python manage.py shell
# Starts a Python shell with access to Django models.

python manage.py check
# Check for project configuration errors.
```

---

## 💃️ Database & Migrations

```bash
python manage.py makemigrations
# Create new migration files for all installed apps that have changes.

python manage.py migrate
# Apply migrations to the database.

python manage.py showmigrations
# Display all migrations and their applied status.

python manage.py sqlmigrate app_name 0001
# Display the SQL query belonging to the migration.

python manage.py flush
# Delete all data and reset the database to its initial state.
```

---

## 👤 Users & Authentication

```bash
python manage.py createsuperuser
# Create an admin user.

python manage.py changepassword username
# Change password for a user.
```

---

## 🧹 Static Files

```bash
python manage.py collectstatic
# Collect all static files in STATIC_ROOT.

python manage.py findstatic css/style.css
# Find the path of the current static file.
```

---

## 📦 Fixtures & Data

```bash
python manage.py dumpdata > data.json
# Export data from the database into a JSON file.

python manage.py loaddata data.json
# Import data from a JSON file.

python manage.py dbshell
# Open the database shell.
```

---

## 🧮 Utilities & Debugging

```bash
python manage.py diffsettings
# Displays the differences between current settings and default settings.

python manage.py showmigrations
# Displays the migrations and their applied status.

python manage.py show_urls
# (django-extensions) Displays all registered URLs.

python manage.py runscript script_name
# (django-extensions) Executes a custom Python script.
```

---

## 🧱 Custom Commands

```bash
python manage.py my_custom_command
# Run the custom management command from app/management/commands/
```