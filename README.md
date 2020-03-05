# ansible-playbooks

## Requirements

- Ansible vault named secret :

```
ansible-vault create secret
```

- with this content :

```
ansible_sudo_pass: password_here
```

- Host file named hosts :

```
[group1]
host1
[group2]
host2
...
```

### Running playbook

```
ansible-playbook test.yml --vault-password-file secret.sh --ask-pass
```
