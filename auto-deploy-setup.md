# DROPLET SETUP
#### General instructions to setup a bare-bones automated CI/CD pipeline.

## Step 1. User Script
  https://github.com/jirishus/automated-setups/blob/master/Ubuntu-18.04/initial_server_setup.sh

## Step 2. Install Nginx
  https://www.digitalocean.com/community/tutorials/how-to-install-nginx-on-ubuntu-22-04

## Step 3. Setup Server Blocks
  Refer to document above

## Step 4. Setup Docker / Docker-Compose
  ## Install docker and docker compose
  ```
  sudo apt update
  sudo apt install -y docker.io docker-compose
  ```

  #### Enable Docker
  ```
  sudo systemctl enable docker
  sudo systemctl start docker
  ```

  #### Add user to docker group
  ```
  sudo usermod -aG docker sammy
  ```

  #### Exit server and ssh back to run:
  ```
  docker ps
  ```

  ## Step 5. Update Nginx Proxy Pass
  > Update /etc/nginx/sites-available/yourdomain.com

  ```
  restart nginx: sudo systemctl nginx restart
  ```


# REPO SETUP
  ## Step 1. Create Files:
  ```
  touch Dockerfile docker-compose.yml .github/workflows/deploy.yml
  ```
  
  ## Step 2. Create Actions Secrets

