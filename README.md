# Personal-cheatsheets
## JSONL
* `jq` for simple jsonl commandline operations such as filtering by label: `cat full-dedup.cleaned.split.filtered.register-labels.jsonl  | jq -c 'select(.register_labels.MT | tonumber < 0.3)' > output.jsonl`

## bash

# Supercomputers:
- Puhti: ssh yourname@puhti.csc.fi 
  - gpu: Nvidia V100, 32G 
  - only machine that let's you have an interactive gpu-node with `sinteractive`
- Mahti: ssh yourname@mahti.csc.fi
  - gpu: Nvidia A100, 40G 
- Lumi: ssh -i ./known_hosts_lumi yourname@lumi.csc.fi  
  - gpu: AMD MI1250X, 128G

# Basic notes about usage:
- When you login to any of these computers, you are logging in to a LOGIN-node. Do not make heavy computations on login-nodes, because it is a shared node with other users. 
- Use-cases for LOGIN-nodes: 
  - creating virtual environments
  - installing software
  - downloading data
  - ... basic filesystem operations
- Use interactive shells to compute nodes to do:
  - data preprocessing 
  - quick prototyping of scripts
  - anything you ask yourself "is this too heavy to be done on a login node"
  - NOTE: computation nodes only text editor is vi!
  -
# SLURM ja lustre:

- sbatch: https://slurm.schedmd.com/sbatch.html
  - runs slurm-launch scripts that requires specifying resource requests, starting with `#SBATCH`
  - 
- sinteractive:
  - gets an interactive
- salloc


# CSCs own commands
`csc-workspaces` -- shows your capacity `used G / total G` and file counts `used n / total n`

`csc-projects` -- shows your projects and remaining "money", remaining billing units 

# CSC:n module-system

# Singularity

# DeepSpeed 



