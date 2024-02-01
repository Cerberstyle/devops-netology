# devops-netology
ter-homeworks_hw-01

Чек лист:<br />
![Pasted Graphic](https://github.com/Cerberstyle/devops-netology/assets/89096235/b4d31dab-4255-431a-80a1-e57506503fa7)


Task1
1. ===<br />
`cerberus@Mac-mini-ILYA src % terraform init` <br />

`Initializing the backend...` <br />

`Initializing provider plugins...` <br />
`- Finding kreuzwerker/docker versions matching "~> 3.0.1"...` <br />
`- Finding latest version of hashicorp/random...` <br />
`- Installing kreuzwerker/docker v3.0.2...` <br />
`- Installed kreuzwerker/docker v3.0.2 (unauthenticated)` <br />
`- Installing hashicorp/random v3.6.0...` <br />
`- Installed hashicorp/random v3.6.0 (unauthenticated)` <br />

`Terraform has created a lock file .terraform.lock.hcl to record the provider` <br />
`selections it made above. Include this file in your version control repository` <br />
`so that Terraform can guarantee to make the same selections by default when` <br />
`you run "terraform init" in the future.` <br />

`╷` <br />
`│ Warning: Incomplete lock file information for providers` <br />
`│ ` <br />
`│ Due to your customized provider installation methods, Terraform was forced to calculate lock file checksums locally for the following providers:` <br />
`│   - hashicorp/random` <br />
`│   - kreuzwerker/docker` <br />
`│ ` <br />
`│ The current .terraform.lock.hcl file only includes checksums for darwin_arm64, so Terraform running on another platform will fail to install these providers.` <br />
`│ ` <br />
`│ To calculate additional checksums for another platform, run:` <br />
`│   terraform providers lock -platform=linux_amd64` <br />
`│ (where linux_amd64 is the platform to generate)` <br />
`╵` <br />

`Terraform has been successfully initialized!` <br />

`You may now begin working with Terraform. Try running "terraform plan" to see` <br />
`any changes that are required for your infrastructure. All Terraform commands` <br />
`should now work.` <br />

`If you ever set or change modules or backend configuration for Terraform,` <br />
`rerun this command to reinitialize your working directory. If you forget, other` <br />
`commands will detect it and remind you to do so if necessary.` <br />

2. personal.auto.tfvars<br />
3. "result": "PpVCCHDer5dnsCjY"<br />
4. ===<br />
`cerberus@Mac-mini-ILYA src % terraform validate` <br />
`╷` <br />
`│ Error: Missing name for resource` <br />
`│ ` <br />
`│   on main.tf line 24, in resource "docker_image":` <br />
`│   24: resource "docker_image" {` <br />
`│ ` <br />
`│ All resource blocks must have 2 labels (type, name).` <br />
`╵` <br />
`╷` <br />
`│ Error: Invalid resource name` <br />
`│ ` <br />
`│   on main.tf line 29, in resource "docker_container" "1nginx":` <br />
`│   29: resource "docker_container" "1nginx" {` <br />
`│ ` <br />
`│ A name must start with a letter or underscore and may contain only letters, digits, underscores, and dashes.` <br />
<br />
Команда ошибок не нашла, но вот некоторые из обнаруженных мною:<br />
a) Строка 24:
`resource "docker_image" {` <br />
Должен быть второй лейбл помимо docker_image
Правильный код:
`resource "docker_image" "nginx"{` <br />
b) Строка 29:
`resource "docker_container" "1nginx" {` <br />
Ошибка в описании одного из лейблов: "1nginx"
Правильный код:
`resource "docker_container" "nginx" {` <br />
c) Строка 31:
`name  = "example_${random_password.random_string_FAKE.resulT}"` <br />
Ошибка в написании параметра
Правильный код:
`name  = "example_${random_password.random_string.result}»` <br />

5. ===<br />
`terraform {` <br />
`  required_providers {` <br />
`    docker = {` <br />
`      source  = "kreuzwerker/docker"` <br />
`      version = "~> 3.0.1"` <br />
`    }` <br />
`  }` <br />
`  required_version = ">=0.13" /*Многострочный комментарий.` <br />
` Требуемая версия terraform */` <br />
`}` <br />
`provider "docker" {}` <br />

`#однострочный комментарий` <br />

`resource "random_password" "random_string" {` <br />
`  length      = 16` <br />
`  special     = false` <br />
`  min_upper   = 1` <br />
`  min_lower   = 1` <br />
`  min_numeric = 1` <br />
`}` <br />

`resource "docker_image" "nginx" {` <br />
`  name         = "nginx:latest"` <br />
`  keep_locally = true` <br />
`}` <br />

`resource "docker_container" "nginx" {` <br />
`  image = docker_image.nginx.image_id` <br />
`  name  = "example_${random_password.random_string.result}"` <br />

`  ports {` <br />
`    internal = 80` <br />
`    external = 9090` <br />
`  }` <br />
`}` <br />

`cerberus@Mac-mini-ILYA src % docker ps` <br />
`CONTAINER ID   IMAGE          COMMAND                  CREATED         STATUS         PORTS                  NAMES` <br />
`29272f63c06c   6c7be49d2a11   "/docker-entrypoint.…"   5 seconds ago   Up 4 seconds   0.0.0.0:9090->80/tcp   example_upkHtF49nS1o7Q0w` <br />
<br />

6.  Ключ -auto-approve используется для применения изменений без подтверждения плана. Данный ключ может быть полезным для внесения быстрых фиксов, незначительных правок, но и также может быть опасным, если над инфраструктурой работают несколько людей.
<br />
`cerberus@Mac-mini-ILYA src % docker ps` <br />
`CONTAINER ID   IMAGE          COMMAND                  CREATED         STATUS         PORTS                  NAMES` <br />
`cb665627d14c   6c7be49d2a11   "/docker-entrypoint.…"   7 seconds ago   Up 6 seconds   0.0.0.0:9090->80/tcp   hello_world` <br />

7. ===<br />
`{` <br />
`  "version": 4,` <br />
`  "terraform_version": "1.5.7",` <br />
`  "serial": 14,` <br />
`  "lineage": "518e06f0-de23-b2ec-6672-38713ebc1d1f",` <br />
`  "outputs": {},` <br />
`  "resources": [],` <br />
`  "check_results": null` <br />
`}` <br />

8. force_remove (Boolean) If true, then the image is removed forcibly when the resource is destroyed.
В нашем случае отсутствует ключ-значение force_remove = true, который отвечает за удаление Docker-образа при terraform destroy.
