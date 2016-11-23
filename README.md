# Fedora Latest Ansible Test Image

[![Docker Automated build](https://img.shields.io/docker/automated/v0rts/docker-fedoraLatest-ansible.svg?maxAge=Latest92000)](https://hub.docker.com/r/v0rts/docker-fedoraLatest-ansible/)

Fedora Latest Docker container for Ansible playbook and role testing.

## How to Build

This image is built on Docker Hub automatically any time the upstream OS container is rebuilt, and any time a commit is made or merged to the `master` branch. But if you need to build the image on your own locally, do the following:

  1. [Install Docker](https://docs.docker.com/engine/installation/).
  2. Clone this repository
      ```shell 
      $ git clone xxxxxx 
      ```
  3. Changed directory into the cloned repository
      ```shell 
      $ cd xxxxxxx
      ```
  4. Execute `docker build` 
      ```shell 
      $ docker build -t fedoraLatest-ansible-custom
      ```

## How to Use

### Pull directly from DockerHub

  1. [Install Docker](https://docs.docker.com/engine/installation/).
  2. Pull image from Docker Hub: 
    ```shell 
      $ docker pull v0rts/docker-fedoraLatest-ansible:latest
    ```
  3. Run a container from the image
    ```shell 
      $ docker run --detach --privileged --volume=/sys/fs/cgroup:/sys/fs/cgroup:ro v0rts/docker-fedoraLatest-ansible:latest /usr/lib/systemd/systemd
    ```
### Image built from locally
  
  1. Pull using tag from build step
    ```shell 
      $ docker pull fedoraLatest-ansible-custom
    ```
  2. Run a container from the image
    ```shell 
      $ docker run --detach --privileged --volume=/sys/fs/cgroup:/sys/fs/cgroup:ro v0rts/docker-fedoraLatest-ansible:latest /usr/lib/systemd/systemd
    ```
## Use Ansible inside the container

    ```shell 
      $ docker exec --tty [container_id] env TERM=xterm ansible-playbook /path/to/ansible/playbook.yml --syntax-check
    ```

## Important Note

This image is for testing purposes only!!

## Author

Created in 2016 by Chad Sailer
