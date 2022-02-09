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

3. Enjoy the Ansible playbook to install the Docker on EC2:

```bash
aws_instance.server (local-exec): PLAY [my playbook] *************************************************************

aws_instance.server (local-exec): TASK [Update all packages to their latest version] *****************************
aws_instance.server: Still creating... [1m20s elapsed]
aws_instance.server (local-exec): ok: [100.25.21.82]

aws_instance.server (local-exec): TASK [Install Docker on the machine] *******************************************
aws_instance.server: Still creating... [1m30s elapsed]
aws_instance.server: Still creating... [1m40s elapsed]
aws_instance.server: Still creating... [1m50s elapsed]
aws_instance.server: Still creating... [2m0s elapsed]
aws_instance.server: Still creating... [2m10s elapsed]
aws_instance.server: Still creating... [2m20s elapsed]
aws_instance.server (local-exec): [WARNING]: Consider using the get_url or uri module rather than running 'curl'.
aws_instance.server (local-exec): If you need to use command because get_url or uri is insufficient you can add
aws_instance.server (local-exec): 'warn: false' to this command task or set 'command_warnings=False' in
aws_instance.server (local-exec): ansible.cfg to get rid of this message.
aws_instance.server (local-exec): changed: [100.25.21.82]

aws_instance.server (local-exec): TASK [Ensure Docker is running] ************************************************
aws_instance.server: Still creating... [2m30s elapsed]
aws_instance.server (local-exec): ok: [100.25.21.82]

aws_instance.server (local-exec): PLAY RECAP *********************************************************************
aws_instance.server (local-exec): 100.25.21.82               : ok=3    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0

aws_instance.server: Creation complete after 2m32s [id=i-08ff88fbbd2d5d285]
```
