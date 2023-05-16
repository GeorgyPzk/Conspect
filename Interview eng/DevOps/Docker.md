# Difference between docker run and docker create

The main difference between these commands is that `docker create` will create the container in a stopped state.

# Namespaces in Docker

Namespaces are needed to provide an isolated workspace called a container. When you start a container, Docker creates a set of namespaces for that container. These namespaces organize the isolation layer.

# Docker Swarm

Docker Swarm is the standard container orchestrator available if Docker itself is installed.

The cluster consists of __Manager Node__ and __Worker__

отличие от K*S?
