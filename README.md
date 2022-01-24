# TIAToolbox-Docker
Docker Official Image packaging for [TIAToolbox](https://github.com/TissueImageAnalytics/tiatoolbox).

1. Navigate to the Dockerfile that you want to use, based on the Python version and Operating System that you prefer

2. Build the Docker image
```bash
docker build -t <IMAGE_NAME> .       
```

3. Check that the image has been created
```bash
docker images 
```

4. Deploy the image as a Docker container
```bash
docker run -it --rm --name <CONTAINER_NAME> <IMAGE_NAME>     
```

5. Connect to the running container
```bash
docker exec -it <CONTAINER_NAME> bash
```

To add your own script and run it through the Docker container, first copy your script into the docker environment and then execute it.
```bash
COPY /path/to/<script>.py .
CMD ["python3", "<script>.py"]
```