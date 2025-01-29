# Flask Hello World

## Overview
This is a minimal Flask application that runs locally and returns "Hello, World!" when accessed via a web browser or API client.

## Requirements
Ensure you have the following installed:
- Python (>=3.7)
- pip (Python package manager)

## Setup Instructions

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

## Additional Enhancements
- Modify the route to return a personalized greeting.
- Deploy the app to a cloud service like **Google Cloud Run** or **Heroku**.

## Troubleshooting
- If Flask is not found, ensure dependencies are installed using `pip install -r requirements.txt`.
- If the port is busy, change `app.run(debug=True)` to `app.run(host='0.0.0.0', port=8080)`. 

---
Happy coding! 🚀