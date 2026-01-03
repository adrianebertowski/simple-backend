Prerequisites
Before you embark on this journey, make sure you have the following:

Docker installed on your machine.
Basic understanding of Python.
Curiosity and enthusiasm for learning new things!
Installation and Usage
Clone the Magical Repository:

git clone https://github.com/milistu/simple-backend.git
cd simple-backend
Build Docker image:

docker build -t simple-backend .
Check if port 1000 is in use:

On Linux and macOS:

sudo lsof -i :1000
On Windows:

netstat -ano | findstr :1000
If you get output from these commands, it means something is running on port 1000. The output will typically include the process ID (PID) of the process using the port.

In my case my 1000 port is free.

Note: If your port 1000 is not available you can change the Dockerfile and replace 1000 with your available port OR simply set PORT variable when running Docker Container!

Run container:

Note: set different PORT if needed.

docker run --rm -it -e PORT=1000 -p 127.0.0.1:1000:1000 simple-backend
Test our server:

You can test the server through backend-test.ipynb notebook or with Swagger.

Swagger:

Open the link in the browser

http://0.0.0.0:1000/docs
Go to Authorize and input your username and password to get the required token.
In our example username:

username=johndoe
password=BestPassword!
Now you can test one of the end-points (eg. image, audio, text).
