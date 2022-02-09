## `Installing Docker on AWS EC2 instance`

Let's check how we can use and install Docker on EC2 instance.

1. First of all create your inventory file on `/etc/ansible`:

```bash
> /etc/ansible/hosts
```

Add your machines on inventory file

2. Now you can check if the host is accessible using `ping module`:

```bash
$ ansible local -m ping
localhost | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "changed": false,
    "ping": "pong"
}
```
