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
