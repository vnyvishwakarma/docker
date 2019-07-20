The goal of this example is to show you how to get a Node.js application into a Docker container. The guide is intended for development, and not for a production deployment. The guide also assumes you have a working Docker installation and a basic understanding of how a Node.js application is structured.


###Building your image

Go to the directory that has your Dockerfile and run the following command to build the Docker image. The -t flag lets you tag your image so it's easier to find later using the docker images command:

####$ docker build -t <your username>/node-web-app .

Your image will now be listed by Docker:

$ docker images

# Example
REPOSITORY                      TAG        ID              CREATED
node                            10         1934b0b038d1    5 days ago
<your username>/node-web-app    latest     d64d3505b0d2    1 minute ago

###Run the image
Running your image with -d runs the container in detached mode, leaving the container running in the background. The -p flag redirects a public port to a private port inside the container. Run the image you previously built:

$ docker run -p 49160:8080 -d <your username>/node-web-app