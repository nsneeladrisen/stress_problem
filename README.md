## Problem

Install the software Stress - https://github.com/gersteinlab/STRESS
Stress has a requiremenent called MMTK - http://dirac.cnrs-orleans.fr/MMTK.html, https://github.com/khinsen/mmtk

Installing and importing MMTK is the problem

## System

CS cluster

## Installing MMTK from the mmtk git

Cloning and installing from using setup.py - https://github.com/khinsen/mmtk

Errors generated - 
```
In file included from Src/MMTK_DCD.c:8:0:
Include/MMTK/trajectory.h:12:37: fatal error: Scientific/netcdfmodule.h: No such file or directory
 #include "Scientific/netcdfmodule.h"

error: Command "cc -fno-strict-aliasing -fno-common -dynamic -g -Os -pipe -fno-common -fno-strict-aliasing -fwrapv -DENABLE_DTRACE -DMACOSX -DNDEBUG -Wall -Wstrict-prototypes -Wshorten-64-to-32 -iwithsysroot /usr/local/libressl/include -DNDEBUG -g -fwrapv -Os -Wall -Wstrict-prototypes -DENABLE_DTRACE -pipe -DLIBM_HAS_ERFC -D_LONG64_ -DEXTENDED_TYPES -IInclude -I/Users/neeladrisen/Library/Python/2.7/lib/python/site-packages/numpy/core/include -I/System/Library/Frameworks/Python.framework/Versions/2.7/include/python2.7 -c Src/MMTK_DCD.c -o build/temp.macosx-11.2-x86_64-2.7/Src/MMTK_DCD.o -DNUMPY=1" failed with exit status 1
```

## Installing netcdf

```
pip install netCDF4
```

The problem persists. Additionally the current version of scientific python should have netdf module

## Installing using mmtk_install

The installation section of https://github.com/khinsen/mmtk says unix users can automaticall install using https://github.com/roygroup/mmtk_install
mmtk is installed in /home/neelsen/.local/lib/python2.7/site-packages/.mmtk

## Problem
While running stress

```
  File "./surface_residue/calpha_modes.py", line 23, in <module>
    from MMTK import *
ImportError: No module named MMTK
```

## Tried
Adding the following line tp calpha_modes.py before importing MMTK
```
sys.path.append('/home/neelsen/.local/lib/python2.7/site-packages/.mmtk')
```
