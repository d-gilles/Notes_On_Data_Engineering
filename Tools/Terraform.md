<img src="https://www.svgrepo.com/show/354447/terraform-icon.svg" width="100" height="100" alt="Postgres">

# Terraform

### ⁉️ Overview

Terraform is an open-source infrastructure as code (IAC) tool that allows users to define, provision, and manage infrastructure resources through code. It supports a variety of providers, including AWS, Google Cloud, and Azure, and allows users to manage their infrastructure using a declarative language, called HashiCorp Configuration Language (HCL).
<details><summary>more ...</summary> Terraform provides users with a number of CLI commands that allow them to manage their infrastructure resources, including initializing a working directory, generating an execution plan, applying changes, and destroying resources. By leveraging Terraform, users can ensure that their infrastructure is consistent, repeatable, and scalable.

Terraform is a popular tool in the DevOps community because it allows infrastructure to be managed as code. This means that infrastructure can be version controlled and changes can be tracked over time, making it easier to collaborate and maintain consistency across teams. Terraform also provides a number of features that make it easier to manage complex infrastructure, including the ability to create modules and workspaces, as well as support for state locking and remote backends.

Overall, Terraform is a powerful tool that can help teams manage their infrastructure more effectively. By allowing infrastructure to be managed as code, Terraform enables teams to work more collaboratively, maintain consistency, and improve the scalability and reliability of their infrastructure.
</details>

### **🧑‍🎓** Ressources

▶️ [Terraform overview in 15 mins](https://www.youtube.com/watch?v=l5k1ai_GBDE)
<details>
<summary>
Here are some of the best open-source resources to learn Terraform:</summary>

* **Terraform official documentation** - https://www.terraform.io/docs/index.html: The official documentation is the best place to start learning Terraform. It covers everything from the basics to advanced topics.

* **Terraform Up & Running, 2nd Edition** - https://www.terraformupandrunning.com/: This is a comprehensive guide to Terraform written by Yevgeniy Brikman. The book covers everything you need to know to get started with Terraform, including how to set up your infrastructure, write Terraform code, and manage your infrastructure.

* **Terraform Getting Started Guide** - https://learn.hashicorp.com/collections/terraform/getting-started: This is a step-by-step guide for beginners to get started with Terraform. It covers the basics of Terraform, such as how to write and execute Terraform code.

* **Terraform Courses on Udemy** - https://www.udemy.com/topic/terraform/: Udemy offers a variety of courses on Terraform that cover different levels of expertise. You can find courses for beginners, intermediate, and advanced levels.

* **Terraform Modules on GitHub** - https://github.com/terraform-aws-modules: GitHub has many Terraform modules that you can use as templates to set up your infrastructure quickly. These modules are community-built and cover a wide range of infrastructure types.

* **HashiCorp Learn** - https://learn.hashicorp.com/terraform: This is a collection of interactive tutorials that cover the basics of Terraform. You can learn how to set up your infrastructure, write Terraform code, and manage your infrastructure through these tutorials.

* **HashiCorp YouTube channel** - https://www.youtube.com/c/HashiCorp/videos: HashiCorp's YouTube channel has many videos on Terraform that cover various topics. You can learn how to use Terraform to manage your infrastructure, how to integrate it with other tools, and how to write efficient Terraform code.

* **Terraform Registry** - https://registry.terraform.io/: This is a repository of community-built Terraform modules that you can use to set up your infrastructure. You can search for modules based on the infrastructure type you want to set up and the provider you want to use.
</details>

### 💻 Commands

Terraform's CLI (Command Line Interface) provides a variety of commands that allow users to manage their infrastructure. Below is an overview of some of the main commands:

- `terraform init` - Initializes a Terraform working directory by downloading and installing modules and providers as specified in the configuration files.
- `terraform plan` - Generates an execution plan that describes what Terraform will do when applied, including creating, modifying, or deleting resources.
- `terraform apply` - Applies the changes described in a Terraform execution plan to the infrastructure, creating, modifying, or deleting resources as necessary.
- `terraform destroy` - Destroys the infrastructure managed by Terraform, deleting all resources that were created as part of the configuration.
- `terraform state` - Provides functionality for inspecting and modifying Terraform's state file, which contains information about the current state of the infrastructure.
- `terraform import` - Imports existing resources into Terraform's state, allowing users to manage those resources with Terraform.
- `terraform output` - Displays the values of any outputs defined in the configuration files.

These commands provide users with the ability to manage and maintain their infrastructure using Terraform. By leveraging these commands, users can ensure that their infrastructure is consistent, repeatable, and scalable.

### HCL - HashiCorp Configuration Language

HCL (HashiCorp Configuration Language) is a declarative language used by Terraform to describe infrastructure resources. It is designed to be easy to read and write, and is similar in syntax to other configuration file formats, such as JSON and YAML. HCL is used to define resources in the Terraform configuration files, which are then used by Terraform to manage the infrastructure.

Here is an example of a simple HCL configuration file that defines an AWS EC2 instance:

```
provider "aws" {
  region = "us-east-1"
}

resource "aws_instance" "example" {
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = "t2.micro"
}

```

In this example, the `provider` block specifies that the AWS provider should be used and that the region should be set to `us-east-1`. The `resource` block defines an AWS EC2 instance with the specified AMI and instance type.

HCL supports a variety of data types, including strings, numbers, lists, and maps. It also allows for the use of variables, functions, and modules, which can be used to create reusable configurations and simplify the management of complex infrastructure.

Overall, HCL is a powerful and flexible language that allows users to define and manage infrastructure resources in a simple and declarative way.

HCL (HashiCorp Configuration Language) is used to define resources in the Terraform configuration files. It supports several block types, including:

- `provider` - Configures a specific provider, such as AWS or Google Cloud.
- `resource` - Defines a resource, such as an EC2 instance or an S3 bucket.
- `data` - Retrieves data from a specific provider, such as a list of AWS AMIs.
- `module` - Defines a module, which is a collection of resources that can be reused across configurations.

These blocks can be used to create complex infrastructure configurations in a simple and declarative way.

### Example

In this example, we are using the Google Cloud provider to interact with GCP. The `credentials` attribute is set to the path of the `creds.json` file, which contains the authentication credentials required to access the GCP project. The `project` attribute specifies the ID of the GCP project that we are working with, and the `region` attribute specifies the default region to use for resources.

The `google_storage_bucket` resource creates a new Google Cloud Storage bucket called `data_lake`. The `name` attribute specifies the name of the bucket.

The `google_bigquery_dataset` resource creates a new BigQuery dataset called `data_warehouse`. The `dataset_id` attribute specifies the ID of the dataset, and the `location` attribute specifies the geographic location where the dataset will be stored.

This HCL file can be used with Terraform to create the specified resources on GCP.

```
provider "google" {
  credentials = file("creds.json")
  project     = "my-project-id"
  region      = "us-central1"
}

resource "google_storage_bucket" "data_lake" {
  name = "data_lake"
}

resource "google_bigquery_dataset" "data_warehouse" {
  dataset_id = "data_warehouse"
  location   = "US"
}

```
