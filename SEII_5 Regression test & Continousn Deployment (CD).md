### Study Notes for Comp 4350 Software Engineering II Lecture 5: Regression Testing and Continuous Deployment

#### I. Key Concepts
- **Main Idea 1:** Regression testing is a software testing practice that ensures unchanged parts of the application function the same after modifications to the code.
- **Main Idea 2:** Continuous Deployment is the automatic release of software changes to production without manual intervention.
- **Main Idea 3:** Containers offer a streamlined way to package and deploy applications consistently across various environments.

#### II. Definitions
- **Regression Testing:** A testing phase that verifies that software previously developed and tested still performs accurately after it has been changed or interfaced with other software.
- **Continuous Deployment:** A software release process that uses automated testing to validate if changes to a codebase are correct and stable for immediate autonomous deployment to a production environment.
- **Container:** A package of software that includes all of the necessary elements such as libraries and other dependencies, and ensures that it runs uniformly despite differences for instance between development and staging.

#### III. Important Details
- **Point 1:** Regression tests are selected based on recent code changes, with priority given to areas with previous bugs or where critical functionality is implemented.
- **Point 2:** Blue-green deployments, canary releasing, and A/B testing are strategies used to reduce the risk associated with deploying new software versions.
- **Point 3:** Containers use less resources than virtual machines as they do not include full operating system images and run directly within the host machine's kernel.

#### IV. Diagrams/Visual Aids
- **Diagram 1:** A visual heatmap for defect frequency aids in visualizing critical areas in the code base that may warrant more intensive regression testing.
- **Diagram 2:** Flow diagram of a typical deployment pipeline demonstrating the stages from code commit to production release.
- **Diagram 3:** Different deployment strategies such as A/B Testing and Canary Releases visually represented to show how users are incrementally introduced to new features.

#### V. Key Formulas/Theorems
- **Formula/Theorem 1:** Defect Prediction formula used by Google weighs the number and age of bugs to prioritize test cases.
- **Formula/Theorem 2:** Docker commands tutorial for container management demonstrates the practical syntax and usage in real-world scenarios.

#### VI. Examples
- **Example 1:** Step-by-step use case of running a MySQL container and exploring operations within the container environment.
- **Example 2:** Creating and deploying a java web application within a container by manually creating and committing a Docker image.
- **Example 3:** Using Dockerfile to build, tag, and push an image to Docker Hub, emphasizing the importance of a well-organized container registry.

#### VII. Summary/Conclusion
- **Recap of Main Points:** Regression testing is vital for maintaining software stability. Continuous deployment with blue-green deployments, canary releases, and A/B testing facilitates the progressive and safe rollout of software. Containers have become a fundamental part of consistent and efficient software deployment.
- **Connections between Concepts:** Regression testing complements the continuous deployment pipeline, ensuring reliability at every development stage. When integrated with containerization, this pipeline becomes even more robust, guaranteeing consistent performance across environments.

#### VIII. Additional Resources
- **Textbook Pages:** Jez Humble and David Farley, "Continuous Delivery," Chapters 7 & 8.
- **Online Resources:** 
  - Google Testing Blog: [Bug Prediction at Google](http://google-engtools.blogspot.com/2011/12/bug-prediction-at-google.html)
  - Tutorial on Docker: [Docker Documentation](https://docs.docker.com/install/)
  - Deployment Strategy: Martin Fowler’s Blog
    - [Blue-Green Deployment](https://martinfowler.com/bliki/BlueGreenDeployment.html)
    - [CanaryRelease](https://martinfowler.com/bliki/CanaryRelease.html)

Notes:
- Ensure TA meeting for sprint evaluation is attended.
- Project proposal submission and presentation preparation are due on noted dates; refer to UMLearn and the project Google spreadsheet for details.
- Docker is a central tool for containerization in DevOps practices.

Please replace the placeholder text in the above template with the correct information from the provided class notes.

---

Notes: 
Comp 4350Software Engineering IILecture 5
Dr. Shaowei Wang
Administrative items	
Meet TA next week for sprint 1 evaluation.
Submit project proposal by next Friday to UMLearn (Assignment -> project proposal)
We will have presentation to introduce your project next week.  
Find the schedule in the project google spreadsheet
Submit slides before your presentation to UMLearn (Assignments-> Project proposal presentation)

Agenda
Regression testing
Continuous deployment
Tutorial on Docker
4
System Building and Release Pipelines


Regression testing


Regression testing
A software testing practice that ensures an application still functions as expected after any code changes, updates, or improvements. 

Goal
Make sure the changes in code does not break existing functional and non-functional requirement of the system.
Find defect in early stage.



Earlier features get more exercise!


How to do regression testing?
Regression testing uses test cases that have already been used but are re-executed to make sure that the software still works the way it did before changes were made. 

Can be done in different levels:
Unit testing
Integration testing
System testing
Acceptance testing 

Complete vs partial ?



Quality (e.g., coverage) 
Cost (e.g., time/resource) 



Complete regression - expensive
Complete regression tests are conducted when:
The software updates affect the foundation of the code;
If there are multiple changes added to the code; or 
If the update greatly affects the codebase







Tips for test cases selection/prioritization
 Select test cases for Regression testing where there are recent code changes or functional changes.

What do we need?
Requires the link between code and test cases


Tips for test cases selection/prioritization
 Select test cases for Regression testing where there are recent code changes or functional changes.
Select test cases for Regression testing in areas with frequent bugs/defects.
What do we need?
Requires the link between code and test cases
Requires the history of the bug fixing 





Defects frequency heatmap
Defect prediction at Google
The score is based on two factors: how many bugs have ever happened in f, and how old are they. 

Decided to score each file by weighting each bug-fixing commit by how old it is. As the commit gets older, so its influence tends towards 0. 

Where n is the number of bug-fixing commits, and ti is the timestamp of the bug-fixing commit represented by i. 
http://google-engtools.blogspot.com/2011/12/bug-prediction-at-google.html
Score (f)  =
Tips for test cases selection/prioritization
 Select test cases for Regression testing where there are recent code changes or functional changes.
Select test cases for Regression testing in areas with frequent bugs/defects.
Choose test cases with critical functionalities.
…

Regression testing can be done in any level and should select tests from various level
Unit testing
Integration testing
System testing
Acceptance testing 

Acceptance testing
An individual acceptance test is intended to verify that the acceptance criteria of a story or requirement have been met. 
The goal is asserting that a user/customer has what they need.   
Type of acceptance testing
Functional
Non-functional (performance, capacity)

Why Is Automated Acceptance Testing Essential? 
Rapid release for modern software system (Web/Mobile Apps). 
Manual acceptance testing is expensive and slow
one organization that spends $3,000,000 on manual acceptance testing for every release. 
Acceptance tests also protect your application when you are making large-scale changes to it. 


Automate Functional testing tool - TESTIM
https://www.testim.io/blog/regression-testing/
Drawback 
Won’t work properly if UI is modified (UI perspective)
Apply it once your UI is stable


Agenda
Regression testing
Continuous deployment
Tutorial on Decker
Continuous Deployment
A software production process where changes are automatically deployed to production without any manual intervention

(see addendums to lecture notes from DZone)
28
Typical deployment pipeline
29
Production environment
Releasing strategies
How can we safely deploy our releases to a large number (e.g., missions to billions) of users?

Blue-green deployments

Canary Releasing

A/B Testing
30
Blue-green deployments
31
Reduce downtime and risk by running two identical production environments called Blue and Green.

At any time, only one of the environments is live, with the live environment serving all production traffic. 
Source: https://martinfowler.com/bliki/BlueGreenDeployment.html
old
new
Canary Releasing
32
Reduces the risk of introducing a new software version in production by slowly rolling out the change to a small subset of users before rolling it out to the entire infrastructure and making it available to everybody.
1. You start by deploying the new version of your software to a subset of your infrastructure, to which no users are routed.
Source: https://martinfowler.com/bliki/CanaryRelease.html
Canary Releasing
33
Reduces the risk of introducing a new software version in production by slowly rolling out the change to a small subset of users before rolling it out to the entire infrastructure and making it available to everybody.
2. When you are happy with the new version, you can start routing a few selected users to it.
Source: https://martinfowler.com/bliki/CanaryRelease.html
Canary Releasing
34
Reduces the risk of introducing a new software version in production by slowly rolling out the change to a small subset of users before rolling it out to the entire infrastructure and making it available to everybody.
3. As you gain more confidence in the new version, you can start releasing it to more servers in your infrastructure and routing more users to it, until all the users have been routed to the new version. Then, you can decommission the old infrastructure. 
Source: https://martinfowler.com/bliki/CanaryRelease.html
A/B Testing
A/B testing is a way of testing features in your application for various reasons like usability, popularity, noticeability, etc,
Compare A vs B, determine which one is better.  
For exploration and experiment
Test a new version of recommendation system, and see it has a higher purchase conversion rate. 
Use nginx to distribute user requests
https://v2-1.docs.kubesphere.io/docs/quick-start/ingress-canary/
Agenda
Regression testing
Continuous deployment
Tutorial on Docker
Deploy applications in containers

A container is a standard unit of software that packages up code and all its dependencies, so the application runs quickly and reliably from one computing environment to another. 


Good practice in DevOps
What is container?
A container is an isolated, lightweight silo for running an application on the host operating system. Containers build on top of the host operating system's kernel and share the kernel, and contain only apps and some lightweight operating system APIs and services that run in user mode.
What is a virtual machine (VM)?
In contrast to containers, VMs run a complete operating system–including its own kernel.


https://www.backblaze.com/blog/vm-vs-containers/
Benefits of containers
Less overheadContainers require less system resources than traditional or hardware virtual machine environments because they don’t include operating system images.
Increased portabilityApplications running in containers can be deployed easily to multiple different operating systems and hardware platforms.
More consistent operationDevOps teams know applications in containers will run the same, regardless of where they are deployed.
Better application developmentContainers support agile and DevOps efforts to accelerate development, test, and production cycles.

Greater efficiencyContainers allow applications to be more rapidly deployed, patched, or scaled.
Uses for VMs vs Uses for Containers
VMs are a better choice for running apps that require all of the operating system’s resources and functionality when you need to run multiple applications on servers, or have a wide variety of operating systems to manage.
Containers are a better choice when your biggest priority is maximizing the number of single or limited number of applications running on a minimal number of servers.



Outline
Step 00 - Installing Docker
Step 01 - A simple Docker use case - Run mysql
Step 02 - Playing with Docker - Containers and Images
Step 03 - Manually creating a docker image
Step 04 – Push image to docker hub

Step 00 - Installing Docker
https://docs.docker.com/install/
Need to install Visual C++ redistributable for windows
Check if your docker is installed by running command:
docker --version
-> Ok
Step 01 - A simple Docker use case - Run mysql
Run command to pull down the mysql image:
docker pull mysql:5.7   
5.7 -> tag
You can specify which version you want to use 
https://hub.docker.com/_/mysql?tab=tags&page=1&ordering=last_updated

link:
https://hub.docker.com/search?q=mysql&source=verified

Step 01 - A simple Docker use case - Run mysql
Starting a MySQL instance by running:
docker run --name mysql_5.7 -e MYSQL_ROOT_PASSWORD=root -d mysql:5.7 
--name mysql_5.7 -> container name
-e MYSQL_ROOT_PASSWORD=root -> password for mysql
-d -> detach mode running command in background
mysql:5.7  -> name:tag of the image






Get into the interaction mode of the container
docker exec -it mysql_5.7 bash
exec: run a command in a running container
-it: interactive mode by allocating a terminal – debugging 
Play with mysql
mysql -u root -p 
CREATE DATABASE dbname 

Link
https://docs.docker.com/engine/reference/commandline/container_exec/




Step 01 - A simple Docker use case - Run mysql
Step 02 - Playing with Docker - Containers and Images
List running containers:
docker ps
List all containers
docker container ls
Restart a container:
docker restart mysql_5.7
Stop a container: 
docker stop mysql_5.7
Remove a container: 
docker rm mysql_5.7 
Stop it first before removing

List all the images
docker images
Remove image
docker image rm [image name]





Step 02 - Playing with Docker - Containers and Images
Step 03 - Manually creating a docker image
Context: I have a simple web application written in Java. I would like to deploy it in a docker image. 
Prepare a jar package
Code can be found:  https://github.com/shaoweiwang2010/SE_course_docker/tree/master/target

Test the jar in local machine
java -jar .\docker-in-5-steps-todo-rest-api-h2-1.0.0.RELEASE.jar

Try http://localhost:5000/hello-world



Step 03 - Manually creating a docker image
Copy the jar  into a Java container and set up to run the jar when launching up
Pull and run a Java container docker
docker run --name openjdk_8 -dit -p 5000:5000 openjdk:8-jdk-alpine
-p how host’s port binds to docker container’s port
Copy jar into running container
docker container cp .\docker-in-5-steps-todo-rest-api-h2-1.0.0.RELEASE.jar openjdk_8:/tmp
docker exec openjdk_8 ls tmp
docker exec -it openjdk_8 /bin/sh

Run the jar in container 
docker exec openjdk_8 java -jar tmp/docker-in-5-steps-todo-rest-api-h2-1.0.0.RELEASE.jar

Create an image for the running container and set up to run the jar when launching up
docker container commit --change=‘CMD exec java -jar /tmp/docker-in-5-steps-todo-rest-api-h2-1.0.0.RELEASE.jar’ openjdk_8 webapp:v1 
docker container commit: create a new image from a container’s change
--change: apply Dockerfile instruction to the created image 

Run a contain from the created image
docker run --name web_app_v1 -dit -p 5000:5000 webapp:v1

https://docs.docker.com/engine/reference/commandline/container_commit/


Step 03 - Manually creating a docker image
--change='CMD exec java -jar /tmp/docker-in-5-steps-todo-rest-api-h2-1.0.0.RELEASE.jar' 
Step 04 – Push image to docker hub
Create an account in docker hub (https://hub.docker.com/)
Create a repo
Push image to docker hub by logining an pushing
Login 
docker login --username=shaoweiwang2020
![important] Re-tag the image to <hub-user>/<repo-name>[:<tag>]
docker tag <existing-image> <hub-user>/<repo-name>[:<tag>]
docker tag webapp:v1 shaoweiwang2020/web_app1:v2 
Push to your repo
docker push <hub-user>/<repo-name>:<tag> 
docker push shaoweiwang2020/web_app1:v2
Materials
https://docs.docker.com/docker-hub/repos/#:~:text=To%20push%20an%20image%20to,docs%2Fbase%3Atesting%20).
https://stackoverflow.com/questions/41984399/denied-requested-access-to-the-resource-is-denied-docker




Create image using Dockerfile

Dockerfile
# Create docker image
FROM openjdk:8-jdk-alpine
VOLUME /tmp
EXPOSE 5000
ADD target/*.jar app.jar
ENTRYPOINT [ "sh", "-c", "java -jar /app.jar" ]


Run this commend in working dir (contain the Dockerfile)
	docker build -t myappweb:v2.4 .

Run this commend to run the built dock image
	docker run --name web_app_v2.4 -dit -p 5001:5000 myappweb:v2.4


https://docs.sevenbridges.com/docs/upload-your-docker-image-with-a-dockerfile
reference
Chapter 7 & 8, Jez Humble and David Farley,  Continuous Delivery.
https://testsigma.com/blog/how-to-prioritize-test-cases-for-regression-testing/
https://testsigma.com/blog/9-tips-for-selecting-test-cases-for-regression-testing/


Create your image based on existing OS
Ubuntu by running
docker pull ubuntu:trusty-20180412
docker run --name ubuntu_2018 -dit ubuntu:trusty-20180412
Install package by running
docker exec -it ubuntu_2018 /bin/bash
sudo apt update
sudo apt install default-jre 

Link 
https://hub.docker.com/_/ubuntu?tab=description&page=7&ordering=last_updated

