# Docker-All-Command

Here’s a comprehensive guide to Docker commands, starting from basic to advanced:

### Basic Commands

1. **Install Docker**  
   On Linux:
   ```bash
   sudo apt-get update
   sudo apt-get install docker-ce docker-ce-cli containerd.io
   ```

2. **Check Docker Version**  
   ```bash
   docker --version
   ```

3. **Run a Container**  
   ```bash
   docker run <image_name>
   ```
   Example:
   ```bash
   docker run hello-world
   ```

4. **List Docker Images**  
   ```bash
   docker images
   ```

5. **Pull an Image**  
   ```bash
   docker pull <image_name>
   ```
   Example:
   ```bash
   docker pull ubuntu
   ```

6. **List Running Containers**  
   ```bash
   docker ps
   ```

7. **List All Containers (Including Stopped)**  
   ```bash
   docker ps -a
   ```

8. **Stop a Running Container**  
   ```bash
   docker stop <container_id>
   ```

9. **Start a Stopped Container**  
   ```bash
   docker start <container_id>
   ```

10. **Remove a Container**  
    ```bash
    docker rm <container_id>
    ```

11. **Remove an Image**  
    ```bash
    docker rmi <image_name>
    ```

12. **Run a Container in the Background (-d flag)**  
    ```bash
    docker run -d <image_name>
    ```

13. **Run a Command in a Running Container**  
    ```bash
    docker exec -it <container_id> <command>
    ```
    Example:
    ```bash
    docker exec -it <container_id> bash
    ```

### Intermediate Commands

1. **Build an Image from a Dockerfile**  
   ```bash
   docker build -t <image_name> <path_to_dockerfile>
   ```

2. **Tag an Image**  
   ```bash
   docker tag <image_id> <repository_name>:<tag>
   ```

3. **Push an Image to Docker Hub**  
   ```bash
   docker push <repository_name>:<tag>
   ```

4. **Inspect a Container**  
   ```bash
   docker inspect <container_id>
   ```

5. **Logs from a Container**  
   ```bash
   docker logs <container_id>
   ```

6. **Stop All Running Containers**  
   ```bash
   docker stop $(docker ps -q)
   ```

7. **Remove All Stopped Containers**  
   ```bash
   docker rm $(docker ps -a -q)
   ```

8. **Remove All Images**  
   ```bash
   docker rmi $(docker images -q)
   ```

9. **View Container Stats (like `top` for containers)**  
   ```bash
   docker stats
   ```

10. **Create a Docker Volume**  
    ```bash
    docker volume create <volume_name>
    ```

11. **Run a Container with a Volume**  
    ```bash
    docker run -v <volume_name>:/path/in/container <image_name>
    ```

12. **View Docker Networks**  
    ```bash
    docker network ls
    ```

13. **Create a Custom Network**  
    ```bash
    docker network create <network_name>
    ```

14. **Run Container on a Custom Network**  
    ```bash
    docker run --network <network_name> <image_name>
    ```

### Advanced Commands

1. **Docker Compose Up (Start Services Defined in `docker-compose.yml`)**  
   ```bash
   docker-compose up
   ```

2. **Docker Compose Down (Stop Services Defined in `docker-compose.yml`)**  
   ```bash
   docker-compose down
   ```

3. **Commit Changes in a Container to a New Image**  
   ```bash
   docker commit <container_id> <new_image_name>
   ```

4. **Run a Container with Port Mapping**  
   ```bash
   docker run -p <host_port>:<container_port> <image_name>
   ```

5. **Use Environment Variables in a Container**  
   ```bash
   docker run -e <env_variable>=<value> <image_name>
   ```

6. **Limit Container Memory and CPU Usage**  
   ```bash
   docker run -m <memory_limit> --cpus <cpu_limit> <image_name>
   ```
   Example:
   ```bash
   docker run -m 500m --cpus 1 ubuntu
   ```

7. **Backup a Container’s Data**  
   ```bash
   docker export <container_id> > <file_name>.tar
   ```

8. **Restore a Container from Backup**  
   ```bash
   docker import <file_name>.tar
   ```

9. **Create a Docker Swarm**  
   ```bash
   docker swarm init
   ```

10. **List Services in a Swarm**  
    ```bash
    docker service ls
    ```

11. **Scale Services in a Swarm**  
    ```bash
    docker service scale <service_name>=<num_of_replicas>
    ```

12. **Docker Prune (Clean Up Unused Containers, Networks, Images, etc.)**  
    ```bash
    docker system prune
    ```

13. **Docker Save (Save an Image to a .tar File)**  
    ```bash
    docker save -o <path_to_save>.tar <image_name>
    ```

14. **Docker Load (Load an Image from a .tar File)**  
    ```bash
    docker load -i <path_to_tar>.tar
    ```

15. **Monitor Events**  
    ```bash
    docker events
    ```

16. **Connect a Running Container to a Network**  
    ```bash
    docker network connect <network_name> <container_id>
    ```

17. **Inspect Volume Details**  
    ```bash
    docker volume inspect <volume_name>
    ```

### Docker Compose Basic Commands

1. **Start Services in the Background**  
   ```bash
   docker-compose up -d
   ```

2. **Stop and Remove Containers, Networks, Volumes**  
   ```bash
   docker-compose down --volumes
   ```

3. **Scale Services**  
   ```bash
   docker-compose scale <service_name>=<num_of_containers>
   ```

By using these commands, you can handle most Docker-related tasks from container management to advanced service scaling and orchestration.
