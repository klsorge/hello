# hello
A demo application to explore how to build a REST application in SpringBoot. Then 
application will be containerized with [Docker](https://docs.docker.com/) and finally 
deployed to [AWS ECS](https://aws.amazon.com/ecs/)with the help of
[GitHub Actions](https://docs.github.com/en/actions).

## The REST application
The REST application is based on the [Spring Quickstart Guide](https://spring.io/quickstart/).
It is a very simple hello style webapp that has one endpoint '/hello' but uses Spring MVC
and Spring Boot to create the application.

* Build and test with `./gradlew clean build`
* Run the app `./gradlew booRun`

## The CI/CD pipeline
Next we will start a CI/CD pipeline with GitHub Actions. Specifically we will use the
[Publish Java packages with Gradle](https://docs.github.com/en/actions/publishing-packages/publishing-java-packages-with-gradle)
tutorial to build and unit test our demo application on every checkin to the GitHub repository.
If the build is successful the pipeline will publish the artifact to
[GitHub Packages](https://docs.github.com/en/packages).

* Publish to GitHub Packages `./gradlew publish`

## Build and run the Docker application

* Build the container `./gradlew docker`
* Run the container `./gradlew dockerRun`

## Publish and run in ECS