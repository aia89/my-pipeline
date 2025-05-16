
# my-pipeline

Build and Test the Java 

run in cli:

```
./gradlew build
./gradlew clean build
```

>BUILD SUCCESSFUL in 396ms
7 actionable tasks: 7 up-to-date

``` 
./gradlew test
```

>BUILD SUCCESSFUL in 262ms
3 actionable tasks: 3 up-to-date


### Add Helm Chart Structure
Create a Helm chart directory structure:

```
mkdir -p helm-chart/templates
```



Create GitHub Actions Workflow
Create the directory and workflow file:


```
mkdir -p .github/workflows
```

.github/workflows/pipeline.yml      # add GH actions workflow here


Build docker:

```
git:(main) docker build -t hello-world-app .
docker images
REPOSITORY    TAG       IMAGE ID       CREATED         SIZE
hello-world   latest    72b7e32a0196   6 seconds ago   402MB

git:(main) docker tag hello-world yourusername/hello-world:latest
git:(main) docker push aiados/hello-world:latest
```



Test the Pipeline
Commit and push your changes:

Check the Actions tab in your GitHub repository to see the pipeline running.

Verify the Output
After the pipeline runs successfully

Check Docker Hub for your new image

Verify the Helm chart values.yaml was updated with the new image tag

The commit from the pipeline should appear in your git history

Check the image from docker hub


Run CLI for Hello World running every 2 sec
```
docker run aiados/hello-world:latest
```


Check helm

                   
``` 
(base) ➜ git:(main) cat helm-chart/values.yaml | grep -A2 "image:"
```
> image:
  repository: docker.io/aiados/hello-world
  tag: latest



