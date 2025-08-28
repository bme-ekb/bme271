# Python Setup


1. Get [Docker Desktop](https://docs.docker.com/get-started/introduction/get-docker-desktop/)

Note: after you install, it will try to get you to log in and create an account, you don't need to do this. You can click **Skip** in the top right corner instead.
 
2. create a folder/directory where you'll store your python code for the class.
3. Create a file called `docker-compose.yml` in that directory and paste the content below (or click here and save/download this file direct to your directory <https://raw.githubusercontent.com/bme-ekb/bme271/refs/heads/main/docker-compose.yml>)

```yaml
services:
  jupyter:
    image: quay.io/jupyter/datascience-notebook:2025-03-14
    ports:
      - "8888:8888"
    volumes:
      - ./:/home/jovyan/work
    environment:
      JUPYTER_TOKEN: "bmeekb"
    restart: "unless-stopped"
```

Note: You can create a .yml with Notepad (Windows) or VS Code.
   
3. open a Terminal
4. change directory to where you're going to keep your code `cd path/to/your/python/code`
5. `docker compose up -d`
6. load your Jupyter Lab <http://localhost:8888/?token=bmeekb>
