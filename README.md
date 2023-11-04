# devops-netology
HM_05-virt-02-iaac

Task 1
-  Увеличение скорости развёртывания инфраструктуры, уменьшение трудозатрат, более высокая степень автоматизации и стабильности системы, а также более простая масштабируемость за счёт того, что описание инфраструктуры в виде конфигурационного файла снижает риски и сводит ошибки к минимуму.
- Идемпотентность - благодаря строгого описания структуры в виде конфигурационного файла появилась возможность добиваться строгой идентичности. 

Task 2
- Низки порог входа, а также отсутствие необходимости установки агентов на целевых хостах, так как работает по протоколу SSH. 
- Push, так как нет необходимости целевым хостам засорять сетевой эфир и тратить процессорное, постоянно опрашивая сервер на новую конфигурацию, что повысит стабильность работы.

Task 3 <br />
`root@vds-924259:/# vagrant -v` <br />
`Vagrant 2.4.0` <br />
 <br />
`root@vds-924259:/# terraform -v` <br />
`Terraform v1.5.7` <br />
`on linux_amd64` <br />
 <br />
`Your version of Terraform is out of date! The latest version` <br />
`is 1.6.3. You can update by downloading from https://www.terraform.io/downloads.html` <br />
 <br />
 <br />
`root@vds-924259:/# ansible --version` <br />
`ansible [core 2.12.10]` <br />
`  config file = /etc/ansible/ansible.cfg` <br />
`  configured module search path = ['/root/.ansible/plugins/modules', '/usr/share/ansible/plugins/modules']` <br />
`  ansible python module location = /usr/lib/python3/dist-packages/ansible` <br />
`  ansible collection location = /root/.ansible/collections:/usr/share/ansible/collections` <br />
`  executable location = /usr/bin/ansible` <br />
`  python version = 3.8.10 (default, May 26 2023, 14:05:08) [GCC 9.4.0]` <br />
`  jinja version = 2.10.1` <br />
`  libyaml = True` <br />
<br />
<br />
Task 4 <br />
В конце 4-ого задания указано следующее:<br />
*Допускается неполное выполнение данного задания если не сможете совладать с Windows.*<br />
<br />
Мне не удалось совладать с заданием, в связи с тем, что под рукой нет машин x86, а только с macOS на ARM процессоре.<br />
Также я пробовал выполнить задание на арендованном x86 сервере под Ubuntu 20.04, но также получил ошибку, как удалось выяснить, связанную с настройкой BIOS, которая мне соответственно не была доступна. Других x86 машин под рукой не оказалось.<br />
<br />
Ниже представлен вывод команд в разных системах:<br />
//на арендованном сервере:<br />
<br />
`root@vds-924259:~# vagrant up` <br />
`Bringing machine 'server1.netology' up with 'virtualbox' provider...` <br />
`==> server1.netology: Importing base box 'bento/ubuntu-20.04'...` <br />
`==> server1.netology: Matching MAC address for NAT networking...` <br />
`==> server1.netology: Checking if box 'bento/ubuntu-20.04' version '202309.09.0' is up to date...` <br />
`==> server1.netology: Setting the name of the VM: server1.netology` <br />
`Vagrant is currently configured to create VirtualBox synced folders with` <br />
`the `SharedFoldersEnableSymlinksCreate` option enabled. If the Vagrant` <br />
`guest is not trusted, you may want to disable this option. For more` <br />
`information on this option, please refer to the VirtualBox manual:` <br />
<br />
`  https://www.virtualbox.org/manual/ch04.html#sharedfolders` <br />
<br />
`This option can be disabled globally with an environment variable:` <br />
<br />
`  VAGRANT_DISABLE_VBOXSYMLINKCREATE=1` <br />
<br />
`or on a per folder basis within the Vagrantfile:` <br />
<br />
`  config.vm.synced_folder '/host/path', '/guest/path', SharedFoldersEnableSymlinksCreate: false` <br />
`==> server1.netology: Clearing any previously set network interfaces...` <br />
`==> server1.netology: Preparing network interfaces based on configuration...` <br />
`    server1.netology: Adapter 1: nat` <br />
`    server1.netology: Adapter 2: hostonly` <br />
`==> server1.netology: Forwarding ports...` <br />
`    server1.netology: 22 (guest) => 20011 (host) (adapter 1)` <br />
`    server1.netology: 22 (guest) => 2222 (host) (adapter 1)` <br />
`==> server1.netology: Running 'pre-boot' VM customizations...` <br />
`==> server1.netology: Booting VM...` <br />
`There was an error while executing `VBoxManage`, a CLI used by Vagrant` <br />
`for controlling VirtualBox. The command and stderr is shown below.` <br />
<br />
`Command: ["startvm", "f108cd0d-e9e4-4cd9-8a14-2861e50e0a36", "--type", "headless"]` <br />
<br />
`Stderr: VBoxManage: error: VT-x is not available (VERR_VMX_NO_VMX)` <br />
`VBoxManage: error: Details: code NS_ERROR_FAILURE (0x80004005), component ConsoleWrap, interface IConsole` <br />
<br />
<br />
//на macOS под ARM (использовалась Ubuntu-22.04-arm64)<br />
//1-ый вариант встречаемой ошибки: <br />
<br />
`cerberus@Mac-mini-ILYA ~ % vagrant up` <br />
`Bringing machine 'server1.netology' up with 'virtualbox' provider...` <br />
`==> server1.netology: Clearing any previously set forwarded ports...` <br />
`==> server1.netology: Clearing any previously set network interfaces...` <br />
`==> server1.netology: Preparing network interfaces based on configuration...` <br />
`    server1.netology: Adapter 1: nat` <br />
`    server1.netology: Adapter 2: hostonly` <br />
`==> server1.netology: Forwarding ports...` <br />
`    server1.netology: 22 (guest) => 20011 (host) (adapter 1)` <br />
`    server1.netology: 22 (guest) => 2222 (host) (adapter 1)` <br />
`==> server1.netology: Running 'pre-boot' VM customizations...` <br />
`==> server1.netology: Booting VM...` <br />
`==> server1.netology: Waiting for machine to boot. This may take a few minutes...` <br />
`    server1.netology: SSH address: 127.0.0.1:2222` <br />
`    server1.netology: SSH username: vagrant` <br />
`    server1.netology: SSH auth method: private key` <br />
`    server1.netology: Warning: Connection reset. Retrying...` <br />
`There was an error while executing `VBoxManage`, a CLI used by Vagrant` <br />
`for controlling VirtualBox. The command and stderr is shown below.` <br />
<br />
`Command: ["showvminfo", "8f2dfbf8-f099-4f4e-898d-ab0b9246ccab", "--machinereadable"]` <br />
<br />
`Stderr: VBoxManage: error: The object is not ready` <br />
`VBoxManage: error: Details: code E_ACCESSDENIED (0x80070005), component SessionMachine, interface IMachine, callee nsISupports` <br />
`VBoxManage: error: Context: "GetHPETEnabled(&f)" at line 1201 of file VBoxManageInfo.cpp` <br />
<br />
<br />
//2-ой вариант встречаемой ошибки: <br />
`cerberus@Mac-mini-ILYA ~ % vagrant up` <br />
`Bringing machine 'server1.netology' up with 'virtualbox' provider...` <br />
`==> server1.netology: Clearing any previously set forwarded ports...` <br />
`==> server1.netology: Clearing any previously set network interfaces...` <br />
`==> server1.netology: Preparing network interfaces based on configuration...` <br />
`    server1.netology: Adapter 1: nat` <br />
`    server1.netology: Adapter 2: hostonly` <br />
`==> server1.netology: Forwarding ports...` <br />
`    server1.netology: 22 (guest) => 20011 (host) (adapter 1)` <br />
`    server1.netology: 22 (guest) => 2222 (host) (adapter 1)` <br />
`==> server1.netology: Running 'pre-boot' VM customizations...` <br />
`==> server1.netology: Booting VM...` <br />
`==> server1.netology: Waiting for machine to boot. This may take a few minutes...` <br />
`    server1.netology: SSH address: 127.0.0.1:2222` <br />
`    server1.netology: SSH username: vagrant` <br />
`    server1.netology: SSH auth method: private key` <br />
`    server1.netology: Warning: Connection reset. Retrying...` <br />
`The guest machine entered an invalid state while waiting for it` <br />
`to boot. Valid states are 'starting, running'. The machine is in the` <br />
`'aborted' state. Please verify everything is configured` <br />
`properly and try again.` <br />
<br />
`If the provider you're using has a GUI that comes with it,` <br />
`it is often helpful to open that and watch the machine, since the` <br />
`GUI often has more helpful error messages than Vagrant can retrieve.` <br />
`For example, if you're using VirtualBox, run `vagrant up` while the` <br />
`VirtualBox GUI is open.` <br />
<br />
`The primary issue for this error is that the provider you're using` <br />
`is not properly configured. This is very rarely a Vagrant issue.` <br />
