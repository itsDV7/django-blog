# Django Blog

A simple blog application built with Django by following the [Django Girls Tutorial](https://tutorial.djangogirls.org).  
This project is a great starting point for learning modern web development with Python and Django.

- **Live blog**: [itsdv7.pythonanywhere.com](https://itsdv7.pythonanywhere.com)
- **Tutorial followed**: [Django Girls Tutorial](https://tutorial.djangogirls.org)

---

## Features

- **Blog posts** with title, text, author, and created/published dates
- **Post list** page showing all published posts
- **Post detail** page with full content
- **Create & edit posts** via a web form (only for logged-in user)
- **Simple, clean layout** using custom CSS
- Built with **Django** and follows common best practices from the Django Girls guide

---

## Project Structure (High-Level)

Typical key files/directories in this project:

- `mysite/`
  - `settings.py` – main Django settings (apps, database, static files, etc.)
  - `urls.py` – root URL configuration that includes the blog URLs
- `blog/`
  - `models.py` – `Post` model defining blog posts
  - `views.py` – functions/classes that handle requests and return responses
  - `urls.py` – URL patterns for the blog pages
  - `forms.py` – Django form for creating/editing posts
  - `templates/blog/`
    - `base.html` – base layout shared by other templates
    - `post_list.html` – list of posts
    - `post_detail.html` – single post page
    - `post_edit.html` – create/edit post form
  - `static/css/blog.css` – custom styles for the blog UI

---

## Steps Taken to Create This Project

These are the main steps that were followed, based on the [Django Girls Tutorial](https://tutorial.djangogirls.org):

1. **Set up environment**
   - Installed Python and pip
   - Created a virtual environment and activated it
   - Installed Django inside the virtual environment

2. **Created the Django project**
   - Ran `django-admin startproject mysite` to create the project
   - Configured `mysite/settings.py` (allowed hosts, installed apps, static files, etc.)
   - Verified everything worked with `python manage.py runserver`

3. **Created the blog app**
   - Ran `python manage.py startapp blog`
   - Added `blog` to `INSTALLED_APPS` in `mysite/settings.py`

4. **Built the `Post` model**
   - Defined a `Post` model in `blog/models.py` with fields like `title`, `text`, `author`, `created_date`, `published_date`
   - Created and applied migrations with:
     - `python manage.py makemigrations`
     - `python manage.py migrate`

5. **Admin setup**
   - Created a superuser with `python manage.py createsuperuser`
   - Registered the `Post` model in `blog/admin.py`
   - Logged in to the Django admin panel and created sample blog posts

6. **Views, URLs, and templates**
   - Created views in `blog/views.py`:
     - Post list view (shows all published posts)
     - Post detail view (shows a single post)
   - Set up `blog/urls.py` and included it in `mysite/urls.py`
   - Created templates in `blog/templates/blog/`:
     - `base.html` (base layout)
     - `post_list.html`
     - `post_detail.html`

7. **Forms and editing posts**
   - Created a `PostForm` in `blog/forms.py`
   - Added views and templates for creating/editing posts (`post_edit.html`)
   - Used Django’s form handling to save and update posts
   - Added links/buttons in templates for creating and editing posts

8. **Static files and styling**
   - Created `blog/static/css/blog.css` for custom styling
   - Linked the CSS in `base.html` using Django’s `{% static %}` tag
   - Updated HTML structure to look clean and modern

9. **Deployment to PythonAnywhere**
   - Pushed the code to a Git repository (optional but recommended)
   - Created a PythonAnywhere account
   - Uploaded the project / pulled from GitHub to PythonAnywhere
   - Configured the virtualenv, WSGI file, and static files
   - Set allowed hosts and debug settings for production
   - Tested the live site at [itsdv7.pythonanywhere.com](https://itsdv7.pythonanywhere.com)

---

## Quick Overview Tutorial (How to Use / Extend This)

### 1. Running the Project Locally

```bash
# 1. Clone your repository
git clone https://github.com/<your-username>/<your-repo>.git
cd <your-repo>

# 2. Create and activate a virtual environment (macOS / Linux)
python3 -m venv venv
source venv/bin/activate

# 3. Install dependencies
pip install django

# 4. Apply migrations
python manage.py migrate

# 5. Create a superuser (optional, for admin access)
python manage.py createsuperuser

# 6. Run the development server
python manage.py runserver
```

Open `http://127.0.0.1:8000/` in your browser to see the blog.

### 2. Creating and Editing Posts

- Go to the blog home page (post list).
- Use the **“New post”** link/button (if implemented) to create a post.
- Fill in the form (title and text) and save.
- Click on a post title in the list to see the full detail page.
- Use the **“Edit”** link on the detail page to update an existing post.

Alternatively:

- Log into the **Django admin** at `http://127.0.0.1:8000/admin/`
- Add, edit, or delete posts directly from the admin interface.

### 3. Where to Edit Things

- **Change layout / HTML**: edit templates in `blog/templates/blog/`
  - `base.html` for global layout (header, footer, etc.)
  - `post_list.html` and `post_detail.html` for main pages
- **Change styles / colors / fonts**: edit `blog/static/css/blog.css`
- **Change data model** (new fields or models): edit `blog/models.py` and run migrations
- **Change URLs / add pages**: modify `blog/urls.py` and `mysite/urls.py`
- **Change logic** (what data is shown, filters, redirections): edit `blog/views.py`

---

## Learning Resources

This project closely follows the official tutorial:

- **Main guide**: [Django Girls Tutorial](https://tutorial.djangogirls.org)

It’s highly recommended to go through the tutorial step by step to deepen your understanding of what each part of this project does and how Django works.
