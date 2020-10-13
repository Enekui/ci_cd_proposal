# Basic code for a sample CI/CD solutino for a basic Ruby microservices-application.

### Infra model
![infra model](simple_ci_cd.png)

## This is composed by a few simple steps

* Dev upload code to Github
* Jenkins/GitOps, etc. will start the build process including some testing
* Images is build and pushed to Docker image repository
* Image is then deployed to Kubernetes

## Now let's elaborate a little bit on why?

1. Why kubernetes and not just Docker-Compose linking all the microservices?
> Because I want to breack down all the complecity of this infra into automation.
> My idea is to let everything defined as code, with specific instructions for k8s
> in a way that the application can be autonomus, self-scaling, self-healing, etc.
> It also provides me with the total control of the appllication infra, avoiding my to rely on 
> a third party for adminsitration, support and quick actions.

2. 
