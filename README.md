Features
--------

- nginx init script to run nginx as as service
- idempotent execution
- helloWorld example server configuration deployment
- abort if OS not Debian

Instructions
-------------------


Edit inventory file
	
	vim test

Update host information there. Currently set to localhost


Update playbook :

	vim test.yml

Update host group name for which to run roles against. Currently configured to run for all hosts listed under the group "loadBalancer"

Finally, fire up the command

	$ ansible-playbook -i test test.yml   --ask-pass -u ubuntu --ask-sudo-pass -v

If you're already root, then

	$ ansible-playbook -i test test.yml  --ask-pass -v