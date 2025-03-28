
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

## 2. Installing FastAPI and Uvicorn
FastAPI is a modern web framework for building APIs with Python. Uvicorn is an ASGI web server used to run FastAPI applications.

Run the following command to install them:
```sh
pip install fastapi uvicorn
```

---

## 3. Writing the FastAPI Application
Create a new Python file `main.py` and add the following code:

```python
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
def read_root():
    return {"Name": "Deepanshu", "Location": "Rajasthan"}

@app.get("/{data}")
def read_data(data: str):
    return {"Response": data, "Location": "UttarPardesh"}
```

### Explanation:
- The root endpoint `/` returns a JSON response with a fixed name and location.
- The dynamic endpoint `/{data}` accepts a path parameter and returns it in the response.

---

## 4. Running the FastAPI Application
Run the following command to start the FastAPI server:
```sh
uvicorn main:app --reload --host 0.0.0.0 --port 8000
```

You should now be able to access the API at: 
```
http://127.0.0.1:8000/
```

---

## 5. Adding a Main Execution Block
Modify `main.py` to include a script execution block:

```python
if __name__ == "__main__":
    import uvicorn
    uvicorn.run("main:app", host="0.0.0.0", reload=True, port=80)
```

This allows you to run the application using:
```sh
python main.py
```

---

## 6. Dockerizing the FastAPI Application
To containerize the FastAPI application, we need to create a Dockerfile.

### Dockerfile:
```dockerfile
FROM python:3.9

WORKDIR /app
COPY . /app/

RUN pip install --no-cache-dir -r requirements.txt

EXPOSE 80
CMD ["python", "./main.py"]
```

### Explanation:
- We use the `python:3.9` base image.
- Set `/app` as the working directory.
- Copy all project files into the container.
- Install dependencies using `requirements.txt`.
- Expose port 80.
- Define the command to start the FastAPI application.

---

## 7. Creating a `requirements.txt` File
Ensure your project has a `requirements.txt` file with:
```txt
fastapi
uvicorn
```

This allows dependencies to be installed inside the container.

---

## 8. Building the Docker Image
Run the following command to build the Docker image:
```sh
docker build -t fastapi-app:v1 .
```

After building, verify the created image using:
```sh
docker images
```

---

## 9. Running the Docker Container
Once the image is built, start the container using:
```sh
docker run -p 80:80 fastapi-app:v1
```

Now, you can access your FastAPI application inside the Docker container at:
```
http://127.0.0.1:80/
```

---

## 10. Done.
