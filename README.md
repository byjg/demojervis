## Hello World! (WAR-style)

This project adds a Dockerfile and the .jervis.yml necessary for build the project using the CI platform

### Build

```bash
docker run -it --rm --name my-maven-project \
    -v "$(pwd)":/usr/src/mymaven \
    -v "$(pwd)/.m2":/root/.m2 \
    -w /usr/src/mymaven \
maven:3.3-jdk-8 mvn install
```
