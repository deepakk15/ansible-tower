Step 1: Update system and add EPEL repository
We need the EPEL repository for this installation. Update your CentOS 7 system and add EPEL repository.
yum -y update
yum -y install https://dl.fedoraproject.org/pub/epel...

Ansible Tower uses Ansible playbook to deploy itself so we also need Ansible installed.
yum -y install ansible vim curl

Step 2: Download Ansible Tower archive
Download the latest Ansible Tower release.
mkdir /tmp/tower && cd  /tmp/tower
curl -k -O https://releases.ansible.com/ansible-...

Extract downloaded archive.
tar xvf ansible-tower-setup-latest.tar.gz

Step 3: Install Ansible Tower
Navigate to the created directory.
cd ansible-tower-setup*/

Edit inventory file to set required credentials.
$ vim inventory

When done, start installation of Ansible Tower.
sudo ./setup.sh

This will invoke Ansible playbook to install Ansible Tower. If successful, the message like this should show at the end.

Step 4: Configure Ansible Tower
You can configure Ansible Tower using:
CLI
RESTful API
Web UI
We will use the Web UI since this is the most preferred method by most new Ansible Tower users. Open your favorite browser point to your Ansible Tower server IP or hostname via https protocol.


Ansible tower login
Login as admin user and password set in the inventory file.

Ansible tower login admin
Once you are logged in, you need to configure Ansible Tower license. Browse to the license file and accept the terms. If you don’t have a license, get trial one here.

ansible tower enter license
