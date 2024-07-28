### LM Studio: Detailed Notes

#### Overview

LM Studio is a comprehensive development environment tailored for working with large language models (LLMs). It offers a range of tools and features to facilitate the training, evaluation, and deployment of LLMs, making it a versatile platform for both researchers and practitioners.

#### Key Features

- **Integrated Development Environment (IDE)**: Provides a rich development environment specifically designed for LLM tasks, including code editing, debugging, and model management.
- **Model Training**: Supports training of LLMs with various configurations and hyperparameters, offering tools for managing datasets, training progress, and performance metrics.
- **Evaluation Tools**: Includes functionalities for evaluating model performance, including benchmarking, metrics calculation, and visualization of results.
- **Deployment**: Facilitates the deployment of trained models to various platforms, including local servers, cloud services, and APIs.
- **Visualization**: Offers visualization tools for analyzing model behavior, training progress, and evaluation metrics.
- **Data Management**: Provides features for managing datasets, including loading, preprocessing, and splitting data.
- **Customization**: Allows customization of training scripts, evaluation criteria, and deployment settings.

#### Installation

##### Quick Start with Docker (Recommended)

**Single-User Mode**:
To disable login for a single-user setup, set `LM_STUDIO_AUTH` to `False`. This will bypass the login page. Note that you cannot switch between single-user mode and multi-account mode after this change.

**Data Storage in Docker**:
When using Docker to install LM Studio, include the `-v lm-studio:/app/data` in your Docker command to ensure your database is properly mounted and prevent any loss of data.

**Default Configuration**

- **If using a local setup**:
  ```bash
  docker run -d -p 4000:8080 --add-host=host.docker.internal:host-gateway -v lm-studio:/app/data --name lm-studio --restart always ghcr.io/lm-studio/lm-studio:main
  ```

- **If connecting to a remote server**:
  ```bash
  docker run -d -p 4000:8080 -e REMOTE_SERVER_URL=https://example.com -v lm-studio:/app/data --name lm-studio --restart always ghcr.io/lm-studio/lm-studio:main
  ```

**With Nvidia GPU Support**:
```bash
docker run -d -p 4000:8080 --gpus all --add-host=host.docker.internal:host-gateway -v lm-studio:/app/data --name lm-studio --restart always ghcr.io/lm-studio/lm-studio:cuda
```

**Using API Key**:
```bash
docker run -d -p 4000:8080 -e API_KEY=your_secret_key -v lm-studio:/app/data --name lm-studio --restart always ghcr.io/lm-studio/lm-studio:main
```

#### Installing LM Studio with Bundled Support

**With GPU Support**:
```bash
docker run -d -p 4000:8080 --gpus=all -v lm-studio:/app/data --name lm-studio --restart always ghcr.io/lm-studio/lm-studio:gpu
```

**For CPU Only**:
```bash
docker run -d -p 4000:8080 -v lm-studio:/app/data --name lm-studio --restart always ghcr.io/lm-studio/lm-studio:cpu
```

After installation, access LM Studio at `http://localhost:4000`.

#### Using the Dev Branch

**Note**: The `:dev` branch contains the latest unstable features and changes. Use it at your own risk as it may have bugs or incomplete features.
```bash
docker run -d -p 4000:8080 -v lm-studio:/app/data --name lm-studio --restart always ghcr.io/lm-studio/lm-studio:dev
```

#### Manual Installation

##### Installation with pip (Beta)

**Python 3.11 is required.**

1. **Install LM Studio**:
   ```bash
   pip install lm-studio
   ```

2. **Start LM Studio**:
   ```bash
   lm-studio serve
   ```

Access LM Studio at `http://localhost:8080`.

#### Other Installation Methods

LM Studio offers various installation alternatives, including non-Docker native installation methods, Docker Compose, Kubernetes, and Helm. Visit the LM Studio Documentation or join the community for comprehensive guidance.

#### Troubleshooting

If you encounter issues like "LM Studio: Server Connection Error," refer to the TROUBLESHOOTING section or seek help from the LM Studio community.

#### Updating

To update your local Docker installation to the latest version:
```bash
docker run --rm --volume /var/run/docker.sock:/var/run/docker.sock containrrr/watchtower --run-once lm-studio
```
Replace `lm-studio` with your container name if it is different.

#### Conclusion

Follow the full getting started guide to explore all features and settings of LM Studio. Enjoy developing and deploying your large language models! 😄
