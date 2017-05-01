Fast and Accurate 3D PSF Computation for Fluorescence Microscopy
=============
[J. Li](http://www.ee.cuhk.edu.hk/~jzli/), [F. Xue](https://www.researchgate.net/profile/Feng_Xue17) and [T. Blu](http://www.ee.cuhk.edu.hk/~tblu/monsite/phps/index.php), _J. Opt. Soc. Am. A_, accepted.

This set of codes is a fast approximation of 3D PSF model in fluorescernce microscopy, based on Gibson-Lanni model. See [the page](http://www.ee.cuhk.edu.hk/~jzli/MicroscPSF) for details.

**Fast approximation** Current approximation can be 498 times faster than the state-of-the-art tool [PSF Generator](http://bigwww.epfl.ch/algorithms/psfgenerator/) for size 511*511*255. 
    Note the `PSF Generator` uses Java language with mult-threading, while the proposed uses pure Matlab without any compiled routine.


Usage of the Proposed Method
-----------

If the parameters of the microscope are not assigned, default setting will be loaded, see MicroscPSF for details.

```
params.size = [256 256 128];
tic;
PSF = MicroPSF(params);
toc
```
GUI
-----------
![GUI of MicroscPSF](GUI/screenshot.jpg?raw=true "GUI")

Even faster?
-------

The last interpolation step is implementated using mex files, which reduce the time cost 50%.

```
cd Utilities
mex transformation.cpp
```

```
params.size = [256 256 128];
params.fastcom = 1;
tic;
PSF = MicroPSF(params);
toc
```


Update log
-----------
- (04 May, 2017) Add mex implementation, the speed is further improved 2 times!
- (28 Dec, 2016) Refined basis functions. 
- (09 Oct, 2016) Optimized code, the speed has been improved 10 times faster!

