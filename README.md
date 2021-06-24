# Docker image to Nexus Repository Manager

### Get image from docker, update tag and push to nexus
```bash
export imageTagId="xxxx";
export imageName="xxxx";
export imageVersion="xxxx";
export nexusPath="xxxx";
export nexusPort="xxxx";
export serverName="xxxx";

# Fetch image from dockerhub
sudo docker pull ${imageName}:${imageVersion}

# View docker images
sudo docker images

# Update tag
sudo docker tag ${tagId} ${nexusPath}:${nexusPort}/${imageName}:${imageVersion}

# Push the image to nexus
sudo docker push ${nexusPath}:${nexusPort}/${imageName}:${imageVersion}
```

### Remove tag
```bash
sudo docker rmi ${nexusPath}:${nexusPort}/${imageName}:${imageVersion}
```

# Migrate Docker image from one server to another with ssh
```bash
docker save ${nexusPath}:${nexusPort} | ssh ${serverName} 'docker load'
