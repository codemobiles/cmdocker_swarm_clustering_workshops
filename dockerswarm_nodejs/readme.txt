- create app.js
- npm init -y
- npm i express
- test with "node app.js"

# Create Image
- create image with ""
- docker build -t cmnode:1.0 .

# Create Docker Container (Standalone)
- docker run -d -p 91:91 --name nodeswarm cmnode:1.0
- curl http://localhost:91


# Create Docker Swarm as Cluster
- docker swarm init
- docker service create --replicas 3 --name cmswarm --publish 91:91 cmnode:1.0

Help:
docker images
docker rmi <image_id>
docker ps 
docker rm <container_id>
docker service ls
docker service rm <service_id>