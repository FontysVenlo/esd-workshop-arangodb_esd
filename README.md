Setup

To run the workshop, you only need Docker installed.

Open your terminal or command prompt.

Run the following command to start the database container:

docker run --pull=always --publish=8560:8529 --env ARANGO_ROOT_PASSWORD=12345 --detach --name arangoDBContainer arangodb:latest


Once the container is running, open your browser and go to:
http://localhost:8560/

You’re ready to start using ArangoDB for the workshop!
