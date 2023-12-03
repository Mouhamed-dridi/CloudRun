# App Deployment on Google Cloud Run 
Cloud Run is a serverless compute platform offered by Google Cloud

## Easy Deployment

Deploy this app to Google Cloud Run easily by following these steps:

1. **Clone the project:**

    ```bash
    git clone https://github.com/your-username/your-repository.git
    cd your-repository
    ```

2. **Run the deployment command:**

    ```bash
    gcloud run deploy
    ```

## Best Practices

Follow these best practices for a smooth deployment experience:

### 1. Create Artifact Registry

When creating the Artifact Registry, note the registry location and repository name.

### 2. Enable Required APIs

```bash
gcloud services enable \
    sourcerepo.googleapis.com \
    cloudbuild.googleapis.com \
    run.googleapis.com
```

### 3. Enable Docker Authentication
Run the following commands to enable Docker authentication
```
cat ~/.docker/config.json
docker login us-central1-docker.pkg.dev/your-project-id/your-repository
 ```

### 4. Build the Container
Build and submit the container to your Artifact Registry:
``` 
gcloud builds submit --tag us-central1-docker.pkg.dev/your-project-id/your-repository/your-image
 ```

### 5. Access Cloud Run Console
Visit the Cloud Run Console to manage your services.

### 6. Create Cloud Run Service
Create a new Cloud Run service and select the container from the Artifact Registry.
Note: Allow external traffic if you want to test the app from the internet.



Visit the Cloud Run Console to manage your services.
