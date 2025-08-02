"Flask Hello World App Containerized with Docker"

---

```markdown
# 🐍 Flask "Hello, World!" App in Docker 🐳

This project is a minimal **Python Flask** web application that returns "Hello, world!" at the root URL.  
The app is then **containerized using Docker** to run in an isolated, reproducible environment.


---

## 🚀 Features

- ✅ Minimal Flask application
- ✅ Dockerized for portability
- ✅ Runs on port `5002`
- ✅ Easy to build and run

---

## 👨‍💻 Step 1: The Python App

Your Flask application is defined in `app.py`:

```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def hello_world():
    return 'Hello, world!'

if __name__ == '__main__':
    app.run(host='0.0.0.0', port=5002)
````

This runs a web server on port `5002` and responds with `"Hello, world!"` at `/`.

---

## 📦 Step 2: Containerizing with Docker

Here is the `Dockerfile` used to build a container image for this app:

```Dockerfile
FROM python:3.11-slim

WORKDIR /app

COPY . /app

RUN pip install flask

EXPOSE 5002

CMD ["python", "app.py"]
```

This tells Docker to:

* Use Python 3.11 as a base image
* Set the working directory
* Copy the app code
* Install Flask
* Expose port `5002`
* Run the Flask app when the container starts

---

## 🧪 Step 3: Build and Run the Container

### 🔨 Build the Docker image:

```bash
docker build -t hello-flask .
```

### ▶️ Run the container:

```bash
docker run -d -p 5002:5002 hello-flask
```

### 🌐 Open in browser:

Visit `http://localhost:5002` and you’ll see:

```
Hello, world!
```

---


## ✅ Requirements

* [Docker](https://www.docker.com/)
* Python 3.11+ (only needed if running without Docker)

---


Created as a simple learning project to demonstrate Python + Docker integration.



