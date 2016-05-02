This is the core devops framework.


Starting a new project with this framework:
  - Create a new repository for your project and clone it onto your local dev machine.
  - Clone this framework into a separate folder on your dev machine:
  	$ git clone https://git.portonefive.com/ansible-framework
  - Delete the 'ansible-framework/.git' folder.
  - Copy the remaining contents of the 'ansible-framework' folder into your bare project.
  - cd into 'your_project/ansible' and run 'ansible-galaxy install -r requirements.yml'
    This will install the latest version of the Port One Five Ansible Roles collection.
  - Open the 'ansible/hosts' file and set the URLs and hostnames for this project.
  - Run 'ansible-playbook vagrant.yml' to build a Vagrantfile for this project.
  - Run 'ansible-playbook bamboo.yml' to create a Bamboo build plan for this project.