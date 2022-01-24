# TIAToolbox-Docker
Docker Official Image packaging for [TIAToolbox](https://github.com/TissueImageAnalytics/tiatoolbox).

1. Navigate to the Dockerfile that you want to use, based on the Python version and Operating System that you prefer

2. Build the Docker image
```bash
docker build -t <image_name> .       
```

3. Deploy the image as a Docker container
```bash
docker run -it --rm --name <container_name> <image_name>     
```
