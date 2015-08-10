# jupyterhub

set up a jupyterhub on a remote server

### Prerequisites
1. SSL certificate
2. Private key for the certificate
3. Password/phrase for the key (if using)
4. Github client id
5. Github client id secret
6. Github oauth callback url
 
Items #4-6 should go in secret.yml \(see below\), along with a value for `hub_configproxy_token`, [see Jupyterhub "Getting Started"](https://github.com/jupyter/jupyterhub/blob/master/docs/getting-started.md#security)

### Layout
```
jupyterhub
├── README.md
├── ansible.cfg
├── backup.yml
├── group_vars
│   └── all
│       ├── config.yml
│       └── secret.yml
├── hosts
├── jupyterhub.yml
├── roles
│   ├── exercises
│   │   ├── files
│   │   │   └── data
│   │   │       └── $DATA_FILES
│   │   └── tasks
│   │       └── main.yml
│   ├── jupyterhub
│   │   ├── files
│   │   │   ├── ca-bundle.crt
│   │   │   └── ssl.key
│   │   ├── handlers
│   │   │   └── main.yml
│   │   ├── tasks
│   │   │   └── main.yml
│   │   └── templates
│   │       └── jupyterhub_config.py.j2
│   ├── python
│   │   └── tasks
│   │       └── main.yml
│   └── system
│       └── tasks
│           └── main.yml
└── sync.yml
```

### To Run
* git clone https://github.com/trevormunoz/automation.git
* cd jupyterhub
* edit `hosts` to point at your server
* ansible-playbook -v jupyterhub.yml
* navigate to the public IP of your server and enjoy

### More
* You pdon't need the `sync.yml` playbook or the exercises role to run a jupyterhub server. These are for copying sample data and notebooks to user directories. YMMV.
