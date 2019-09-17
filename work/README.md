#本次使用的image docker hub位址: https://hub.docker.com/r/jupyter/base-notebook/ 
mkdir mission7
cd mission7
#work資料夾拿來讓container mount
mkdir work
#create a docker-compose.yml file
touch docker-compose.yml
#撰寫yml
version: '3'
services:
  mission7:
    image: jupyter/base-notebook
    container_name: jupyter-notebook
    restart: always
    ports:
      - "8888:8888"
    volumes:
      - ./work:/home/jovyan/work/
    command: start-notebook.sh --NotebookApp.token=''


#use docker compose

docker-compose up -d


