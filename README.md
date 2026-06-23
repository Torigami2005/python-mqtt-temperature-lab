# Python MQTT Temperature Monitoring System 
This project is a Dockerized Python MQTT laboratory exercise. 
## Components - Eclipse Mosquitto MQTT broker - Python temperature sensor publisher - Python temperature subscriber 

## New added: JSON messages parsing
This delivers JSON parsing towards the terminal via Docker container. This will show data both from Python message and JSON messages.

## Alternative for Buffered python execution in Docker.
Correct me if I'm wrong. Though, this code will work after you 
```bash
docker compose up --build 
```
in the terminal but it takes longer because python codes are buffering in the print statements. That's why the sensor and subscriber messages took so long. To fix that, put "-u" in both sensor and subriber folder in the Dockerfile like this in temperature_sensor: CMD ["python", "-u","temperature_sensor.py"] and temperature_subscriber: CMD ["python", "-u","temperature_subscriber.py"]. That will show that the "-u" in Python stands for unbuffered. That way, it will print all the messages quickly rather than you wait for several minutes. Either way, it works with or without it.


## Run 
```bash 
docker compose up --build 
``` 
## Stop 
```bash 
docker compose down 
``` 
