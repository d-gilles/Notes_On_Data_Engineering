<img src="https://www.aloudinthecloud.com/images/gcp_icon_cloud.png" width="100" height="100" alt="GC CLI">

# Google Cloud CLI

### ⁉️ Overview

The gcloud library is a command-line tool and Python library provided by Google Cloud Platform to interact with various Google Cloud services, including compute, storage, machine learning, and many more. The library can be used to manage resources, deploy applications, and automate tasks related to Google Cloud Platform.

Some of the key features of gcloud library include:

- Interact with Google Cloud services using command-line interface or programmatically using Python code
- Manage Google Cloud resources such as virtual machines, storage buckets, and databases
- Deploy and manage applications on Google Cloud Platform using built-in tools and APIs
- Access and manage Google Cloud services programmatically using client libraries
- Securely authenticate and authorize access to Google Cloud Platform resources

Overall, the gcloud library provides a convenient and powerful way to manage Google Cloud Platform resources and services.

### **🧑‍🎓** Resources
<details><summary>Here are 10 resources to learn GCP and its CLI:</summary>


1. **Google Cloud Platform documentation**: The official GCP documentation is a great place to start learning about the platform and its CLI. It covers a wide range of topics, from getting started with GCP to advanced topics like machine learning and big data.
2. **GCP YouTube Channel**: The GCP YouTube channel offers a wealth of videos on various topics related to the platform, including tutorials, demos, and webinars.
3. **GCP Coursera courses**: Google offers several GCP courses on Coursera, which provide a comprehensive introduction to the platform and its CLI. These courses are self-paced and include hands-on labs.
4. **GCP Qwiklabs**: Qwiklabs provides hands-on labs and tutorials for GCP, allowing you to practice using the platform and its CLI in a safe, sandboxed environment.
5. **GCP Stack Overflow**: Stack Overflow is a great resource for getting answers to specific questions related to GCP and its CLI. You can browse questions and answers or ask your own questions.
6. **GCP Community**: The GCP Community is a forum for developers and users of GCP to share knowledge and best practices. You can ask questions, share your experiences, and learn from others in the community.
7. **GCP Blog**: The GCP Blog provides updates, news, and insights about GCP and its CLI. It's a great resource for staying up to date on the latest developments in the platform.
8. **GCP Slack channel**: The GCP Slack channel is a community of GCP users and experts who share knowledge and help each other out. You can join the channel to ask questions, get help, and connect with other GCP users.
9. **GCP GitHub**: Google maintains several GitHub repositories for GCP, including client libraries and sample code. You can browse these repositories to learn how to use GCP and its CLI programmatically.
10. **GCP Training and Certification**: Google offers official training and certification programs for GCP, which provide a structured curriculum and hands-on labs to help you master the platform and its CLI. These programs are designed for developers, IT professionals, and data scientists who want to learn how to use GCP effectively.
</details>

### Install

Install the `gcloud` CLI to communicate with [Google Cloud Platform](https://cloud.google.com/) through your terminal:

```bash
echo "deb [signed-by=/usr/share/keyrings/cloud.google.gpg] https://packages.cloud.google.com/apt cloud-sdk main" | sudo tee -a /etc/apt/sources.list.d/google-cloud-sdk.list
sudo apt-get install apt-transport-https ca-certificates gnupg
curl https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key --keyring /usr/share/keyrings/cloud.google.gpg add -
sudo apt-get update && sudo apt-get install google-cloud-sdk
sudo apt-get install google-cloud-sdk-app-engine-python
```

👉 [Install documentation](https://cloud.google.com/sdk/docs/install#deb)

Run `gcloud init` when runing the first time to setup everything.

Run `gcloud --help` to see the Cloud Platform services you can interact with.

- Run `gcloud help COMMAND` to get help on any gcloud command.
- Run `gcloud topic --help` to learn about advanced features of the SDK like arg files and output formatting
- Run `gcloud cheat-sheet` to see a roster of go-to `gcloud` commands.

### 💻 Commands

**NAME**
`gcloud cheat-sheet` - display gcloud cheat sheet

**DESCRIPTION**
A roster of go-to gcloud commands for the gcloud tool, Google Cloud's
primary command-line tool.

**Getting started**
Get going with the gcloud command-line tool

```
  ▪ gcloud init: Initialize, authorize, and configure the gcloud tool.
  ▪ gcloud version: Display version and installed components.
  ▪ gcloud components install: Install specific components.
  ▪ gcloud components update: Update your Google Cloud CLI to the latest
    version.
  ▪ gcloud config set project: Set a default Google Cloud project to work
    on.
  ▪ gcloud info: Display current gcloud tool environment details.
```

**Help**
Google Cloud CLI is happy to help.

```
  ▪ gcloud help: Search the gcloud tool reference documents for specific
    terms.
  ▪ gcloud feedback: Provide feedback for the Google Cloud CLI team.
  ▪ gcloud topic: Supplementary help material for non-command topics like
    accessibility, filtering, and formatting.
```

**Personalization**
Make the Google Cloud CLI your own; personalize your configuration with properties.

```bash
      ▪ gcloud config set: Define a property (like compute/zone) for the
        current configuration.
      ▪ gcloud config get: Fetch value of a Google Cloud CLI property.
      ▪ gcloud config list: Display all the properties for the current
        configuration.
      ▪ gcloud config configurations create: Create a new named
        configuration.
      ▪ gcloud config configurations list: Display a list of all available
        configurations.
      ▪ gcloud config configurations activate: Switch to an existing named
        configuration.
```

**Credentials**
Grant and revoke authorization to Google Cloud CLI

```bash
      ▪ gcloud auth login: Authorize Google Cloud access for the gcloud tool
        with Google user credentials and set current account as active.
      ▪ gcloud auth activate-service-account: Like gcloud auth login but with
        service account credentials.
      ▪ gcloud auth list: List all credentialed accounts.
      ▪ gcloud auth print-access-token: Display the current account's access
        token.
      ▪ gcloud auth revoke: Remove access credentials for an account.
```

**Projects**
Manage project access policies

```
  ▪ gcloud projects describe: Display metadata for a project (including
    its ID).
  ▪ gcloud projects add-iam-policy-binding: Add an IAM policy binding to
    a specified project.

```

**Identity & Access Management**
Configuring Cloud Identity & Access Management (IAM) preferences and
service accounts

```
  ▪ gcloud iam list-grantable-roles: List IAM grantable roles for a
    resource.
  ▪ gcloud iam roles create: Create a custom role for a project or org.
  ▪ gcloud iam service-accounts create: Create a service account for a
    project.
  ▪ gcloud iam service-accounts add-iam-policy-binding: Add an IAM policy
    binding to a service account.
  ▪ gcloud iam service-accounts set-iam-policy: Replace existing IAM
    policy binding.
  ▪ gcloud iam service-accounts keys list: List a service account's keys.

```

**Docker & Google Kubernetes Engine (GKE)**
Manage containerized applications on Kubernetes

```
  ▪ gcloud auth configure-docker: Register the gcloud tool as a Docker
    credential helper.
  ▪ gcloud container clusters create: Create a cluster to run GKE
    containers.
  ▪ gcloud container clusters list: List clusters for running GKE
    containers.
  ▪ gcloud container clusters get-credentials: Update kubeconfig to get
    kubectl to use a GKE cluster.
  ▪ gcloud container images list-tags: List tag and digest metadata for a
    container image.
```

**Virtual Machines & Compute Engine**
Create, run, and manage VMs on Google infrastructure

```
  ▪ gcloud compute zones list: List Compute Engine zones.
  ▪ gcloud compute instances describe: Display a VM instance's details.
  ▪ gcloud compute instances list: List all VM instances in a project.
  ▪ gcloud compute disks snapshot: Create snapshot of persistent disks.
  ▪ gcloud compute snapshots describe: Display a snapshot's details.
  ▪ gcloud compute snapshots delete: Delete a snapshot.
  ▪ gcloud compute ssh: Connect to a VM instance by using SSH.
```

**Serverless & App Engine**
Build highly scalable applications on a fully managed serverless platform

```
  ▪ gcloud app deploy: Deploy your app's code and configuration to the
    App Engine server.
  ▪ gcloud app versions list: List all versions of all services deployed
    to the App Engine server.
  ▪ gcloud app browse: Open the current app in a web browser.
  ▪ gcloud app create: Create an App Engine app within your current
    project.
  ▪ gcloud app logs read: Display the latest App Engine app logs.
```

**Miscellaneous**
Commands that might come in handy

```
  ▪ gcloud kms decrypt: Decrypt ciphertext (to a plaintext file) using a
    Cloud Key Management Service (Cloud KMS) key.
  ▪ gcloud logging logs list: List your project's logs.
  ▪ gcloud sql backups describe: Display info about a Cloud SQL instance
    backup.
  ▪ gcloud sql export sql: Export data from a Cloud SQL instance to a SQL
    file.
```

**GCLOUD WIDE FLAGS**

```bash
These flags are available to all commands: --access-token-file, --account,
--billing-project, --configuration, --flags-file, --flatten, --format,
--help, --impersonate-service-account, --log-http, --project, --quiet,
--trace-token, --user-output-enabled, --verbosity.
```
