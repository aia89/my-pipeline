
# my-pipeline

Build and Test:
###run in cli:


```./gradlew build```

>BUILD SUCCESSFUL in 396ms
7 actionable tasks: 7 up-to-date

``` ./gradlew test```

>BUILD SUCCESSFUL in 262ms
3 actionable tasks: 3 up-to-date


###Add Helm Chart Structure
Create a Helm chart directory structure:

```
mkdir -p helm-chart/templates
```

helm-chart/templates/deployment.yaml:

###Create GitHub Actions Workflow
Create the directory and workflow file:


```mkdir -p .github/workflows```

.github/workflows/pipeline.yml:

###Set Up Secrets in GitHub
add these secrets to your GitHub repository:


```DOCKER_HUB_USERNAME - Your Docker Hub username```

```DOCKER_HUB_TOKEN - Your Docker Hub access token ```

###Test the Pipeline
Commit and push your changes:

Check the Actions tab in your GitHub repository to see the pipeline running.

###Verify the Output
After the pipeline runs successfully:

Check Docker Hub for your new image

Verify the Helm chart values.yaml was updated with the new image tag

The commit from the pipeline should appear in your git history

###Check the image from docker hub


###Run CLI
```docker run aiados/hello-world:latest```


###Check helm

                   
``` (base) ➜ git:(main) cat helm-chart/values.yaml | grep -A2 "image:"```
> image:
  repository: docker.io/aiados/hello-world
  tag: latest

