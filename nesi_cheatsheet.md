# NeSI Cheatsheet

## [Logging in](nesi.github.io/hpc_training/lessons/maui-and-mahuika/connecting): 

- setup ssh config

```
ssh mahuika
```

password, 2nd factor, password, \<enter>


## File transfer

```
rsync -azvP -e 'ssh -A -J <username>@lander02.nesi.org.nz' <source_dir>  <username>@login.mahuika.nesi.org.nz:<target_dir>
```

## Mahuika running jobs

https://nesi.github.io/hpc_training/lessons/maui-and-mahuika/slurm
