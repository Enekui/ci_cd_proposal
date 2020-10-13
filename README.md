# Basic code for a sample CI/CD solutino for a basic Ruby microservices-application.

### Infra model
![infra model](simple_ci_cd.png)

## This is composed of a few simple steps

* Dev upload code to Github
* Jenkins/GitOps, etc. will start the build process including some testing
* Images is built and pushed to Docker image registry
* Image is then deployed to Kubernetes

## Now let's elaborate a little bit on why?

1. Why kubernetes and not just Docker-Compose linking all the microservices?
> Because I want to break down all the complexity of this infra into automation.
> My idea is to let everything defined as code, with specific instructions for k8s
> in a way that the application can be autonomous, self-scaling, self-healing, etc.
> It also provides me with the total control of the application infra, avoiding my to rely on 
> a third party for administration, support, and quick actions.
> There are many other reasons, but I am trying to be brief.

2. Will everything is defined as code in a repository?
> Yes, my main idea is to define the k8s cluster infra as code using Terraform.
> My goal is to have an infrastructure defined in such a way, that everything
> can be deployed by clicking on a button and everything can come back to the previous state.
> This can be easily achieved with a combination of three tools: Terraform, Ansible, and Helm.
> We will dive deeper into this as the project is being shaped.

3. Should we use cloud or OnPrem?
> Well, this is something that I can't answer right away, since this needs to be reviewed with you
> but I would like to have this k8s cluster as a service, DigitalOcean could be a great candidate.
> The thing is that if I am gonna be the only one managing and supporting this infra, I want to delegate
> most of the platform administration in some cloud provider.

4. Why is it not a monitoring system in the diagram?
> Well, since this needs to be review with you, I will add a more detailed 
> architecture after this very talk.
> We need to agree if we want to use a fully open-sourced solution or a paid solution with good extra features.
> I will come back to this point as I get more inside of the applications.

5. How much time can take to have this up & running.
> This a good and critical point, but it will depend on the bureaucracy of the company.
> I could have something like this ready in a couple of weeks if no unexpected issues come around.

## In a nutshell

* Define all infra as code
* Perform testing
* Deploy the infra
* Automate the application deployment
* Perform testing
* Deploy the application to k8s
* Setup monitoring solution
* Sharpen alerting and monitoring system

## What I need from you?

> The good thing with kubernetes is that it can run almost anything, no matter which application, language, etc.
> But to get the most of this architecture, I will need to have more inside of this application.

* Application performance requerements.
* Networking architecture of the microservices.
* Storage requirements
* Security concerns
* Microservices isolation
* And a few more points that will come along as I get more inside of the app
