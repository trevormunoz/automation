# IIIF Image Server (IIPImage)

Set up an instance of [IIPImage](http://iipimage.sourceforge.net/) to serve images according to the [IIIF standard](http://iiif.io/).

### Layout
```
├── README.md
├── Vagrantfile
├── ansible.cfg
├── group_vars
│   └── all
│       └── config.yml
├── hosts
├── iiif-server.yml
└── roles
    ├── iip
    │   └── tasks
    │       └── main.yml
    ├── nginx
    │   ├── files
    │   │   ├── cors.conf
    │   │   └── restrictions.conf
    │   ├── handlers
    │   │   └── main.yml
    │   ├── tasks
    │   │   └── main.yml
    │   └── templates
    │       └── iipsrv.j2
    ├── supervisor
    │   ├── handlers
    │   │   └── main.yml
    │   ├── tasks
    │   │   └── main.yml
    │   └── templates
    │       └── iipsrv.conf.j2
    └── system
        └── tasks
            └── main.yml
```

### To Run

1. `git clone https://github.com/trevormunoz/automation.git`
2. `cd iiif-server`
3. edit `hosts` to point at your server
4. supply the domain name for your server in `config.yml`
5. `ansible-playbook -v iiif-server.yml`

### Notes

This setup expects images to be located on the server at `/data`
