# 🐋 Docker Commands for RAG Implementation

A comprehensive guide for managing your Ollama Mistral Docker container.

---

## 📋 Configuration Variables

```bash
IMAGE_NAME=ollama-mistral-img
CONTAINER_NAME=ollama-mistral-offline
PORT=127.0.0.1:11434:11434
```

---

## 🚀 Quick Start Guide

1. **Build the image:**
   ```bash
   docker build -f dockerfile -t ollama-mistral-img .
   ```

2. **Run the container:**
   ```bash
   docker run -d --rm --name ollama-mistral-offline -p 127.0.0.1:11434:11434 ollama-mistral-img
   ```

3. **Test the connection:**
   ```bash
   curl http://127.0.0.1:11434/api/tags
   ```

---

## 🔧 Core Commands

### 🏗️ BUILD - Build the Docker image

```bash
docker build -f dockerfile -t ollama-mistral-img .
```

> Run this first to create the Docker image from your Dockerfile.

---

### ▶️ RUN (GPU) - Start with GPU support

```bash
docker run -d --rm --gpus all --name ollama-mistral-offline -p 127.0.0.1:11434:11434 ollama-mistral-img
```

> Starts the container with NVIDIA GPU acceleration enabled.

---

### ▶️ RUN (CPU) - Start with CPU only

```bash
docker run -d --rm --name ollama-mistral-offline -p 127.0.0.1:11434:11434 ollama-mistral-img
```

> Starts the container using CPU only (no GPU required).

---

### ⏹️ STOP - Stop the running container

```bash
docker stop ollama-mistral-offline
```

> Gracefully stops the running container.

---

## 📊 Monitoring & Debugging

### 📝 LOGS - View container logs

```bash
docker logs -f ollama-mistral-offline
```

> Follow the container logs in real-time. Press `Ctrl+C` to exit.

---

### ✅ STATUS - Check container status

```bash
docker ps --filter "name=ollama-mistral-offline"
```

> Verify if the container is currently running.

---

### 💻 SHELL - Access container shell

```bash
docker exec -it ollama-mistral-offline /bin/bash
```

> Open an interactive bash shell inside the container for troubleshooting.

---

## 🧪 Testing

### 🔍 TEST - Verify Ollama is responding

```bash
curl http://127.0.0.1:11434/api/tags
```

> Tests the API endpoint to ensure Ollama is ready to accept requests.

---

### 📦 MODELS - List available models

```bash
docker exec ollama-mistral-offline ollama list
```

> Shows all models currently available in the container.

---

## 🧹 Cleanup

### 🗑️ CLEAN - Complete cleanup

```bash
docker stop ollama-mistral-offline 2>$null
docker rm ollama-mistral-offline 2>$null
docker rmi ollama-mistral-img 2>$null
```

> Stops the container, removes it, and deletes the image. Errors are suppressed.

---

## 💡 Tips

- 🎯 Always build the image before running the container
- 🔌 Ensure port `11434` is not already in use
- 🖥️ Use GPU version for better performance if available
- 📊 Monitor logs regularly to catch issues early
- 🔄 Container uses `--rm` flag, so it auto-removes when stopped

---

## 📚 Additional Resources

- [Docker Documentation](https://docs.docker.com/)
- [Ollama Documentation](https://ollama.ai/docs)
- PowerShell compatible commands included

---

*Generated for IS640 RAG Project*
