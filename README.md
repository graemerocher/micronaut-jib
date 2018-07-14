# Containerize a [Micronaut](http://micronaut.io/) app with [Jib](https://github.com/GoogleContainerTools/jib)

This is an example of how to easily build a Docker image for a [Micronaut framework Groovy/Java application](http://guides.micronaut.io/creating-your-first-micronaut-app-groovy/guide/index.html) with Jib.

Read more about Jib at the [official blog post](https://cloudplatform.googleblog.com/2018/07/introducing-jib-build-java-docker-images-better.html).

<!-- Dockerize "Hello World" @Java @micronautfw app with #Jib in 2 seconds -->
<p align="center">
    <a href="https://twitter.com/intent/tweet?text=Dockerize%20%22Hello%20World%22%20%40java%20%40micronautfw%20app%20with%20%23Jib%20in%202%20seconds&url=https://asciinema.org/a/191805&hashtags=docker,kubernetes">
    <img src="https://github.com/coollog/micronaut-jib/blob/master/dockerize-micronaut-jib.gif?raw=true" width="600" alt="Dockerize Micronaut app with Jib">
  </a>
</p>

## Quickstart

### With Docker

```shell
./gradlew jibDockerBuild

docker run -d -p 8080:8080 micronaut-jib:0.1
```
```shell
curl localhost:8080/hello
> Hello World
```

<!-- Dockerize "Hello World" @java @micronautfw app with #Jib in 2 seconds -->
Give it a [![Tweet](https://img.shields.io/twitter/url/http/shields.io.svg?style=social)](https://twitter.com/intent/tweet?text=Dockerize%20%22Hello%20World%22%20%40java%20%40micronautfw%20app%20with%20%23Jib%20in%202%20seconds&url=https://github.com/coollog/micronaut-jib&hashtags=docker,kubernetes)

### With Kubernetes

```shell
IMAGE=<your image, eg. gcr.io/my-project/micronaut-jib>

./gradlew jib --image=$IMAGE

kubectl run micronaut-jib --image=$IMAGE --port=8080 --restart=Never

# Wait until pod is running
kubectl port-forward micronaut-jib 8080 > /dev/null 2>&1 &
```
```shell
curl localhost:8080/hello
> Hello World
```

<!-- "Hello World" @java @micronautfw app on #Kubernetes with #Jib -->
Give it a [![Tweet](https://img.shields.io/twitter/url/http/shields.io.svg?style=social)](https://twitter.com/intent/tweet?text=%22Hello%20World%22%20%40java%20%40micronautfw%20app%20on%20Kubernetes%20with%20%23Jib%20in%202%20seconds&url=https://github.com/coollog/micronaut-jib&hashtags=docker,kubernetes)

## More information

Learn [more about Jib](https://github.com/GoogleContainerTools/jib).
Learn [more about Micronaut](https://micronaut.io).
