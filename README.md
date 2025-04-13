# 🚦 Traffic Light Docker Challenge

Este proyecto consiste en desplegar tres aplicaciones Node.js (`red`, `yellow`, `green`) utilizando contenedores Docker, conectados mediante una red interna y gestionados por un servidor Nginx que actúa como proxy inverso y también como balanceador de carga.

---

## 📁 Estructura del proyecto

```
trafficlight-docker-challenge/
├── red/
├── yellow/
├── green/
├── nginx/
│   ├── proxy/
│   │   └── default.conf
│   └── loadbalancer/
│       └── default.conf
├── docker-compose.proxy.yml
├── docker-compose.loadbalancer.yml
└── README.md
```

---

## 🧪 Requisitos

- Docker
- Docker Compose

---

## ▶️ Parte 1: Proxy inverso con Nginx

Esta parte expone las 3 aplicaciones web en diferentes puertos:

- `http://localhost:3000` → red-app
- `http://localhost:4000` → yellow-app
- `http://localhost:5000` → green-app

### 🧱 Para ejecutar:

```bash
docker compose -f docker-compose.proxy.yml up --build -d
```

### 🧼 Para detener:

```bash
docker compose -f docker-compose.proxy.yml down
```

---

## 🔁 Parte 2: Balanceador de carga con Nginx

En esta versión, Nginx actúa como balanceador de carga. Todas las apps están detrás del puerto `3000`, y se muestran alternadamente en cada petición.

### 🧱 Para ejecutar:

```bash
docker compose -f docker-compose.loadbalancer.yml up --build -d
```

### 🧼 Para detener:

```bash
docker compose -f docker-compose.loadbalancer.yml down
```

---

## 👨‍🏫 Entrega

Este repositorio incluye:

- `Dockerfile` para cada app
- Configuraciones de Nginx (proxy y balanceador)
- 2 archivos `docker-compose` para levantar cada versión del reto

La corrección se puede hacer ejecutando directamente los archivos:

```bash
docker compose -f docker-compose.proxy.yml up -d
docker compose -f docker-compose.loadbalancer.yml up -d
```

---

## 📅 Autor

- Joan Merino Serrano
