user_name:admin
password:admin123

# to install docker
sudo apt install docker.io

# to install docker-compose
sudo apt install docker-compose

# Rebuild and restart services
docker-compose up --build -d

# Stop all services
docker-compose down -v

# View logs
docker logs -f airfare-backend
docker logs -f airfare-frontend

# Check DB health
docker exec -it airfare-db pg_isready -U user


# Jenkins Setup
# Update VM
sudo apt update && sudo apt upgrade -y

# Install Java (required for Jenkins)
sudo apt install openjdk-11-jdk -y
java -version

# Add Jenkins repository key
curl -fsSL https://pkg.jenkins.io/debian/jenkins.io.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null

# Add Jenkins repository
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null

# Install Jenkins
sudo apt update
sudo apt install jenkins -y

# Start and enable Jenkins service
sudo systemctl start jenkins
sudo systemctl enable jenkins
sudo systemctl status jenkins

# Access Jenkins Web UI
# Open browser: http://<VM-IP>:8080
# username and password
  saikumar
  saikumar
