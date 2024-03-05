There is a requirement to Dockerize a Node app and to deploy the same on App Server 2. Under /node_app directory on App Server 2, we have already placed a package.json file that describes the app dependencies and server.js file that defines a web app framework.


Am3ric@
Create a Dockerfile (name is case sensitive) under /node_app directory:

Use any node image as the base image.
Install the dependencies using package.json file.
Use server.js in the CMD.
Expose port 3002.

The build image should be named as nautilus/node-web-app.


Now run a container named nodeapp_nautilus using this image.

Map the container port 3002 with the host port 8091.

. Once deployed, you can test the app using a curl command on App Server 2:



curl http://localhost:8091