
Launching a job to execute after previous has finished. 

``` 
JOBID=$(sbatch my_job.sh | cut -f 4 -d " ")
sbatch --dependency=$JOBID
```
