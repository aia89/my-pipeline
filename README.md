
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

```
DOCKER_HUB_USERNAME - Your Docker Hub username

DOCKER_HUB_TOKEN - Your Docker Hub access token```

###Test the Pipeline
Commit and push your changes:

Check the Actions tab in your GitHub repository to see the pipeline running.

###Verify the Output
After the pipeline runs successfully:

Check Docker Hub for your new image

Verify the Helm chart values.yaml was updated with the new image tag

The commit from the pipeline should appear in your git history

###check the image

![img width="831" alt="Screenshot 2025-05-16 at 5 04 38 PM" src="https://github.com/user-attachments/assets/b3e7f083-3e92-41de-a380-b8e49810e04c" ]

###Run CLI
docker run aiados/hello-world:latest
![img width="763" alt="Screenshot 2025-05-16 at 5 13 34 PM" src="https://github.com/user-attachments/assets/80fbebbc-81be-4635-8060-8188a492ed62" ]


###check helm

                   
```(base) ➜  Platform-Engineering-Challenges---Pipelining git:(main) cat helm-chart/values.yaml | grep -A2 "image:"
image:
  repository: docker.io/aiados/hello-world
  tag: latest```



