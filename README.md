## What's here

- Playbooks that start with `redfish_*` interact with individual iDRACs using the RedFish API.
- Playbooks that start with `cmc_*` interact with the CMC using ssh and `racadm`

## Interacting with the CMC

To check the power status on all systems using:

```
ansible-playbook cmc_racadm_serveraction.yaml
```

To power cycle systems wrk-72 and wrk-74:

```
ansible-playbook cmc_racadm_serveraction.yaml -e 'server_action=powercycle' -l wrk-72,wrk-74
```

To perform a virtual reseat operation on all systems:

```
ansible-playbook cmc_racadm_reseat.yaml
```

Running arbitrary `racadm` commands. Note the extra quoting!

```
ansible-playbook cmc_racadm_command.yaml -e racadm_command='"help getmodinfo"'
```

