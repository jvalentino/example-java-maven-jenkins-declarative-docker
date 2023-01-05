# Building Java with Maven using a Jenkins Declarative Pipeline running on a Docker-based Build Agent

This project is used to demonstrate that:

1. The build agent of https://github.com/jvalentino/jenkins-agent-maven (Docker Hub as `jvalentino2/jenkins-agent-maven`) works
2. The Jenkins project of https://github.com/jvalentino/example-jenkins-docker-jcasc-2 is able to run this pipeline on the build agent

The basis of this project is https://github.com/jvalentino/example-java-maven-lib-4, which had a Jenkinsfile added referencing the agent of `maven` that is then setup as a Docker Build agent mapping to `jvalentino2/jenkins-agent-maven`.

