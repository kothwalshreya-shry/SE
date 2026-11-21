# **Docker Compose — Exam Practical Cheat Sheet**

Follow these steps in the exam

## **STEP 1 — Open Docker Desktop**

1. Open Docker Desktop.
2. Wait until Docker Engine is running.
3. Open Command Prompt.

Check Docker:

```
docker --version
docker compose version
```

## **STEP 2 — Create your project folder**

Type these commands one by one:

```
mkdir SE-Lab
cd SE-Lab
```

## **STEP 3 — Create the YAML file**

```
notepad docker-compose.yml
```

Paste this template and replace the values according to your question.

## **STEP 4 — Write docker-compose.yml**

```

services:
  web:
    image: YOUR_DOCKERHUB_IMAGE
    container_name: web-app
    ports:
      - "8080:8080"
    depends_on:
      - db

  db:
    image: mysql:8
    container_name: mysql-db
    restart: always
    environment:
      MYSQL_ROOT_PASSWORD: root123
      MYSQL_DATABASE: mydb
      MYSQL_USER: user
      MYSQL_PASSWORD: pass123
    ports:
      - "3307:3306"
    volumes:
      - mysql_data:/var/lib/mysql

volumes:
  mysql_data:

```

Save using **Ctrl + S**, then close Notepad.

### **What should you replace?**

| YAML value             | What to enter                          |
| ---------------------- | -------------------------------------- |
| `YOUR_DOCKERHUB_IMAGE` | Image specified in question            |
| `8080:8080`            | Host port : application container port |
| `root123`              | MySQL root password                    |
| `mydb`                 | Database name                          |
| `user`                 | MySQL username                         |
| `pass123`              | MySQL password                         |
| `3307:3306`            | Host port : MySQL container port       |

If the question specifies different values, use those instead.

## **STEP 5 — Validate the YAML file**

```
docker compose config
```

Expected: Docker displays the parsed configuration without errors.

## **STEP 6 — Start containers**

```
docker compose up -d
```

Expected: Images are pulled if needed, containers are created and services start.

## **STEP 7 — Verify containers**

```
docker compose ps
```

Expected: Both web and database services should show Up/Running.

If not running:

```
docker compose logs
```

## **STEP 8 — Verify application**

Open browser and enter:

```
http://localhost:8080
```

Use the actual host port from your YAML.

[Exploring Microsoft Radius Application Platform - The New Stack](https://images.openai.com/static-rsc-4/TVh8NxOjrWasvQG3Ae95i_dL5bEu1nzCiftb6WYyr_LjVr4xiLzAtNVMkOMzC6ltoVuIbgWdRjISZ7WqIkfxo7zjjKHoeRP3LtK6wQOdnmlLpvhqERsg61q_SmMtQ8oMgSVNPldOcUffitxZS8h-BHqaUXWQmQKL24qPYpJdOz0?purpose=inline)

For your Nginx practice image, you should see the Nginx welcome page. For the actual exam image, the expected application page may differ.

## **STEP 9 — Scenario questions**

Memorise these five answers:

| Scenario                          | Command                       |
| --------------------------------- | ----------------------------- |
| Temporarily stop all services     | `docker compose stop`         |
| Start the same stopped containers | `docker compose start`        |
| Remove containers and network     | `docker compose down`         |
| Apply updated YAML configuration  | `docker compose up -d`        |
| Stop only backend                 | `docker compose stop backend` |

## **STEP 10 — After completing the practical**

If the examiner asks you to clean up:

```
docker compose down
```

This removes containers and the default network. Named volumes remain.
