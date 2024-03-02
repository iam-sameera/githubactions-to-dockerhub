# GitHub Actions for Building and Pushing Docker Image to Docker Hub

This repository contains GitHub Actions workflows to automatically build a Docker image and push it to Docker Hub whenever changes are pushed to the specified branch.

## Prerequisites

Before you begin, ensure you have the following:

- A GitHub account
- A Docker Hub account


## Setting up GitHub Actions

1. **Fork this repository**: Fork this repository to your GitHub account.

2. **Create Docker Hub Repository**: Create a repository on Docker Hub where you want to push your Docker images.

3. **GitHub Secrets**:

   - Go to your forked repository on GitHub.
   - Navigate to Settings > Secrets.
   - Add the following secrets:
     - `DOCKER_USERNAME`: Your Docker Hub username.
     - `DOCKER_PASSWORD`: Your Docker Hub password or access token. It's recommended to use an access token instead of your password.

4. **Configure Workflow**:

   - In your forked repository, navigate to the `.github/workflows` directory.
   - Edit the `build-and-push.yml` file.
   - Replace `<your_docker_username>/<your_docker_repository>` with your Docker Hub repository name.

5. **Commit Changes**:

   - Commit the changes and push them to your forked repository.
   - GitHub Actions will automatically trigger the workflow defined in `docker-build.yml` whenever changes are pushed to the specified branch.

## Workflow Details

The `docker-build.yml` workflow performs the following steps:

1. **Checkout**: Checks out the repository code.
2. **Build Docker Image**: Builds the Docker image using the Dockerfile in the repository.
3. **Login to Docker Hub**: Logs in to Docker Hub using the provided credentials.
4. **Push Docker Image**: Pushes the built Docker image to the specified Docker Hub repository.

## Notes

- Make sure to replace `<your_docker_username>/<your_docker_repository>` with your actual Docker Hub repository name in the workflow file.
- Ensure that your Dockerfile is present at the root of your repository.
- The workflow can be customized further according to your specific requirements.

## Resources

- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [Docker Hub Documentation](https://docs.docker.com/docker-hub/)
