# **Quick Start Guide — Booking System Containers (Phase 1 / Part 2)**

---

## 1. Requirements 🚀

* Docker + Docker Compose installed
* You have already completed **Phase 1 / Part 1**, which created project

  * 📦 `cybersec-phase1-part1`
* You now download [`docker-compose.yml`](https://github.com/vheikkiniemi/CybersecurityAndDataPrivacyAutumn2025/blob/main/BookingSystem/Phase1/Part2/docker-compose.yml) for **Phase 1 / Part 2** into its own folder, which will create

  * 📦 `cybersec-phase1-part2`

---

## 2. Start Phase 1 / Part 2 ▶️

In the folder where the **Phase 1 / Part 2** `docker-compose.yml` is stored:

```bash
docker compose up -d
```

This starts:

* 🗄️ `cybersec-db-phase1-part2` (PostgreSQL database)
* 🌐 `cybersec-web-phase1-part2` (web application)

---

## 3. Access the application 🌍

* Open browser:  

  `cybersec-phase1-part1` 👉  `http://localhost:8000`  
  `cybersec-phase1-part2` 👉  `http://localhost:8001`

---

* PostgreSQL from host:  

  `cybersec-phase1-part1` 👉 
    ```bash
    docker exec -it cybersec-db-phase1-part1 psql -U postgres -d postgres
    ```
  `cybersec-phase1-part2` 👉 
    ```bash
    docker exec -it cybersec-db-phase1-part2 psql -U postgres -d postgres
    ```
---

## 4. Check that both projects exist 🔍

### In Docker Desktop

1. Open **Docker Desktop**
2. Go to **Containers** tab
3. You should see two Compose projects:

   * `cybersec-phase1-part1` (from earlier part)
   * `cybersec-phase1-part2` (this new one)

Each project will have its own containers listed under it.

---

### From command line

```bash
docker compose ls
```

You should see **both** names in the list:

```text
NAME                      STATUS
cybersec-phase1-part1     ...
cybersec-phase1-part2     ...
```

---

## 5. View logs 🧾

All services (in current project folder):

```bash
docker compose logs -f
```

Single service:

```bash
docker compose logs -f web
docker compose logs -f database
```

---

## 6. Stop and clean up 🧹

Stop containers (keep data):

```bash
docker compose down
```

Stop containers **and delete database data** (Phase 1 / Part 2 only):

```bash
docker compose down -v
```

Use `-v` only if you are OK with **losing all PostgreSQL data** for this project.
