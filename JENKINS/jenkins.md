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
