## Integrate Docker Hub with GitHub via token
- **Generate token** Go to Docker Hub - > Under Account Setting -> Settings - > Personal access tokens
GitHub
  - Keep the Username of Docker hub and token
- Go to GitHub Repository ->  Settings -> Secrets and variables -> Actions -> New repository secret
- Type DOCKERHUB_USERNAME - add the password of github account in order to update the token integrated
- Type DOCKERHUB_TOKEN
- Type DOCKERHUB_USERNAME
- Docker DOCKERHUB_TOKEN
- Click "Add secret".

  - Create folder .github Repository or create it automaticlly under Action Tab
  - Create the yaml workflow for example ./github/build-image.yaml
  - For Example **Hello World based on app-js **
