# Configuring Docker Daemon (Snap-installed) on Ubuntu

This guide explains how to configure the Docker daemon when Docker is installed via Snap on Ubuntu.

## 1. Locate the Config File

Docker's configuration file (for Snap installation) is located at:

```/var/snap/docker/current/config/daemon.json```

## 2. Edit the Config File

Use your preferred text editor. For example:

```bash
sudo nano /var/snap/docker/current/config/daemon.json```

To enable TCP access on port 2375 (insecure), you can add the following:

```json
{ 
	"hosts": ["tcp://0.0.0.0:2375", 
	"unix:///var/run/docker.sock"] 
} ```

## 3. Restart Docker After saving your changes, restart the Docker service:

```bash 
sudo snap restart docker ```
