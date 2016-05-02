#Core devops framework
*This should be the bare starting point for every project.

##Prerequisites:
  * You must have Git installed:
  	`apt-get update`
  	`apt-get -y install git`
  * You must have Ansible installed:
  	`sudo apt-get install software-properties-common`
	`sudo apt-add-repository ppa:ansible/ansible`
	`sudo apt-get update`
	`sudo apt-get install ansible`

##Starting a new project with this framework:
  1. Create a new repository for your project and clone it onto your local dev machine.
  2. Clone this framework into a separate folder on your dev machine:
	`git clone https://git.portonefive.com/devops-framework.git`
  3. Delete the 'devops-framework/.git' folder.
  4. Copy the remaining contents of the 'devops-framework' folder into your bare project.
  5. Open the 'ansible/inventory' directory and set the URLs and hostnames for the local, staging, and production environments for this project.
  6. Build a Vagrantfile for this project:
	`ansible-playbook vagrant.yml -i inventory/local`
  7. Configure the Staging Server for this project:
	`ansible-playbook configure_vhost.yml web -i inventory/staging`
  8. Create a new Bamboo build project:
  	`ansible-playbook bamboo.yml build_server -i inventory/dev`

##Migrating a WordPress database with find-and-replace:
  You can move a the structure and content from a `source_db` to a `dest_db` with the following command:
  `ansible-playbook copy_db database -e replace_this=staging.mydomain.com with_this=production.mydomain.com`
  