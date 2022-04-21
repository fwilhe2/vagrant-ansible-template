# vagrant-ansible-template

Run Playbook in vm:

```
vagrant up
```

or

```
vagrant provision
```

Run Playbook locally:

```
ansible-playbook --ask-become-pass --connection=local --inventory localhost, -vv playbook.yaml
```