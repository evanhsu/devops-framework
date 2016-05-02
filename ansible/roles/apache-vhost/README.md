apache-vhost
=========

Add or ensure the existence of a specific vhost on the given servers.
The only customization that this role currently supports is the name 
of the vhost to be created - all other decisions are based off of this
variable.

The following settings are used for the vhost that is created:

- 'project_name' is used as the subdomain
- The documentroot will be '/var/www/vhosts/project_name/public_html'
- The directory will belong to the 'www-data' user
- 'www.' alias is created
- Port 80 and 443 are opened.


Requirements
------------
A running Apache server.


Role Variables
--------------
project_name	- A vhost will be created for 'project_name.hostname'


Dependencies
------------
None


Example Playbook
----------------

- hosts: staging
  roles:
  - { role: apache-vhost, project_name: mycoolwebsite }

Explanation:
If the 'staging' host group includes 'staging1.mydomain.com' and 'staging2.mydomain.com'
then the following vhosts will be created:

	- mycoolwebsite.staging1.mydomain.com
	- mycoolwebsite.staging2.mydomain.com


License
-------
BSD


Author Information
------------------
Evan Hsu
GitHub: evanhsu

