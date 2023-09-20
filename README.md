# Personal-cheatsheets
## JSONL
* `jq` for simple jsonl commandline operations such as filtering by label: `cat full-dedup.cleaned.split.filtered.register-labels.jsonl  | jq -c 'select(.register_labels.MT | tonumber < 0.3)' > output.jsonl`

## Singularity
Create writable images for venv-like building with --sandbox:
```
BASE_IMAGE=/containers/pytorch-lumi_sles-rocm-5.5.1-python-3.10-pytorch-v2.0.1-apex-torchvision-torchdata-torchtext-torchaudio.sif
singularity build --sandbox my_new_image $BASE_IMAGE

# shell into image to pip install etc.
singularity shell --writable development_img

singularity build production.sif development_img/
```
[Docs](https://docs.sylabs.io/guides/3.7/user-guide/build_a_container.html#sandbox)



## SLURM
### Dependecy jobs
Launching a job to execute after previous has finished.
[link](https://hpc.nih.gov/docs/job_dependencies.html)
```
JOBID=$(sbatch my_job.sh | cut -f 4 -d " ")
sbatch --dependency=$JOBID
```
