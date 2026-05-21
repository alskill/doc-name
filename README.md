# Step 1 – Check Existing Volumes
```bash
docker volume ls
```
Why this command is used
Lists all Docker volumes available in the system.
Helps verify whether a volume already exists.
# Step 2 – Create a Docker Volume
```bash 
docker volume create vol1
```
Why this command is used
Creates a persistent storage volume named vol1.
Data inside the volume remains even if containers are deleted.
# Step 3 – Run Nginx Container with Attached Volume
```bash
docker run -d -p 1020:80 --name cont1 -v vol1:/usr/share/nginx/html nginx
```
# Step 4 – Check Running Containers
```bash
docker ps
```
# Step 5 – Check Downloaded Images
```bash
docker images
```
# Step 6 – Enter Inside the Container
```bash
docker exec -it cont1 /bin/bash
```
# Step 7 – Verify Web Directory
```bash
cd /usr/share/nginx/html
```
```bash
ls
```
Why this command is used
Checks files and folders inside the Nginx web root directory.

# Step 8 – Remove Default Website Files
```bash
rm -rf *
```
# Step 9 – Install Vim Editor
```bash
apt update
```
```bash
apt install vim -y
```
# Step 10 – Create HTML Website File
```bash
vim index.html
```
Example HTML Code
```bash

<html>
<head>
<title>Docker Volume Lab</title>
</head>

<body bgcolor="orange">

<h1 align="center">
Docker Volume Successfully Attached
</h1>

<p align="center">
Website hosted using Docker Volume
</p>

</body>
</html>

```
# Step 11 – Create Multiple Files
```bash
touch file{1..10}
```
# Step 12 – Verify Files
```bash
ls
```
You should see:

index.html
file1 to file10

# Step 13 – Exit Container
```bash
exit
```
# Step 14 – Launch Second Container Using Same 
```bash
docker run -d -p 1030:80 --name cont2 -v vol1:/usr/share/nginx/html nginx
```
# Step 15 – Enter Second Container
```bash
docker exec -it cont2 /bin/bash
```
# Step 16 – Verify Shared Files
```bash
cd /usr/share/nginx/html
```
```bash
ls
```
# Step 17 – Access Hosted Website

Open browser:
```bash
http://localhost:1020
```
or
```bash
http://<EC2-Public-IP>:1020
```

Docker Hub Image Tagging
# Step 18 – Tag Docker Image
```bash
docker tag <local-image-name> <dockerhub-username>/<image-name>:<tag>
```
# Step 19 – Login to Docker Hub
```bash
docker login
```
# Step 20 – Push Image to Docker Hub
```bash
docker push <dockerhub-username>/<image-name>:<tag>
```
Uploads Docker image to Docker Hub repository.
Image can later be pulled from anywhere.

# Final Understanding

Docker Volume Advantages
Persistent storage
Data survives container deletion
Multiple containers can share same data
Best for websites, databases, logs, and application files

# Important Point

If data is stored only inside container:
Data is lost when container is removed.
If data is stored in volume:
Data remains safe and reusable.
















