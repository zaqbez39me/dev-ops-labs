## Version number
Terraform v1.5.3
## Installation
To install the Terraform on ubuntu I ran the following commands:
```bash
sudo apt update && sudo apt upgrade -y 
sudo apt install -y gnupg software-properties-common curl
```
Then I installed the terraform zip from mirror:

https://hashicorp-releases.yandexcloud.net/terraform/1.5.3/

After I used command:
```bash
sudo unzip terraform_1.5.3_linux_386.zip -d /usr/local/bin
```

##  Deployment

### Build

First, I ran commands:

```bash
 mkdir learn-terraform-docker-container
 cd learn-terraform-docker-container
 touch main.tf
 nano main.tf
```

Put the following in the file main.tf:
```
terraform {
  required_providers {
    docker = {
      source = "kreuzwerker/docker"
      version = "~> 3.0.1"
    }
  }
}

provider "docker" {}

resource "docker_image" "nginx" {
  name         = "nginx:latest"
  keep_locally = false
}

resource "docker_container" "nginx" {
  image = docker_image.nginx.image_id
  name  = "tutorial"
  ports {
    internal = 80
    external = 8000
  }
}
```

Then I initialized infrastructure:

```bash
terraform init
```

Formatted and validated infrastructure:

```bash
terraform fmt && terraform validate
```

And lastly created infrastructure entering the value "yes" when it asks for:

```bash
terraform apply
```

To inspect state you can use:

```bash
terraform show
```

## Challenges

The biggest challenge that I met is that terraform and some dependencies are not available in Russia directly.