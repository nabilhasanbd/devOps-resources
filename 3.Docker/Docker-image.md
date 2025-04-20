Create a simple Flask App that says "Hello Flask" and build a Docker image of it using only Linux commands.

1. First, update your package manager:
sudo apt update

2. Now install Python and pip
sudo apt install python3 python3-pip -y

3. Check versions
python3 --version
pip3 --version

4. Install Flask
pip3 install flask

5. Create Project Directory and Files
mkdir flask-app
cd flask-app

6. create app.py
nano app.py

7. Paste the code

    from flask import Flask
    app = Flask(__name__)

    @app.route('/')
    def hello():
        return "Hello Flask!"

    if __name__ == "__main__":
        app.run(host='0.0.0.0', port=5000)

8. Create requirements.txt
echo "flask" > requirements.txt

9. Create Dockerfile
nano Dockerfile

10. Paste 

    # Base image with Python
    FROM python:3.9-slim

    # Set working directory inside container
    WORKDIR /app

    # Copy dependency file and install packages
    COPY requirements.txt .
    RUN pip install -r requirements.txt

    # Copy app code into container
    COPY . .

    # Expose port Flask runs on
    EXPOSE 5000

    # Start Flask app
    CMD ["python", "app.py"]

11. Build Docker Image
Make sure Docker is installed and the daemon is running.

docker build -t flask-hello .

12. Visit in Browser
http://localhost:5000

you should see "hello flask"
