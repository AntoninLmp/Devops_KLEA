# Continuous Integration and Continuous Deployment Experimentation 🚀

Welcome to our CI/CD project named KLEA ! 

## Project Objectives 💻

1. **Automated CI/CD Pipeline Setup**
2. **Enhanced Development Speed and Reliability**
3. **Monitoring Stack Implementation**
 
## Team Collaboration 👨🏻‍👨🏻‍👦🏻‍👦🏻

Our group of 4 is composed of : 
 - Kylian Sauvee
 - Léo Mercier
 - Enzo PeudePiece
 - Antonin Lampin

## Rapport 📄

Explore the project documentation for detailed instructions. Let's work together to enhance our understanding of CI/CD practices and improve software development processes.

```
https://docs.google.com/document/d/1KWgJo2rP_GpqPEL3z3x_VOVbeXd-5-i4JiBwfAdyk9M/edit?usp=sharing
```

# How to run localy

Spawn Jenkins locally
```
docker run -p 8081:8080 -v jenkins_home:/var/jenkins_home --name my-jenkins-container -e JENKINS_JAVA_OPTS="-Djenkins.install.runSetupWizard=false" -e JENKINS_OPTS="--prefix=/jenkins" jenkins/jenkins:lts
```

Go to `http://localhost:8081/jenkins`
Install docker kubernetes pipeline and git plugins

Create the pipeline

Create a slave node called 'slave' with websocket enabled

Create agent to connect to the node
```
java -jar agent.jar -jnlpUrl http://localhost:8081/jenkins/computer/slave/jenkins-agent.jnlp -workDir "C:\Users\Utilisateur\Downloads\jenkins"
```

Run agent
```
java -jar C:\Users\Utilisateur\Downloads\jenkins\agent.jar -jnlpUrl http://localhost:8081/jenkins/computer/slave/jenkins-agent.jnlp -workDir "C:\Users\Utilisateur\Downloads\jenkins"
```

Go to `http://localhost:8081/jenkins/scriptApproval/` and add `method groovy.lang.GroovyObject invokeMethod java.lang.String java.lang.Object` to the `Signatures already approved`

