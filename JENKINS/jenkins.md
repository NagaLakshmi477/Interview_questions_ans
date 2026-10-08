# CI/CD Pipeline — DevSecOps with Jenkins, Kubernetes & Argo CD
In our project, we use **GitHub as the source code repository**, **Jenkins as the CI/CD orchestrator**, and **Kubernetes as the target deployment platform**.

Whenever a developer commits code or raises a pull request, the code is reviewed and merged into the GitHub repository. Once the code is committed, a **GitHub webhook triggers the Jenkins pipeline**.

Our Jenkins pipeline follows a **DevSecOps approach with Shift-Left practices**, where we try to identify code quality and security issues as early as possible.

The pipeline starts with the **Checkout stage**, where Jenkins checks out the latest application code from GitHub.

Next, we have the **Build and Unit Test stage**. Since we are using a Java application, we use **Maven** to build the application and execute the unit test cases. If the build or unit tests fail, the pipeline stops.

After that, we have the **SonarQube/code quality stage**. Here, we perform static code analysis and security-related checks. SonarQube checks the code for issues such as bugs, code smells, vulnerabilities, and maintainability issues. We also configure a **Quality Gate**, and Jenkins verifies the Quality Gate result. If the Quality Gate fails, the pipeline stops and the code will not proceed to the next stages.

We also perform the required **security and dependency checks** as part of our Shift-Left approach so that vulnerabilities can be identified before the application is deployed.

Once the code passes these checks, we move to the **container image build stage**. Since our target platform is Kubernetes, we build a container image using the Dockerfile available in the repository.

After building the image, we perform **container image scanning** to identify vulnerabilities in the base image, operating-system packages, and application dependencies.

If the image passes the security checks, we **push the container image to our image registry**. In an AWS environment, for example, this could be Amazon ECR.

After the image is pushed, the deployment configuration needs to reference the new image version. We maintain our Kubernetes deployment manifests or Helm charts in Git.

Once the Kubernetes configuration is updated with the new image version, **Argo CD follows the GitOps approach**. Argo CD continuously monitors the Git repository and detects the configuration change.

When Argo CD detects the new image version, it synchronizes the changes and deploys the application to the **Kubernetes cluster**.

So, overall, our flow is:

**Developer → GitHub → Jenkins → Checkout → Build & Unit Test → SonarQube + Quality Gate → Security Checks → Container Image Build → Image Scan → Image Registry → Kubernetes Manifest/Helm Update → Argo CD → Kubernetes**

The main advantage of this approach is that we combine **CI, security checks, and GitOps-based continuous delivery**, while keeping Git as the source of truth for our deployment configuration.

## Can you explain your project?”
“Sure. I’m currently working on an Immigration application that supports the immigration and visa processing workflow. From the DevOps side, my responsibility is to support the application teams by managing the application deployment, CI/CD automation, infrastructure, and environment-related activities.
The application is a web-based application with frontend and backend components, and it uses a database for storing application and immigration-related information. We have different environments such as development, testing, and production.
As part of my role, I work on CI/CD pipelines using Jenkins. When developers commit their code to Git, the pipeline is triggered. Jenkins checks out the code, performs the build and unit testing, and then we perform code-quality and security checks using tools such as SonarQube. After the validation is successful, we build the application/container image and deploy it to the respective environment.
For infrastructure provisioning and configuration, we use Terraform and Ansible. Terraform is used for provisioning the required infrastructure, while Ansible is used for configuration management and application/server-related configuration.
I also work on deployment troubleshooting, monitoring, environment issues, and coordinating with developers and other teams whenever there are deployment or application-related issues.
So overall, my role in the Immigration project is to make sure the application can be built, tested, deployed, and supported reliably across different environments through automation and DevOps practices.”

## Can you explain the architecture?”

“At a high level, our Immigration application follows a web-based application architecture. Users interact with the frontend through the browser. The frontend communicates with the backend application through APIs. The backend handles the business logic and communicates with the database for storing and retrieving the required information.
From the DevOps perspective, the application source code is maintained in Git. Jenkins is used for CI/CD automation. During the CI process, we perform build, unit testing, SonarQube quality checks and security validation. After the application is packaged successfully, it is deployed to the target environment.
We use Terraform for infrastructure provisioning and Ansible for configuration management. We also have monitoring and logging mechanisms to identify deployment or application issues.
So the simplified flow is:
User → Frontend → Backend/API → Database
And from the DevOps side:
Git → Jenkins → Build & Tests → SonarQube/Quality Gate → Deployment → Environment → Monitoring.”
## day to day activities

In my current project, I work as a DevOps engineer for an **Immigration application**.

My day-to-day activities mainly include **CI/CD, deployments, infrastructure, configuration management, and troubleshooting**.

I work with **Git and Jenkins** for CI/CD pipelines. Whenever developers make code changes, I monitor the Jenkins pipeline and troubleshoot issues related to build, testing, SonarQube, or deployment.

I use **Terraform** for infrastructure-related activities and **Ansible** for configuration management.

I also support application deployments and troubleshoot environment or deployment issues. If there are any security or VAPT observations, I work with the team to fix them.

Apart from technical activities, I attend **daily stand-up meetings**, work on Jira tickets based on priority, and coordinate with developers and other teams.

So, overall, my main responsibility is to **automate deployments, maintain the environment, troubleshoot issues, and support the development team in delivering the application smoothly.**

Hi, my name is Naga Lakshmi. I’m from Andhra Pradesh, and I completed my B.Tech in Electronics and Communication in 2021.

I started my career as a Python developer, where I worked mainly on backend APIs and PostgreSQL. Later, I moved into DevOps, and I now have over 4 years of overall experience, mainly working with AWS and DevOps technologies.

Currently, I’m working at HTC Global Services on the Open ERP Immigration project. My responsibilities include building and maintaining Jenkins CI/CD pipelines, starting from application build and testing, followed by Docker image creation, security scanning, pushing images to Amazon ECR, and deploying applications across different environments.

I also provision AWS infrastructure using Terraform, and I work with Amazon EKS for deploying microservices using Helm and Argo CD. We have also integrated SonarQube and security scanning into our CI/CD pipelines as part of our DevSecOps approach.

Before this, I worked at Deloitte on the TIAA project, where my main responsibilities were provisioning AWS infrastructure using Terraform and server configuration using Ansible, with Jenkins used for automation.

My strongest areas are Terraform, Jenkins, Docker, and Ansible, and I also have hands-on experience with Kubernetes and EKS. I particularly enjoy troubleshooting because a major part of my work involves identifying why a deployment, application, or connectivity issue is happening and resolving it.

Going forward, I want to continue growing in cloud, Kubernetes, and DevOps, and I believe this opportunity at Infosys would give me a good platform to take that experience further.

Thank you.

