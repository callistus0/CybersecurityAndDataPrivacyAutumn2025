# 🌐 Using the Phase0 Docker Container

The provided [`docker-compose.yml`](https://raw.githubusercontent.com/vheikkiniemi/CybersecurityAndDataPrivacyAutumn2025/refs/heads/main/BookingSystem/Phase0/docker-compose.yml) runs **one web container**:

```yaml
services:
  web:
    image: vheikkiniemi/cybersec-web-phase0:v1.0
    container_name: cybersec-web-phase0
    restart: always
    ports:
      - "8000:8000"
```

This means your application becomes available at **[http://localhost:8000](http://localhost:8000)**.

---

## ✅ Requirements

Before starting, make sure you have:

### 🐳 Docker installed

* **Windows/macOS** → Docker Desktop
* **Linux** → Docker Engine (you may need `sudo`)
* **Virtual Machine** → Debian-based → Docker Engine (you may need `sudo`)

### 📦 Docker Compose support

**You can use → Debia-based command:**

```bash
sudo docker compose ...
```

**Windows command:**

```powershell
docker compose ...
```

### 🔓 Free port 8000

Make sure no other application uses:

```
http://localhost:8000
```

### 📁 The compose file

Copy the compose file → **Debia-based command:**

```bash
mkdir phase0
cd phase0
wget https://raw.githubusercontent.com/vheikkiniemi/CybersecurityAndDataPrivacyAutumn2025/refs/heads/main/BookingSystem/Phase0/docker-compose.yml
```

Or download the [`docker-compose.yml`](https://github.com/vheikkiniemi/CybersecurityAndDataPrivacyAutumn2025/blob/main/BookingSystem/Phase0/docker-compose.yml) other ways into an empty folder.

---

## 🚀 Start the container for the first time

Open a terminal **in the same folder as the compose file**, then run → **Debia-based command:**

```bash
sudo docker compose up -d
```

**Windows command:**

```powershell
docker compose up -d
```


What happens:

* ⬇️ Docker pulls the image
* 📦 Creates container `cybersec-web-phase0`
* 🔌 Maps port `8000 -> 8000`

Check it is running → **Debia-based command:**

```bash
sudo docker compose ps
```

**Windows command:**

```powershell
docker compose ps
```

---

## 🌍 Open the application

Open your browser and go to:

👉 **[http://localhost:8000](http://localhost:8000)**

If it doesn’t load:

* Check Docker is running
* Check the container list: `docker compose ps` or 
* Check logs (below)

---

## 📜 View container logs

**Show logs once → Debia-based command:**

```bash
sudo docker logs cybersec-web-phase0
```

**Windows command:**

```powershell
docker logs cybersec-web-phase0
```

---

**Follow logs in real time → Debia-based command:**

```bash
sudo docker logs -f cybersec-web-phase0
```

**Windows command:**

```powershell
docker logs -f cybersec-web-phase0
```

(Press **Ctrl + C** to stop)

---

## 🔄 Normal container lifecycle

### 🛑 Stop the container (temporary)

**Debia-based command:**

```bash
sudo docker compose stop
```

**Windows command:**

```powershell
docker compose stop
```

### ▶️ Start it again

**Debia-based command:**

```bash
sudo docker compose start
```

**Windows command:**

```powershell
docker compose start
```

### 🔁 Restart it

**Debia-based command:**

```bash
sudo docker compose restart
```

**Windows command:**

```powershell
docker compose restart
```

---

## 🧪 Optional: Enter the container (for debugging)

**Debia-based command:**

```bash
sudo docker exec -it cybersec-web-phase0 sh
```

**Windows command:**

```powershell
docker exec -it cybersec-web-phase0 sh
```

Exit with:

```bash
exit
```

---

## 🧹 Remove everything when finished

*When the project is over, shut down and remove the container:*

**Stop containers (keep data) → Debia-based command:**

```bash
sudo docker compose down
```

**Windows command:**

```powershell
docker compose down
```

---

**Stop and remove volumes (fresh start) → Debia-based command:**

```bash
sudo docker compose down -v
```

**Windows command:**

```powershell
docker compose down -v
```

---

**Stop and remove images (fresh start) → Debia-based command:**

```bash
sudo docker compose down --rmi local
```

**Windows command:**

```powershell
docker compose down --rmi local
```

---

**These:**

* 🛑 Stops the container
* 🗑️ Removes it (with or without image)
* 🔗 Removes networks

---

# 📌 Quick Student Summary

| Task                    | Command                                        | Emoji |
| ----------------------- | ---------------------------------------------- | ----- |
| Start container         | `docker compose up -d`                         | 🚀    |
| Open app                | [http://localhost:8000](http://localhost:8000) | 🌍    |
| View logs               | `docker logs -f cybersec-web-phase0`           | 📜    |
| Restart                 | `docker compose restart`                       | 🔄    |
| Stop                    | `docker compose stop`                          | 🛑    |
| Remove container        | `docker compose down`                          | 🗑️   |

---