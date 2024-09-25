# URL Shortener Web Application

A simple URL shortener web application built with Django. This app takes a long URL as input and returns a shortened version using the Bit.ly API.

## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [API](#api)
- [Screenshots](#screenshots)
- [Technologies Used](#technologies-used)

## Features

- Shortens any valid URL using the Bit.ly API.
- Simple and responsive web UI.
- Displays the shortened URL with a direct link.
- Error handling for invalid URLs or issues with the API.

## Installation

1. Clone this repository:

   ```bash
   git clone https://github.com/Venuka04/url-shortener.git
   cd url-shortener
   ```

2. Create and activate a virtual environment:

   ```bash
   python -m venv urlShortner
   source urlShortner/bin/activate   # On Windows: urlShortner\Scripts\activate
   ```

3. Install the required dependencies:

   ```bash
   pip install django
   pip install requests
   ```

4. Set up environment variables (if necessary, such as API keys):

   - Create an account on https://bitly.com/
   - In settings select API. Then Enter your password and Generate an access token.
   - Replace the Bit.ly API token in the `views.py` file:

   ```python
   headers = {
       'Authorization': 'Bearer YOUR_BITLY_API_TOKEN',
       'Content-Type': 'application/json',
   }
   ```

5. Apply the migrations:

   ```bash
   python manage.py migrate
   ```

6. Run the Django development server:

   ```bash
   python manage.py runserver
   ```

7. Open your browser and navigate to:

   ```
   http://127.0.0.1:8000
   ```

## Usage

1. On the home page, enter a long URL in the input field.
2. Click the **Submit** button to shorten the URL.
3. The app will return a shortened URL, which you can copy or click to visit the original website.

## API

This project uses the Bit.ly API to shorten URLs.

- **Endpoint used**: `https://api-ssl.bitly.com/v4/shorten`
- **Request type**: `POST`
- **Authentication**: Bearer Token (requires a valid Bit.ly API token)

## Screenshots

### Home Page (Input Long URL)

![Home Page](screenshots/home_page.png)

### Shortened URL Page

![Shortened URL](screenshots/shortened_url_page.png)

## Technologies Used

- **Frontend**: HTML, Bootstrap
- **Backend**: Django
- **API**: Bit.ly API
- **Database**: SQLite (default for Django)
