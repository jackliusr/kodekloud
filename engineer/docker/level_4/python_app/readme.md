A python app needed to be Dockerized, and then it needs to be deployed on App Server 1. We have already copied a requirements.txt file (having the app dependencies) under /python_app/src/ directory on App Server 1. Further complete this task as per details mentioned below:



Create a Dockerfile under /python_app directory:

Use any python image as the base image.
Install the dependencies using requirements.txt file.
Expose the port 8085.
Run the server.py script using CMD.

Build an image named nautilus/python-app using this Dockerfile.


Once image is built, create a container named pythonapp_nautilus:

Map port 8085 of the container to the host port 8092.

Once deployed, you can test the app using curl command on App Server 1.


curl http://localhost:8092/