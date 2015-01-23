Instructions
-------------------

Edit inventory file
	
	vim test

Update host information there, it not localhost


Update playbook :

	vim test.yml

Update host name for which to run roles

Finally, fire up the command

	$ ansible-playbook -i test test.yml   --ask-pass -u ubuntu --ask-sudo-pass -v