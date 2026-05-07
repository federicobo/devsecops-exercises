# devsecops-exercises

🇮🇹 [Leggi in italiano](README.it.md)

This repository was created to collect exercises and provide practical instructions to help you prepare for the *Integrate Vulnerability Management in DevSecOps Cycle* course

## Base Prerequisites
To complete the tasks in the exercises, you'll need a GitHub account (it's free):  
https://github.com/signup

**If the course is held in person, please remember to bring your laptop and charger!**

To get the most out of the tools we’ll be using together in this course, we strongly recommend having a PC running a Linux distribution, or alternatively a virtual machine (WSL for Linux is fine too!).

## Functional Prerequisites
### Fork the repository

To ensure you can work independently during the exercises, we recommend that you fork our starter repository to your GitHub profile.  

Here are the steps you need to follow once you’ve created your GitHub account:  
https://docs.github.com/en/get-started/quickstart/fork-a-repo

### Docker Hub

To run the exercise on Docker, you need to have an account on Docker Hub, create an API access key, and then add it to the **Secrets** section of the repository you are going to create.  

You can create an account at the following link:  
https://hub.docker.com/signup  

Once you've created your account, you'll be able to generate an access token.  
To do so, follow the steps at the link below:  
https://docs.docker.com/security/for-developers/access-tokens/

#### Forked Repo docker hub permissions

Once you have completed the *Docker Hub* step, you need to enter the Docker credentials you just generated (**username** + **access token**) into the repository secrets you forked.

To do this, follow these steps:
1. Navigate to the link for the repository you forked (e.g., https://github.com/your_name/devsecops-exercises)
2. Click **Settings** in the top-right navigation bar.
3. On the new page, in the left sidebar, click **Secrets and variables** and then **Actions** in the dropdown menu that just opened.
4. On the new page, click **New repository secret**, and fill out the form by entering the following fields


    | Name | Secret |
    | :---|---:|
    | **DOCKERHUB_USERNAME** | your docker username |
    | **DOCKERHUB_PASSWORD**   | the API key you just generated |

<br/>

For your reference, here is the documentation on managing secrets on GitHub:  
https://docs.github.com/en/actions/security-guides/using-secrets-in-github-actions

### Dependency Track
To speed up the download and simplify the setup process for the exercises, please follow these steps once you have installed Docker on the computer or virtual machine you will be using during the course:
#### Dependency track docker compose execution
Run the following command from the root directory of this repository:
``` bash
cd dtrack
docker compose up -d
```

This will download the Docker images required by the application, which will then be launched.  
Once running, it will download the additional data needed to use its features.

#### Public CVEs DB API key creation
To avoid the rate limits imposed by CVE data providers on public APIs, you need to set up personal access tokens for the GitHub Advisories and NIST databases.  
Be sure to save both tokens so that you can easily access them later.

##### GitHub
Go to the following link and create a token (classic); you'll need a GitHub account (at this point you should already have it):  
https://github.com/settings/tokens  
The token does not require a scope or access to the repository.

##### NIST
Please click on the following link and fill out the form with your information:  
https://nvd.nist.gov/developers/request-an-api-key  
Once you've submitted the form, follow the instructions in the email to obtain the API key that we'll use during the course.

## Extra

If you have a preferred IDE, you can clone the repository you forked and set up the Git client configurations as usual.

### Generate SSH key on GitHub
https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent

### Installing Docker and pulling images

Some of the exercises we will be working on during the course require the use of containerization software. Due to its popularity and extensive documentation, we recommend using **Docker**, but the equivalent alternatives **Podman** and **Containerd** are also suitable for this purpose.  

To use **Docker**, you will find installation instructions specific to the Linux operating system you will be using during the course at the following address:  
https://docs.docker.com/engine/install/  


To speed up access to the content, once you have installed **Docker**, download the following images to your workstation a few days before the course begins:
- `docker pull aquasec/trivy@sha256:be1190afcb28352bfddc4ddeb71470835d16462af68d310f9f4bca710961a41e` (0.70.0)
- `docker pull zaproxy/zap-stable@sha256:4f67b3e798fd4e23649265eac9ad84a67e883850c96691fc1743b2a6e1cc7ed0` (2.17.0)

# External resources
In this section, you'll find links to the tools and external resources shared during the training.

## Threat Modeling with OWASP threat dragon
https://github.com/OWASP/threat-dragon

## CVSS scoring
**CVSS 3.1** - https://www.first.org/cvss/calculator/3.1  
**CVSS 4.0** - https://www.first.org/cvss/calculator/4.0

## SBOM generation
**cdxgen** - https://cdxgen.github.io/cdxgen/#/

## VEX generation
**osv scanner** - https://github.com/google/osv-scanner  
**trivy** - https://github.com/aquasecurity/trivy

## K8s (kubernetes) cluster KBOM and scan
**trivy** - https://trivy.dev/docs/latest/guide/target/kubernetes/  

## Continuous Security Monitoring
**Dependency Track** - https://dependencytrack.org/

## SAST
**OWASP suggested SAST tools** - https://owasp.org/www-community/Source_Code_Analysis_Tools  
**CodeQL supported languages** - https://codeql.github.com/docs/codeql-overview/supported-languages-and-frameworks/  
**SonarQube supported languages** - https://docs.sonarsource.com/sonarqube/latest/analyzing-source-code/languages/overview/  

## DAST
**ZAP GitHub Action** - https://github.com/marketplace/actions/zap-full-scan  
**ZAP Custom Auth Scripts** - https://www.zaproxy.org/docs/authentication/handling-auth-yourself/  
**ZAProxy (CheckMarx)** - https://www.zaproxy.org/download  
**BurpSuite (PortSwigger)** - https://portswigger.net/burp/communitydownload  
**Nuclei (ProjectDiscovery)** - https://projectdiscovery.io/nuclei

## Image Scan
**Docker Scout** - https://docs.docker.com/scout/quickstart/

## Security frameworks
**5D framework** - https://owasp.org/www-project-software-security-5d-framework/  
**SCVS** - https://owasp.org/www-project-software-component-verification-standard/  
**SCVS JSON** - https://github.com/OWASP/Software-Component-Verification-Standard/releases/download/1.0/OWASP_SCVS-1.0.json  
**ASVS** - https://owasp.org/www-project-application-security-verification-standard/

## OWASP Vulnerable Apps
The vulnerable applications we have exposed in this repository are taken from a list provided by OWASP, which compiles and categorizes projects created for this purpose at the following link:  
https://owasp.org/www-project-vulnerable-web-applications-directory/


# Follow Us on Security News
Stay up to date with the latest news on cybersecurity by subscribing at the following link:  
https://davideariu.substack.com/
