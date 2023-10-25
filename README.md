# devops-netology
HM_02-git-04-tools
- Task 1 <br />


`commit aefead2207ef7e2aa5dc81a34aedf0cad4c32545` <br />
`Author: Alisdair McDiarmid <alisdair@users.noreply.github.com>` <br />
`Date:   Thu Jun 18 10:29:58 2020 -0400` <br />

`    Update CHANGELOG.md` <br />

`diff --git a/CHANGELOG.md b/CHANGELOG.md` <br />
`index 86d70e3e0d..588d807b17 100644` <br />
`--- a/CHANGELOG.md` <br />
`+++ b/CHANGELOG.md` <br />
`@@ -27,6 +27,7 @@ BUG FIXES:` <br />
` * backend/s3: Prefer AWS shared configuration over EC2 metadata credentials by default ([#25134](https://github.com/hashicorp/terraform/issues/25134))` <br />
` * backend/s3: Prefer ECS credentials over EC2 metadata credentials by default ([#25134](https://github.com/hashicorp/terraform/issues/25134))` <br />
` * backend/s3: Remove hardcoded AWS Provider messaging ([#25134](https://github.com/hashicorp/terraform/issues/25134))` <br />
`+* command: Fix bug with global `-v`/`-version`/`--version` flags introduced in 0.13.0beta2 [GH-25277]` <br />
` * command/0.13upgrade: Fix `0.13upgrade` usage help text to include options ([#25127](https://github.com/hashicorp/terraform/issues/25127))` <br />
` * command/0.13upgrade: Do not add source for builtin provider ([#25215](https://github.com/hashicorp/terraform/issues/25215))` <br />
` * command/apply: Fix bug which caused Terraform to silently exit on Windows when using absolute plan path ([#25233](https://github.com/hashicorp/terraform/issues/25233))` <br />
 <br />
- Task 2
- - tag: v0.12.23
- - 56cd7859e0 9ea88f22fc
- - 33ff1c03bb (HEAD, tag: v0.12.24) v0.12.24 <br />
b14b74c493 [Website] vmc provider links <br />
3f235065b9 Update CHANGELOG.md <br />
6ae64e247b registry: Fix panic when server is unreachable <br />
5c619ca1ba website: Remove links to the getting started guide's old location <br />
06275647e2 Update CHANGELOG.md <br />
d5f9411f51 command: Fix bug when using terraform login on Windows <br />
4b6d06cc5d Update CHANGELOG.md <br />
dd01a35078 Update CHANGELOG.md <br />
225466bc3e Cleanup after v0.12.23 release <br />
85024d3100 (tag: v0.12.23) v0.12.23 <br />
- - services *disco.Disco
- - 78b12205587fe839f10d946ea3fdc06719decb05 <br />
52dbf94834cb970b510f2fba853a5b49ad9b1a46 <br />
41ab0aef7a0fe030e84018973a64135b11abcd70 <br />
66ebff90cdfaa6938f26f908c7ebad8d547fea17 <br />
8364383c359a6b738a436d1b7745ccdce178df47
<br />
<br />
<br />
<br />
<br />
HM2 Task 1 item 8

#Будет игнорироваться:
- `**/.terraform/*` - любая директория (в том числе подкаталоги) с именем .terraform
- `*.tfstate` -  любой файл с расширением tfstate (или скрытый файл .tfstate)
- `*.tfstate.*` - любой файл, в названии которого содержится .tfstate.
- `crash.log` - любой файл с данным названием
- `crash.*.log` - любой файл, название которого начинается с crash. и заканчивается .log
- `*.tfvars` - любой файл с расширение .tfvars или одноимённый скрытый файл
- `*.tfvars.json` - любой файл, название которого заканчивается .tfvars.json
- `override.tf` - любой файл с данным названием
- `override.tf.json` - любой файл с данным названием
- `*_override.tf` - любой файл, название которого заканчивается на _override.tf
- `*_override.tf.json` - любой файл, названием которого заканчивается на _override.tf.json
- `.terraformrc` - любой файл с данным названием 
- `terraform.rc` - любой файл с данным названием
