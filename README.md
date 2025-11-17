<div style="display: flex; align-items: center; gap: 10px;">
  <img src="https://skillicons.dev/icons?i=linux" style="height: 40px;"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/apache/apache-original.svg" style="height: 40px;"/>
  <img src="https://skillicons.dev/icons?i=mysql,php,prometheus,grafana,docker" style="height: 40px;"/>  
</div>

## Dockerized LAMP Stack with Prometheus & Grafana Monitoring     

A containerized LAMP (Linux, Apache, MySQL, PHP) application deployed using Docker Compose, integrated with Prometheus and Grafana for real-time performance monitoring and metrics visualization.

![Readme Card](https://github-readme-stats.vercel.app/api/pin/?username=mirakib&repo=dockerize-lamp-monitoring-stack)

## Features

- **LAMP Stack** (Linux, Apache, MySQL, PHP) for a CRUD web app  
- **Prometheus** for collecting metrics  
- **Grafana** for visualization dashboards  
- **Exporters** for Apache, MySQL, and Node metrics  
- Fully containerized and network-isolated  
- Easy to extend or deploy on any Docker host  


## Architecture
```
[ Apache (PHP App) ] → [ Apache Exporter ] ┐

[ MySQL Database ] → [ MySQL Exporter ] ├──> [ Prometheus ] → [ Grafana ]

[ Host System ] → [ Node Exporter ] ┘
```

## Project Structure

```
.
├── apache
│   ├── 000-default.conf
│   ├── Dockerfile
│   └── index.php
├── compose.yml
├── mysql
│   └── init-exporter.sql
├── mysqld-exporter
├── prometheus
│   └── prometheus.yml
└── README.md
```
## Setup Instructions

1. **Clone the Repository**  
   ```bash
   git clone https://github.com/mirakib/dockerize-lamp-monitoring-stack.git
   ```
2. **Navigate to the Project Directory**  
   ```bash
   cd dockerize-lamp-monitoring-stack
   ```
3. **Build and Start the Containers**  
   ```bash
   docker compose up -d --build
   ```  
4. **Access the Application and Dashboards**  
   - LAMP App: `http://localhost:8080`
   - Prometheus: `http://localhost:9090`
   - Grafana: `http://localhost:3000` 
  
5. **Clean Up**  
   To stop and remove all containers, run:  
   ```bash
   docker compose down
   ```