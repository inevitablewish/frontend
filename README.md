##Project Phase 2

In the second phase we will create CI/CD pipeline that builds the container from image and push it to the dockerhub through Jenkins pipeline. This is to be done for both frontent and backend.

Build the docker using following command

<docker buildx build -t backend:first> . # where first represents the image tag
  
Then run the container based upon the image created in first step  
 <docker run -it --name backend -p 8080:8080 backend:first>

Run the jenkins pipeline for both front end and backend

   #Project Phase3
   In this phase of the project, we will use images pushed to dockerhub in phase2 to create K8s Menifest to deploy application. The application will fetch the latest image updated through Jenkins pipelines and use it to create deployments/replicas/pods etc. 
