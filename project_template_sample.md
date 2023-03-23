>> This is a sample Octernships project for your inspiration.

>> A Tl;DR is including the readme with information and starter code in a single repository. Every applied student gets a copy of this repository with write access where they submit the Octernships Task.

>> Please enable discussions for your Octernship project repository so students can ask project relevant questions via GitHub Discussions

# Octernship Information
*Your Logo Here*

### Company information 
*Use this section to share information about your company such as founding information, mission statement, product description, product success, etc*

### Why participate in an Octernship with GitHub
*Use this section to appeal to students. Consider sharing information about recent projects, the technology stack, the type of mentorship students can expect, listing future employment opportunities, etc.*

### Octernship role description

We're looking for a DevOps Intern who have experience with Kubernetes or are passionate to learn Kubernetes and work in a Cloud Native DevOps environment. 

| Octernship info  | Timelines and Stipend |
| ------------- | ------------- |
| Assignment Deadline  | 26 March 2023  |
| Octernship Duration  | 3 Months  |
| Monthly Stipend  | $700 USD  |

### Recommended qualifications
*Use this section to describe what skills a student might need to complete the problem statement on GitHub Classroom*

- Experience with Git & GitHub
- Experience with networking and basic Linux commands
- Passion to learn Kubernetes
- Writing modern JavaScript/Node.js
- Passion for open source & Cloud Native Technology

### Eligibility
To participate, you must be:
* A [verified student](https://education.github.com/discount_requests/pack_application) on Global Campus
* 18 years or older
* Active contributor on GitHub (monthly)

# Assignment - Expose Kubernetes pod 

The following steps will help you setup and reproduce Kubernetes in your machine. 👇🏻

The starter code is included in this repository. ‼️

## Setting up 🖥️
1. Install [Git](https://git-scm.com/)
2. Install [Node](https://nodejs.org/en/download/)
3. Install [Docker Desktop](https://www.docker.com/products/docker-desktop/)
4. Create an account on [Docker Hub](https://hub.docker.com/)
   1. Login to Docker Desktop with your docker account 
   2. Login to Docker CLI `docker login` ([more info](https://docs.docker.com/engine/reference/commandline/login/))
5. Clone this repo 
   1. https: `https://github.com/ashwinexe/GHW-December.git`
   2. ssh: `git@github.com:ashwinexe/GHW-December.git`
   
## Conterize your app 🚀
1. Check out the `Dockerfile` to understand what's happening
2. Login to your docker account in your shell `docker login`
3. Run `docker build -t <docker_username>/<image_name>:<version_number> .`
4. It shoudl look like this:
```
   ➜  GHW-December git:(main) ✗ docker build -t ashwinexe/ghw:1.0 .
Sending build context to Docker daemon  9.639MB
Step 1/6 : FROM node:current-slim
 ---> b131f467b9ea
Step 2/6 : LABEL MAINTAINER="kumarashwin2603@gmail.com"
 ---> Running in ad644f733bb0
Removing intermediate container ad644f733bb0
 ---> 80536b85f226
Step 3/6 : COPY . /src
 ---> a0d5b1092b14
Step 4/6 : RUN cd /src; npm install
 ---> Running in 69961af002d6

up to date, audited 97 packages in 5s

12 packages are looking for funding
  run `npm fund` for details
Successfully built 1f2bfa5b0245
Successfully tagged ashwinexe/ghw:1.0
```

>> Notice the "." in the end is crucial, it tells docker that all the files in the local directory get compressed and sent to the Docker daemon.

5. Run your docker image with port exposed:
   1. `docker run -p 8080:8080 ashwinexe/ghw:1.0`
   2. Check localhost:8080 in your browser

>> Fact:  8080:8080 means any request coming for port 8080 will be forwarded to service running on port 8080 inside your container. simply put  
 `docker run -p Port for Outside World: Actual Port of service in container ashwinexe/ghw:1.0`

6. Push  your image to dockerhub `docker push <username>/<image>:<version>` 
   1. for eg: in my case it'd be `docker pull ashwinexe/ghw:1.0`

You can use my deployed version if you wish so: `docker pull ashiwnexe/ghw:1.0`

## Enable Kuberenetes 🕹️
There are several ways to run kubernetes locally on your machine. `Docker Desktop` is the easier way to get started 

>> Still curious? Check out Kind, minikube and kubeadm which are also popular choice to run kubernetes locally

- Run Docker Desktop -> Settings -> Kubernetes -> Toggle `Enable Kubernetes` -> Check Kubernetes status at the bottom
   
![](https://i.imgur.com/oDYxGti.png)

- Open command terminal and run `kubectl get nodes` your output should look like:
```
kubectl get nodes
NAME             STATUS   ROLES           AGE     VERSION
docker-desktop   Ready    control-plane   5d11h   v1.25.2
```

Hurray! You got your own Kubernetes cluster running! 🥳

*So you containerized a Node.js web application into a container image and stored it on Docker Hub. You're about to deploy that application to your cluster inside a Kubernetes Pod.*

## Configure Kubenetes 
- `kubectl apply -f pod.yaml` //applies Pod configuration
- `kubectl apply -f service-local.yaml` //applies Service configuration to expose port locally
- Verify service
```
  $ kubectl get svc
NAME         TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)          AGE
kubernetes   ClusterIP   10.96.0.1       <none>        443/TCP          9d
svc-local    NodePort    10.96.122.250   <none>        8080:30000/TCP   7h33m
```
  Check the output at **localhost:30000** (or where NodePort is exposed in your `service-local.yaml` file)

---

## Task instructions
*Use this section to describe the task that students are required to complete. We ask that you also include instructions on running and preparing the students' local environment if necessary.*

Now that you got a Kubernetes Cluster up and running it's time for the challenge! 
We want to test whether you understood the basics of kubernetes and are willing to push yourself to understand more and create a new service on your own!

Your task is to
- Implement service.yaml which exposes the Kubernetes pod.
- Route the exposed Kubernetes pod to localhost:30000 or other available PORT.

## Task Expectations
*Please add expectations that students need to follow to be considered. Some examples include: completing the task on their own, not using code from external resources without comprehending the logic, etc.*

- Kubernetes pod is exposed to localhost:30000 or other available PORT
- User can see the index page on localhost:30000 (or other available PORT) when cluster is runnning.
- BONUS: If use an external [LoadBalancer](https://kubernetes.io/docs/tasks/access-application-cluster/create-external-load-balancer/).
- BONUS: If you use [ingress](https://kubernetes.io/docs/concepts/services-networking/ingress/) in the cluster.

## Task submission

Students are expected to use the [GitHub Flow](https://docs.github.com/en/get-started/quickstart/github-flow) when working on their task. This includes

1. Making changes on the auto generated feedback branch to complete the task
2. Using the auto generated Feedback Pull Request for review and submission
3. Using GitHub Discussions to ask any relevant questions regarding the projec

## Resources
*Use this section to add resources for students to refer to. For example: Documentation, Tutorials, Guides, and more.*

- [Containerzie a node app](https://nodejs.org/en/docs/guides/nodejs-docker-webapp/)
- [Hosting a simple static app using Express](https://www.digitalocean.com/community/tutorials/use-expressjs-to-deliver-html-files)
- [ExpressJS tutorial](https://www.freecodecamp.org/news/express-explained-with-examples-installation-routing-middleware-and-more/#:~:text=Both%20req%20and%20res%20are,it%20gets%20an%20HTTP%20request.)

## Questions
We love to answer questions! We highly recommend learning by doing and looking up the questions before reaching out. If you were unable to find your solution online, please open a new discussion in this repository.
