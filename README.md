# Prerna

Prerna's is an online Python Ecommerce website built with Django, SQLite and Bootstrap. A simple and lightweight ecommerce app easily deployable anywhere anytime with modules developed upon the inbuilt django admin.

# Get Started

To setup the prerna project, here is the following guidelines:

- Open Project folder on terminal
- Prepare your virtual environment <code>python3 -m venv venv</code>
- Activate your virtual environment <code>source env/bin/activate</code>
- Install your requirements.txt file <code>pip install -r requirements.txt</code>
- Create migrations using <code>python3 manage.py makemigrations</code>
- Run migrations <code>python3 manage.py migrate</code>
- Start your dev server with <code>python3 manage.py runserver</code>
- Visit your App using <code>http://127.0.0.1:8000/</code>
- Create super user to access admin dashboard using <code> python3 manage.py createsuperuser</code>
- Follow the prompts after <code>Username: , Email address: , Password: , Password (again): </code>
- Visit Admin Page using <code>http://127.0.0.1:8000/admin</code> and login with the credentials created above.
- Add Products under the <b>Products</b> Menu, Add Offers also.
- Visit Products Page using <code>http://127.0.0.1:8000/products/</code>
- Visit New Arrival (Products) Page using <code>http://127.0.0.1:8000/products/new</code>
- Wish to extend codebase/project? just say hi

---

## Front-end redesign — Prerna's Ecommerce

`products/templates/index.html` has been replaced with a full front-end redesign: **Prerna's Ecommerce**, a Flipkart-style storefront for women's fashion. It's a self-contained HTML/CSS/JavaScript single-page app (no build step) covering registration/login (incl. social-login UI), profile & address book, search/filter/sort, product details with reviews & ratings, wishlist, cart, full checkout (guest checkout, shipping, multiple payment options, coupons, tax), order history & tracking, cancellations/returns, and notification preferences.

- All product, cart, wishlist, order and login data is currently mocked and stored in the browser's `localStorage` — it is **not yet wired up** to the Django backend (`products/models.py`, `views.py`) in this repo.
- To connect it, extend `products/views.py` to return real product data (e.g. as JSON via an API endpoint), and replace the `PRODUCTS` array and `localStorage`-based logic near the top of the `<script>` block in `index.html` with calls to those endpoints.
- Product "photos" are elegant color-coded placeholder tiles rather than real images (see the `swatchDiv()` function) — swap in real `<img>` tags once you have image URLs or an upload pipeline.

### Run it as-is (frontend only)

Just open `products/templates/index.html` directly in a browser.

### Run it through Django (as originally intended)

```
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
```

Then visit `http://127.0.0.1:8000/` — Django will render `products/templates/index.html` as the homepage.
