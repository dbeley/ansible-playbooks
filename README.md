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

- A valid hosts.yml file. Use the provided hosts_example.yml file for an example.

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
