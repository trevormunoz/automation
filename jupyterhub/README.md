# jupyterhub

set up a jupyterhub on a remote server

### Prerequisites
* SSL certificate
* Private key for the certificate
* Password/phrase for the key (if using)
* Github client id
* Github client id secret
* Github oauth callback url

### To Run
* git clone https://github.com/trevormunoz/automation.git
* cd jupyterhub
* ansible-playbook -v jupyterhub.yml
* navigate to the public IP of your server and enjoy
