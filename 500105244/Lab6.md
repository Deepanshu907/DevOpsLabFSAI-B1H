
# DevOps Lab 6

## Name: Deepanshu Kumar Jindal  
**SAP ID:** 500105244  
**Roll Number:** R2142220475  
**Batch:** Full Stack AI B1 Hons  

---

# Git FastAPI - Dockerization  

## 1. Setting up the Development Environment
```sh
sudo apt update -y
sudo apt install python3 python3-pip pipenv -y
```

---


## Install FastAPI and Uvicorn
```bash
pipenv install fastapi uvicorn
```

## Write a FastAPI Application
Create a Python file `main.py` and add the following code:

```python
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
def read_root():
    return {"Name": "Docker", "Location": "Dehradun"}

@app.get("/{data}")
def read_data(data: str):
    return {"hi": data, "Location": "Dehradun"}

if __name__ == "__main__":
    import uvicorn
    uvicorn.run("main:app", host="0.0.0.0", reload=True, port=80)
```

## Run the FastAPI Application
```bash
python main.py
```

## Create a Dockerfile
Create a file named `Dockerfile` and add the following content:

```Dockerfile
FROM ubuntu

RUN apt update -y \
    && apt install -y python3 python3-pip pipenv

WORKDIR /app
COPY . /app/
RUN pipenv install -r requirements.txt

EXPOSE 80
CMD pipenv run python3 ./main.py
```

## Create a `requirements.txt` File
```text
uvicorn
fastapi
```

## Build the Docker Image
```bash
docker build -t test02 .
```

## Run the Docker Image
```bash
docker run -p 80:80 test02:latest
```

## Install Docker on Linux
```bash
sudo apt update -y
sudo apt install -y docker.io
sudo systemctl start docker
sudo systemctl enable docker
```

## Verify Docker Installation
```bash
docker --version
```

## Install Docker Desktop on Linux
Download and install Docker Desktop:
```bash
wget https://desktop.docker.com/windows/main/amd64/docker-desktop-<latest-version>-amd64.deb
sudo dpkg -i docker-desktop-<latest-version>-amd64.deb
```

Start Docker Desktop:
```bash
docker-desktop
```

Ensure your user is added to the Docker group to avoid permission issues:
```bash
sudo usermod -aG docker $USER
newgrp docker
```

## Verify Docker Desktop
```bash
docker info
```

This completes **DevOps Lab 6** on fastapi and dockerize.

