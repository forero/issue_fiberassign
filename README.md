# issue_fiberassign

After cloning this repo and running the command

```
fiberassign --overwrite --mtl mtl.fits --sky sky.fits --footprint ./tiles.fits --outdir ./
```

the following error appears

```
INFO: Writing tile 0
Traceback (most recent call last):
  File "/global/common/software/desi/cori/desiconda/20190804-1.3.0-spec/code/fiberassign/master/bin/fiberassign", line 151, in <module>
    run_assign_full(assign_args)
  File "/global/common/software/desi/cori/desiconda/20190804-1.3.0-spec/code/fiberassign/master/py/fiberassign/scripts/assign.py", line 400, in run_assign_full
    gfa_targets=gfa_targets, overwrite=args.overwrite)
  File "/global/common/software/desi/cori/desiconda/20190804-1.3.0-spec/code/fiberassign/master/py/fiberassign/assign.py", line 526, in write_assignment_fits
    write_tile(params)
  File "/global/common/software/desi/cori/desiconda/20190804-1.3.0-spec/code/fiberassign/master/py/fiberassign/assign.py", line 337, in write_assignment_fits_tile
    target_rows = [tg_indx[x] for x in assigned_real]
  File "/global/common/software/desi/cori/desiconda/20190804-1.3.0-spec/code/fiberassign/master/py/fiberassign/assign.py", line 337, in <listcomp>
    target_rows = [tg_indx[x] for x in assigned_real]
KeyError: 0

```

Surprisingly things work with 
```
fiberassign --overwrite --mtl mtl.fits --sky sky.fits --footprint ./good_tiles.fits --outdir ./
```

The only difference is that the `TILEID` in `good_tiles.fits` talke values different from `0` or `1`.