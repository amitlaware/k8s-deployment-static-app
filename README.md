# 🚀 Deploy Static Web App on Kubernetes Cluster

---

## 🛠 Technologies Used

- HTML, CSS  
- Docker  
- Kubernetes  
- GKE (Google Kubernetes Engine)  
- GCR (Google Container Registry)  

![HTML](https://img.icons8.com/color/48/html-5--v1.png)
![CSS](https://img.icons8.com/color/48/css3.png)
![Docker](https://img.icons8.com/color/48/docker.png)
![Kubernetes](https://img.icons8.com/color/48/kubernetes.png)
![Google Cloud](https://img.icons8.com/color/48/google-cloud.png)

---
## Prerequistes
  .Create Docker file for your static app in your project folder
---

## 📋 Steps
-[x] Create Kubernetes cluster on GCP
-[x] Configure GCP console with following commands
```export PROJECT_ID=PROJECT_ID```
```gcloud config set project PROJECT_ID```
-[x] Clone github repository of static app to GCP console
```git clone <GITHUB_REPO_LINK>```
```cd <REPO_NAME```

-[X]Read Docker file of Static app
```cat Docker```

-[x] Create docker Image 
```docker build -t static-app:v1 .```

-[x] Run Docker Image
```docker run --rm -p 5173:5173 static-app:v1```

-[x] Configures Docker to authenticate with Google Artifact Registry
```gcloud auth configure-docker asia-central1-docker.pkg.dev```

-[x] This command tags the local Docker image with a new name so it can be pushed to Google Container Registry (GCR) under the project <PROJECT_ID> with the repository name static-app.
```docker tag static-app:v1 gcr.io/<PROJECT_ID>/static-app```

-[X] Push the Docker Image to Google Container Registry.
```docker push gcr.io/<PROJECT_ID>/static-app```

-[x] Connect local machine to GKE cluster
```gcloud container  clusters get-credentials <CLUSTER_NAME> --zone=<ZONE>```


