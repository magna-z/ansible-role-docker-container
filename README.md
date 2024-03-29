docker_container
---

Build and run unprivileged docker container.


### Links:
- <https://docs.docker.com/engine/reference/commandline/build/>
- <https://docs.ansible.com/ansible/latest/collections/community/docker/docker_image_module.html>
- <https://docs.docker.com/engine/reference/commandline/run/>
- <https://docs.ansible.com/ansible/latest/collections/community/docker/docker_container_module.html>


### Variables:
- **`docker_container_name`** *(type=string)* - Assign a name to the container.  
  Work as `docker run --name="..."`.
- **`docker_container_image`** *(type=string, mandatory)* - Image name and tag (`latest` if no set).  
  Work as `docker run IMAGE`.

- **`docker_container_network`** *(type=string, default=omit)* - Connect a container to a network.  
  Work as `docker run --network="..."`.
- **`docker_container_publish_ports`** *(type=list, default=omit)* - List of published a container port's to the host with format `"host_port:container_port/proto"`.  
  Work as `docker run --publish="..." --publish="..."`.

- **`docker_container_enviroments`** *(type=object, default=omit)* - Object with struct `{ KEY: value }` for set environment variables.  
  Work as `docker run --env="KEY=value" --env="KEY=value"`.

- **`docker_container_labels`** *(type=object, default=omit)* - Object with struct `{ key: value }` for set meta data on a container.  
  Work as `docker run --label="key=value" --label="key=value"`.

- **`docker_container_entrypoint`** *(type=string, default=omit)* - Overwrite the default `ENTRYPOINT` of the image.  
  Work as `docker run --entrypoint="..."`.
- **`docker_container_command`** *(type=string, default=omit)* - Overwrite the default `CMD` of the image.  
  Work as `docker run ... CMD`.

- **`docker_container_temporary`** *(type=string, default=omit)* - Automatically remove the container when it exits.  
  Work as `docker run --rm ... CMD`.

- **`docker_container_build_path`** *(type=string)* - A build’s context is the set of files located in the specified `PATH`.  
  Work as `docker build PATH`.
- **`docker_container_build_dockerfile_path`** *(type=string, default=omit)* - Path to the Dockerfile.  
  Work as `docker build --file="..."`.
- **`docker_container_build_args`** *(type=object, default=omit)* - Object with struct `{ KEY: value }` for set build-time variables.  
  Work as `docker build --build-arg="KEY=value" --build-arg="KEY=value"`.
- **`docker_container_build_network`** *(type=string, default=omit)* - Set the networking mode for the `RUN` instructions during build.  
  Work as `docker build --network="..."`.
