```markdown
# Python Socket Programming Docker Project

This project demonstrates a simple socket programming example using Python, containerized with Docker.

## Table of Contents
- [Overview](#overview)
- [Requirements](#requirements)
- [How to Run](#how-to-run)
- [Usage](#usage)
- [Dockerfile Explanation](#dockerfile-explanation)
- [Code Structure](#code-structure)
- [Troubleshooting](#troubleshooting)

## Overview

This project showcases a basic socket server-client communication using Python's socket library. It uses Docker to containerize the application, allowing for easy deployment and scaling.

The server listens on port 9999 and accepts connections from clients. When a client connects, it sends a welcome message and some sample data.

## Requirements

- Docker installed on your machine
- Python 3.x

## How to Run

1. Clone the repository:
   ```
   git clone https://github.com/BeratDM/docker-python-socket.git
   cd docker-python-socket
   ```

2. Build the Docker image:
   ```
   docker build -t python-socket .
   ```

3. Run the container:
   ```
   docker run -p 9999:9999 python-socket
   ```

## Usage

1. Open a terminal and connect to the server:
   ```
   telnet localhost 9999
   ```

2. You should see the welcome message followed by some sample data.

3. To disconnect, type Ctrl+], then Ctrl+] again.

## Dockerfile Explanation

The Dockerfile uses the official Python slim image as the base. It installs pip requirements, copies the application code, and sets up a non-root user.

Key points:
- Uses Python slim image for smaller footprint
- Installs pip requirements from requirements.txt
- Sets up a non-root user for security
- Copies application code into the container
- Runs the main.py script

## Code Structure

The project consists of two main files:

1. `main.py`: Contains the socket server implementation
2. `Dockerfile`: Defines the Docker build instructions

## Troubleshooting

- If the server doesn't start, check the logs:
  ```
  docker logs <container_id>
  ```

- If you encounter connection issues, verify that port 9999 is not already in use:
  ```
  sudo netstat -tuln | grep 9999
  ```

This README provides a basic overview of the project, its setup, and usage instructions. It also includes a brief explanation of the Dockerfile and code structure.