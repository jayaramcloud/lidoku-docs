# Docker Documentation for lidoku-turbo

This guide will help you set up and run the project using Docker.

## Prerequisites

**Docker**: Install Docker if not already available. Check Docker's official documentation for installation instructions.

---

### 1. Building the Docker Image

To build the Docker image, navigate to the project’s root directory (where
the `Dockerfile` is located) and run the following command:

```bash
docker build -t [image-name]:[tag] .
```

#### Example

```bash
docker build -t myapp:latest .
```

This command will:

- Use the `Dockerfile` in the root directory.
- Tag the image with the specified name and version.

---

### 2. Running the Docker Container

To run the Docker container, use the following command:

```bash
docker run -p [host-port]:[container-port] [image-name]:[tag]
```

#### Example 2

```bash
docker run -p 3000:3000 myapp:latest
```

This command:

- Maps `host-port` to `container-port` (replace as needed).
- Runs the container in the foreground.

#### Optional Flags

- `-d`: Run the container in detached mode.
- `--env-file`: Use this option to specify an environment file for configuring
  container variables. In this project, a sample environment file, `.env.example`
  , is located in the root directory. To get started, copy this file to `.env`
  and update it with your configuration values.

#### Example with `env` file

```bash
docker run --env-file .env -p [host-port]:[container-port] [image-name]:[tag]
```

---

### 3. Accessing the Application

Once the container is running, access the application at `http://localhost:[host-port]`

---

### 4. Managing Docker Containers

#### List Running Containers

```bash
docker ps
```

#### Stop a Container

```bash
docker stop [container-id]
```

#### Remove a Container

```bash
docker rm [container-id]
```

#### Remove an Image

```bash
docker rmi [image-name]:[tag]
```

---

### 5. Common Issues and Troubleshooting

- **Port Conflicts:** If you encounter an error about ports already in use, make
  sure the host port you are mapping to is available or change it.
- **Permissions Errors:** If there are issues with file permissions, check if
  volume mounts have appropriate permissions for Docker.
