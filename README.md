# devops-netology
**HM_05-virt-03-iaac**

**Task 1**
![Снимок экрана 2023-11-10 в 00 11 34](https://github.com/Cerberstyle/devops-netology/assets/89096235/63c977c9-6c69-4bc2-b7c1-afcd1dce428c)


**Task 2**

`(devops) cerberus@Mac-mini-ILYA cloud % terraform apply                                  ` <br />
`yandex_vpc_network.default: Refreshing state... [id=enpodt5lp3uhec5ai3ld]` <br />
`yandex_vpc_subnet.default: Refreshing state... [id=b0c4opb4og88751r6vd8]` <br />
`` <br />
`Note: Objects have changed outside of Terraform` <br />
`` <br />
`Terraform detected the following changes made outside of Terraform since the last "terraform apply" which may have affected this plan:` <br />
`` <br />
`  # yandex_vpc_network.default has been deleted` <br />
`  - resource "yandex_vpc_network" "default" {` <br />
`      - id                        = "enpodt5lp3uhec5ai3ld" -> null` <br />
`        name                      = "net"` <br />
`        # (5 unchanged attributes hidden)` <br />
`    }` <br />
`` <br />
`  # yandex_vpc_subnet.default has been deleted` <br />
`  - resource "yandex_vpc_subnet" "default" {` <br />
`      - id             = "b0c4opb4og88751r6vd8" -> null` <br />
`        name           = "subnet"` <br />
`        # (7 unchanged attributes hidden)` <br />
`    }` <br />
`` <br />
`` <br />
`Unless you have made equivalent changes to your configuration, or ignored the relevant attributes using ignore_changes, the following plan may include actions to` <br />
`undo or respond to these changes.` <br />
`` <br />
`─────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────` <br />
`` <br />
`Terraform used the selected providers to generate the following execution plan. Resource actions are indicated with the following symbols:` <br />
`  + create` <br />
`` <br />
`Terraform will perform the following actions:` <br />
`` <br />
`  # yandex_compute_instance.node01 will be created` <br />
`  + resource "yandex_compute_instance" "node01" {` <br />
`      + allow_stopping_for_update = true` <br />
`      + created_at                = (known after apply)` <br />
`      + folder_id                 = (known after apply)` <br />
`      + fqdn                      = (known after apply)` <br />
`      + gpu_cluster_id            = (known after apply)` <br />
`      + hostname                  = "node01.netology.cloud"` <br />
`      + id                        = (known after apply)` <br />
`      + metadata                  = {` <br />
`          + "ssh-keys" = <<-EOT` <br />
`                centos:ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAICgO911zWiTXIkud11spaxLa5H2hoSBBUJYjRICzqpOq cerberus@Mac-mini-ILYA.local` <br />
`            EOT` <br />
`        }` <br />
`      + name                      = "node01"` <br />
`      + network_acceleration_type = "standard"` <br />
`      + platform_id               = "standard-v1"` <br />
`      + service_account_id        = (known after apply)` <br />
`      + status                    = (known after apply)` <br />
`      + zone                      = "ru-central1-c"` <br />
`` <br />
`      + boot_disk {` <br />
`          + auto_delete = true` <br />
`          + device_name = (known after apply)` <br />
`          + disk_id     = (known after apply)` <br />
`          + mode        = (known after apply)` <br />
`` <br />
`          + initialize_params {` <br />
`              + block_size  = (known after apply)` <br />
`              + description = (known after apply)` <br />
`              + image_id    = "fd8cqujpntm1f5m46kq8"` <br />
`              + name        = "root-node01"` <br />
`              + size        = 10` <br />
`              + snapshot_id = (known after apply)` <br />
`              + type        = "network-hdd"` <br />
`            }` <br />
`        }` <br />
`` <br />
`      + network_interface {` <br />
`          + index              = (known after apply)` <br />
`          + ip_address         = (known after apply)` <br />
`          + ipv4               = true` <br />
`          + ipv6               = (known after apply)` <br />
`          + ipv6_address       = (known after apply)` <br />
`          + mac_address        = (known after apply)` <br />
`          + nat                = true` <br />
`          + nat_ip_address     = (known after apply)` <br />
`          + nat_ip_version     = (known after apply)` <br />
`          + security_group_ids = (known after apply)` <br />
`          + subnet_id          = (known after apply)` <br />
`        }` <br />
`` <br />
`      + resources {` <br />
`          + core_fraction = 100` <br />
`          + cores         = 4` <br />
`          + memory        = 4` <br />
`        }` <br />
`    }` <br />
`` <br />
`  # yandex_vpc_network.default will be created` <br />
`  + resource "yandex_vpc_network" "default" {` <br />
`      + created_at                = (known after apply)` <br />
`      + default_security_group_id = (known after apply)` <br />
`      + folder_id                 = (known after apply)` <br />
`      + id                        = (known after apply)` <br />
`      + labels                    = (known after apply)` <br />
`      + name                      = "net"` <br />
`      + subnet_ids                = (known after apply)` <br />
`    }` <br />
`` <br />
`  # yandex_vpc_subnet.default will be created` <br />
`  + resource "yandex_vpc_subnet" "default" {` <br />
`      + created_at     = (known after apply)` <br />
`      + folder_id      = (known after apply)` <br />
`      + id             = (known after apply)` <br />
`      + labels         = (known after apply)` <br />
`      + name           = "subnet"` <br />
`      + network_id     = (known after apply)` <br />
`      + v4_cidr_blocks = [` <br />
`          + "192.168.101.0/24",` <br />
`        ]` <br />
`      + v6_cidr_blocks = (known after apply)` <br />
`      + zone           = "ru-central1-c"` <br />
`    }` <br />
`` <br />
`Plan: 3 to add, 0 to change, 0 to destroy.` <br />
`` <br />
`Changes to Outputs:` <br />
`  + external_ip_address_node01_yandex_cloud = (known after apply)` <br />
`  + internal_ip_address_node01_yandex_cloud = (known after apply)` <br />
`` <br />
`Do you want to perform these actions?` <br />
`  Terraform will perform the actions described above.` <br />
`  Only 'yes' will be accepted to approve.` <br />
`` <br />
`  Enter a value: yes` <br />
`` <br />
`yandex_vpc_network.default: Creating...` <br />
`yandex_vpc_network.default: Creation complete after 3s [id=enpruki3sast4jv04e6q]` <br />
`yandex_vpc_subnet.default: Creating...` <br />
`yandex_vpc_subnet.default: Creation complete after 1s [id=b0cnrqcvjf9621f9h8k3]` <br />
`yandex_compute_instance.node01: Creating...` <br />
`yandex_compute_instance.node01: Still creating... [10s elapsed]` <br />
`yandex_compute_instance.node01: Still creating... [20s elapsed]` <br />
`yandex_compute_instance.node01: Still creating... [30s elapsed]` <br />
`yandex_compute_instance.node01: Creation complete after 38s [id=ef37vj7k5in4godcibe4]` <br />
`` <br />
`Apply complete! Resources: 3 added, 0 changed, 0 destroyed.` <br />
`` <br />
`Outputs:` <br />
`` <br />
`external_ip_address_node01_yandex_cloud = "51.250.37.61"` <br />
`internal_ip_address_node01_yandex_cloud = "192.168.101.27"` <br />

![Pasted Graphic](https://github.com/Cerberstyle/devops-netology/assets/89096235/1e76ec96-57b8-4751-9682-f438bdb4412e)

**Task 3**


**Task 4**
