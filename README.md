# Infra

Sample container infrastructure.

## Getting started

Once you've cloned the repository, please run the following command.
```shell
git submodule update --init --recursive
```

To launch the applications stack run the following shell script.
```shell
docker compose up; docker compose down
```

## Diagram

```mermaid
C4Context
  Person(user, "User", "People that interact with the system")

  Container_Boundary(c1, "Cluster") {
    Container(console, "Console", "python", "Web application representing console")
    Container(worker, "Worker", "C++", "Service executing task")
    Container(monitor, "Monitor", "python", "Web application representing monitor")
  }

  Rel(user, console, "Uses", "https")
  Rel(user, monitor, "Uses", "https")
  Rel(console, worker, "Commands", "tcp")
  Rel(worker, monitor, "Notifies", "tcp")
```

## Links

[Docker Desktop](https://www.docker.com/products/docker-desktop/)

[Rancher Desktop](https://rancherdesktop.io/)

[Lazydocker](https://github.com/jesseduffield/lazydocker)

[Docker Compose](https://docs.docker.com/compose/)
