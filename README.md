# Flask Hello World

## Overview
This is a minimal Flask application that runs locally and returns "Hello, World!" when accessed via a web browser.

## Requirements
Ensure you have the following installed:
- Python (>=3.7)
- pip (Python package manager)

  
---

## Exercise 1
### Setup Instructions

1. **Clone the repository on your local machine:**
   ```sh
   git clone <repository_url>
   cd flask-hello-world
   ```

2. **Create a virtual environment (optional but recommended):**
   ```sh
   python -m venv venv
   source venv/bin/activate  # On macOS/Linux
   venv\Scripts\activate     # On Windows
   ```

3. **Install dependencies:**
   ```sh
   pip install -r requirements.txt
   ```

4. **Run the application:**
   ```sh
   python app.py
   ```

5. **Access the application:**
   Open a web browser and go to:
   ```
   http://127.0.0.1:5000/
   ```
   You should see "Hello, World!" displayed on the page.

## Understanding the Code

```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def hello_world():
    return "Hello, World!"

if __name__ == '__main__':
    app.run(debug=True)
```

### Breakdown: 
- `Flask(__name__)` initializes a Flask web application.
- `@app.route('/')` maps the root URL (`/`) to the `hello_world` function.
- `return "Hello, World!"` sends the response when the URL is accessed.
- `app.run(debug=True)` starts the development server with debug mode enabled.

---

## Exercise 2
### Assignment Instructions
Modify the page by adding a base.html file to the repository to set the look and feel of your local application.
  
1. Create a directory within the respository at the root level called 'templates'
2. In the templates directory create a file called base.html and copy and paste the below contents to the html file.
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>{% block title %}Flask App{% endblock %}</title>
</head>
<body>
    <header>
        <h1>My Flask Application</h1>
    </header>

    <main>
        {% block content %}{% endblock %}
    </main>

    <footer>
        <p>&copy; 2025 Flask App</p>
    </footer>
</body>
</html>
```

  3. In the templates directory create another html file called index.html and copy and paste the below contents to the html file.
```
{% extends 'base.html' %}

{% block title %}Home - Flask App{% endblock %}

{% block content %}
    <h2>Hello, World!</h2>
{% endblock %}
```

  4. Update the app.py file to have this content:
```python
from flask import Flask, render_template

app = Flask(__name__)

@app.route('/')
def home():
    return render_template('index.html')

if __name__ == '__main__':
    app.run(debug=True)
```
5. Flask allows you to use your local machine as a server and host a local application. Once you have successfully run the app from the terminal, to terminate the server upon completion of the assignment, you will need to execute **Ctrl + C**.

## Troubleshooting
- If Flask is not found, ensure dependencies are installed using `pip install -r requirements.txt`.
- If the port is busy, change `app.run(debug=True)` to `app.run(host='0.0.0.0', port=8080)`. Don't forget to update the port in the url.
- If you go to the end point for your localhost and your page is not redendering then you need to run: 
   ```sh
   python app.py
   ```
---
Happy coding! 🚀
