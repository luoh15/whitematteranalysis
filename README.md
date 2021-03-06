whitematteranalysis
===================

# Synopsis
White Matter Analysis provides clustering and tractography analysis tools.

It implements algorithms from publications listed here:
http://projects.iq.harvard.edu/whitematteranalysis/publications

Also see the github.io page here:
http://slicerdmri.github.io/whitematteranalysis/

**Please cite the following papers:**

    O'Donnell, LJ., and Westin, CF. Automatic tractography segmentation
    using a high-dimensional white matter atlas. Medical Imaging,
    IEEE Transactions on 26.11 (2007): 1562-1575.

    O’Donnell LJ, Wells III WM, Golby AJ, Westin CF. Unbiased groupwise registration of white matter tractography.
    In International Conference on Medical Image Computing and Computer-Assisted Intervention 2012 Oct 1 (pp. 123-130).
    Springer Berlin Heidelberg.

**For projects using Slicer and SlicerDMRI please also include the following text (or similar) and citations:**

* How to cite the [Slicer platform](http://wiki.slicer.org/slicerWiki/index.php/CitingSlicer)
* An example of how to cite SlicerDMRI (modify the first part of the sentence according to your use case):

    "We performed diffusion MRI tractography and/or analysis and/or visualization in 3D Slicer (www.slicer.org) via the SlicerDMRI project (dmri.slicer.org) (Norton et al. 2017)."
    
    - [Isaiah Norton, Walid Ibn Essayed, Fan Zhang, Sonia Pujol, Alex Yarmarkovich, Alexandra J. Golby, Gordon Kindlmann, Demian Wassermann, Raul San Jose Estepar, Yogesh Rathi, Steve Pieper, Ron Kikinis, Hans J. Johnson, Carl-Fredrik Westin and Lauren J. O'Donnell. SlicerDMRI: Open Source Diffusion MRI Software for Brain Cancer Research. Cancer Research 77(21), e101-e103, 2017.](http://cancerres.aacrjournals.org/content/77/21/e101)

# Installation
## 1. Download whitematteranalysis from github. 

      git clone https://github.com/SlicerDMRI/whitematteranalysis.git
      
## 2. Install python. 
Anaconda is a nice option since it has VTK and scipy.
First install anaconda from http://continuum.io/downloads, then run: 

      conda install vtk=5.10.1

## 3. Install the following python packages (dependencies).

Once you have anaconda installed, run: 

      pip install joblib

Other distributions, or self-compiled, Python will require installation of scipy.stats, scipy.optimize, and statsmodels, depending on the usage.

Note: If you decide to use another python that does not already have VTK, you can compile VTK.
* VTK: http://www.vtk.org/Wiki/VTK/Building
* http://www.vtk.org/Wiki/VTK/Git/Download

You will need to compile it with python wrapping. VTK_WRAP_PYTHON must be on.
Make sure that at configure time it finds the version of python that you want to use for this project. You may need to toggle t for advanced mode in ccmake. I have something like this when I run:
     cd VTK-build
     ccmake ../VTK

       PYTHON_EXECUTABLE                /Users/lauren/anaconda/bin/python            
       PYTHON_EXTRA_LIBS                                                             
       PYTHON_INCLUDE_DIR               /Users/lauren/anaconda/pkgs/python-2.7.4-1/in
       PYTHON_LIBRARY                   /Users/lauren/anaconda/lib/libpython2.7.dylib
       PYTHON_UTIL_LIBRARY              /usr/lib/libutil.dylib   

Note this requires both git and cmake. More information is at vtk.org.
To install your compiled vtk into your python:
     cd VTK-build/Wrapping/Python
     python setup.py install

## 4. Install WhiteMatterAnalysis into your python in the standard way.

     cd whitematteranalysis
     python setup.py install

## 5. Documentation
* Please see the wiki for usage instructions of whitematteranalysis.

    https://github.com/SlicerDMRI/whitematteranalysis/wiki

* Please see the following page for instructions of applying a pre-provided anatomically curated white matter atlas, along with the computation tools provided in whitematteranalysis, to perform subject-specific tractography parcellation. 

    https://dmri.slicer.org/atlases


