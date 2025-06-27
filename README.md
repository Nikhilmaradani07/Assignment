
Docker-Compose file link : https://github.com/Nikhilmaradani07/Assignment.git

# DevOps Intern Assignment: Nginx Reverse Proxy + Docker

A Dockerized microservices setup with:
- A **Go backend** (service_1)
- A **Python Flask backend** (service_2)
- An **Nginx reverse proxy** routing traffic to each service via `/service1` and `/service2`
- All services orchestrated using **Docker Compose**

---

## 🧰 Technologies Used

| Tool/Service     | Purpose |
|------------------|---------|
| Docker           | Containerization of all services |
| Docker Compose   | Multi-container orchestration |
| Nginx            | Reverse proxy with path-based routing |
| Go               | Backend service 1 |
| Python + Flask   | Backend service 2 |
| EC2 Instance     | Deployment environment |


---

## 🔁 Routing Logic

| Route             | Target Service      | Example Response |
|------------------|---------------------|------------------|
| `/service1/ping` | Go Service          | `{ "status": "ok", "service": "1" }` |
| `/service2/ping` | Python Service      | `{ "status": "ok", "service": "2" }` |
| `/service1/hello`| Go Service          | `{ "message": "Hello from Service 1" }` |
| `/service2/hello`| Python Service      | `{ "message": "Hello from Service 2" }` |
| `/health`        | Static response     | `OK` (no logging) |

---

## 🚀 How to Run Locally or on EC2

### Prerequisites

- Docker & Docker Compose installed
- Port `8080` open (for EC2 security group)


curl http://localhost:8080/service1/ping
curl http://localhost:8080/service2/ping
curl http://localhost:8080/health
