## encrypt and decrypt a vault using the ansible password from LP

```
ansible-vault encrypt group_vars/graphdb-test
ansible-vault decrypt group_vars/graphdb-test

```
Restart after making any changes including creating new users
```
ansible-playbook graphdb-test.yml -i inventories/test -l graphdb-masters -t settings,restart --vault-password-file inventories/vault_pass.txt
```
