# Unofficial teach-back script — Docker

**Illustrative 8–10 minute rehearsal only; actual assessment instructions override this example.**

**Objective:** Explain the difference between a Docker image and a container, and run a simple local example.

**Hook:** “An app can work on a developer laptop but fail on a different server. Container images help package the runtime and dependencies consistently.”

**Concept:** “A Dockerfile contains build instructions; an image is the reusable package; a container is an instance created from an image.”

**Demo:** Ensure Docker Engine or Docker Desktop is running, then execute:

```bash
docker --version
docker pull nginx:alpine
docker images
docker run --name mct-demo -d -p 8080:80 nginx:alpine
docker ps
curl http://localhost:8080
docker stop mct-demo
docker rm mct-demo
```

**Narration:** “We pulled an image; `docker run` created and started an Nginx container. Port 8080 on the host maps to port 80 inside it. We stopped and removed the container.”

**Knowledge check:** “Does deleting the container automatically delete its image?” Answer: No; the image remains.

**Wrap-up:** “Image = packaged blueprint. Container = its instance. Try starting a second container with a different host port.”

If the port is in use, choose another. Pre-pull the image in a rehearsal so network delays don't interrupt.
