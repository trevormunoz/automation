# wordpress

set up a wordpress dev environment in a vagrant box

* git clone https://github.com/trevormunoz/automation.git
* cd wordpress
* vagrant up
* open http://192.168.33.10 and complete the install process

### Notes

permissions are set wide open on synced folder for the elasticsearch vm so
that elasticsearch can write its data there &mdash; obviously, don't use this in production
