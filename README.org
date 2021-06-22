# Docker image to Nexus Repository Manager

### Get image from docker, update tag and push to nexus
```bash
export imageTagId="xxxx";
export imageName="xxxx";
export imageVersion="xxxx";
export nexusPath="xxxx";
export nexusPort="xxxx";

# Fetch image from dockerhub
sudo docker pull ${imageName}:${imageVersion}

# View docker images
sudo docker images

# Update tag
sudo docker tag ${tagId} ${nexusPath}:${nexusPort}/${imageName}:${imageVersion}

# Push the image to nexus
sudo docker push ${nexusPath}:${nexusPort}/${imageName}:${imageVersion}
```

### Remove Tag
```bash
sudo docker rmi ${nexusPath}:${nexusPort}/${imageName}:${imageVersion}
```
