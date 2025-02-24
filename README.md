pySuStaIn
============

**Su**btype and **Sta**ging **In**ference, or SuStaIn, is an algorithm for discovery of data-driven groups or "subtypes" in chronic disorders. This repository is the Python implementation of SuStaIn, with the option to describe the subtype progression patterns using either the event-based model or the piecewise linear z-score model.

Installation
============
In main pySuStaIn directory (where you see setup.py, README.txt, LICENSE.txt and all subfolders), run:

```
pip install -e ./awkde
pip install  .
```

This will install the [awkde](https://github.com/mennthor/awkde) package (used for mixture modelling), then the pySuStaIn package.

Troubleshooting
============
If the above install breaks, you may have some interfering packages installed. One way around this would be to create a new [Anaconda](https://www.anaconda.com) environment that uses Python 3.7, then activate it and repeat the installation steps above. To do this, download and install Anaconda, then run:

```
conda create  --name sustain_env python=3.7
conda activate sustain_env
```

To create an environment named `sustain_env`.

Papers
============
- The SuStaIn algorithm: [Young et al. 2018](https://doi.org/10.1038/s41467-018-05892-0) 
- The event-based model: [Fonteijn et al. 2012](https://doi.org/10.1016/j.neuroimage.2012.01.062), (with Gaussian mixture modelling [Young et al. 2014](https://doi.org/10.1093/brain/awu176))
- The piecewise linear z-score model: [Young et al. 2018](https://doi.org/10.1038/s41467-018-05892-0) 
- Implementation in multiple sclerosis (predicting treatment response): [Eshaghi et al. 2020](https://www.medrxiv.org/content/10.1101/19011080v2). The trained model is available [here](https://github.com/armaneshaghi/trained_models_MS_SuStaIn). 
- Application to tau PET data in Alzheimer's disease: [Vogel, et al., 2020](https://doi.org/10.1101/2020.08.20.20176883)

Quotes
============
> _(The authors) have also persuaded me that (SuStaIn is) as clever as e.g. Heiko Braak's brain, (and) can infer longitudinal trajectories based on cross-sectional observations._
> - Anonymous reviewer

Dependencies
============
- Python >= 3.7 
- [NumPy >= 1.18](https://github.com/numpy/numpy)
- [SciPy](https://github.com/scipy/scipy)
- [Matplotlib](https://github.com/matplotlib/matplotlib)
- [Scikit-learn](https://scikit-learn.org) for cross-validation
- [kde_ebm](https://github.com/noxtoby/kde_ebm_open) for mixture modelling (KDE and GMM included)
- [pathos](https://github.com/uqfoundation/pathos) for parallelization
- [awkde](https://github.com/mennthor/awkde) for KDE mixture modelling

Parallelisation
===============
- Added parallelized startpoints

Running different SuStaIn implementations
===============
sustainType can be set to:
  - `mixture_GMM` : SuStaIn with an event-based model progression pattern, with Gaussian mixture modelling of normal/abnormal.
  - `mixture_KDE`:  SuStaIn with an event-based model progression pattern, with Kernel Density Estimation (KDE) mixture modelling of normal/abnormal.
  - `zscore`:       SuStaIn with a piecewise linear z-score model progression pattern.
  
 See `simrun.py` for examples of how to run these different implementations.

SuStaIn Tutorial
===============  
See the jupyter notebook for a tutorial on how to use SuStaIn using simulated data.

Acknowledgement
================
This project has received funding from the European Union’s Horizon 2020 Research and Innovation Programme under Grant Agreements 666992. Application of SuStaIn to multiple sclerosis was supported by the International Progressive MS Alliance (IPMSA, award reference number PA-1603-08175).
