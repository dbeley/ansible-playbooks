# ansible-playbooks

## Requirements

- Ansible vault named secret (for sudo):

```
ansible-vault create secret
```

- with this content:

```
ansible_sudo_pass: password_here
```

Telegraf also uses the following variables:
```
telegraf_url: url_here
telegraf_database: name_here
telegraf_user: user_here
telegraf_password: password_here
```

- Host file named hosts :

```
[group1]
host1
[group2]
host2
[group3]
host3 ansigle_ssh_user=username ansible_ssh_pass=password
...
```

- secret.sh script (to decrypt ansible vault) :

```
#!/usr/bin/env bash
echo password_here
```

```
chmod +x secret.sh
```

### Running a playbook

```
ansible-playbook test.yml --vault-password-file secret.sh --ask-pass
```

- --ask-pass : password for ssh without auth
- --ask-become-pass : password for sudo
