# Inception

# Project Overview
Inception is a system administration and virtualization project at 42 that introduces Docker and container orchestration.
The goal is to set up a multi-container environment using Docker Compose, following best security practices and ensuring 
scalability.

# Technologies Used
- **Docker:** Containerization
- **Docker Compose:** Multi-container management
- **NGINX:** Reverse proxy and web server
- **WordPress:** CMS for the website
- **MariaDB:** Database engine
- **Redis:** Cache system
- **PHP-FPM:** Optimized PHP execution

# Satus:

Result : 
ft_irc - 100%✅


# Project Structure

📦 inception
|---📁 srcs
|   |---📁 requirements
|   |   |---📁 nginx
|   |   |---📁 wordpress
|   |   |---📁 mariadb
|   |   |---📁 tools
|   |   |--- .env
|   |   |--- .gitignore
|   |   |--- docker-compose.yml
|--- Makefile
|--- README.md


# Instalation & Setup

1️⃣ ## Clone the Repository
`git clone git@github.com:benanredzhebov/inception.git`
`cd inception`

2️⃣ ## Configure Environment Variables
Modify the `.env` file to set up database credentials, WordPress settings, and domain names.

3️⃣ ## Buld and Run Containers
`docker-compose up --build -d`

4️⃣ ## Access the Services
  - **Wordpress:** http://your-domain.com

5️⃣ ## Stop and Clean Up
`docker-compose down -v`

# Key Features
- Secure and isolated multi-container environment
- Persistent data storage with Docker volumes
- SSL/TLS encryption
- Customizable environment via `.env` file
- Efficient resource usage with lightweight containers
