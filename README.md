# 🌤️ Weather-App

A 'Microservices-based weather application built using Go, Node.js, Python and MySQL, containerized with Docker and orchestrated using Kubernetes.

---

## 🧩 Project Structure

```
WeatherApp/
├── auth/                    # Go-based Auth microservice
│   ├── main/
│   ├── .dockerignore
│   ├── Dockerfile
│   ├── go.mod / go.sum
│
├── Kubernetes/Auth/        # K8s deployment files for services
│   ├── MySQL/
│   ├── UI/
│   ├── Weather/
│   ├── deployment.yml
│   └── service.yml
│
├── mysql-init/
│   └── init.sql            # MySQL schema/init script
│
├── UI/                     # Node.js (likely React or Express) frontend
│   ├── public/
│   ├── app.js
│   ├── package.json
│   ├── .gitignore
│   └── .dockerignore
│
├── weather/                # Go-based Weather service
│   ├── Dockerfile
│   ├── main.py
│   └── requirements.txt

└── README.md
```

---

## 🚀 Features

- **Authentication Service**: Built in Go with database-backed user auth.
- **Weather Service**: Retrieves and processes weather data.
- **UI**: Frontend UI to interact with the services.
- **Database**: MySQL used to store user and app data.
- **Dockerized**: Each component is containerized using Docker.
- **Kubernetes**: Deployable on a Kubernetes cluster for scalability.

---

## 🛠️ Tech Stack

- **Languages**: Go, Node.js, Python
- **Frontend**: Node.js (Express or React assumed)
- **Database**: MySQL
- **Containerization**: Docker
- **Orchestration**: Kubernetes

---

## 📦 Setup Instructions

1. **Clone the repo:**

   ```bash
   git clone https://github.com/Khaled1771/Weather-App.git
   cd Weather-App
   ```


3. **Deploy with Kubernetes:**

   ```bash
   kubectl apply -f Kubernetes/Auth/MySQL/statefulset.yml
   kubectl apply -f Kubernetes/Auth/MySQL/headless-service.yml
   kubectl apply -f Kubernetes/Auth/MySQL/init-job.yml

   kubectl apply -f Kubernetes/Auth/deployment.yml
   kubectl apply -f Kubernetes/Auth/service.yml

   kubectl apply -f Kubernetes/Auth/UI/deployment.yml
   kubectl apply -f Kubernetes/Auth/UI/service.yml
   kubectl apply -f Kubernetes/Auth/UI/ingress.yml

   kubectl apply -f Kubernetes/Auth/Weather/deployment.yml
   kubectl apply -f Kubernetes/Auth/Weather/service.yml
   ```

5. **Edit your local DNS conifuration:**

    ```bash
    sudo /etc/hosts

    127.0.0.1 weatherapp.com
    ```

6. **Access the UI:**

   Open your browser and go to `http://localhost:<port>`

---

## 🧪 Testing

- Postman collections or curl scripts can be added here.

