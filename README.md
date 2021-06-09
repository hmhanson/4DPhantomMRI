# 4DPhantomMRI
4D Deformable Digital Phantom for MRI Sequence Development

Code and files in this repository accompany article by [Hanson et al.](https://onlinelibrary.wiley.com/doi/10.1002/mp.15036)


# Requirements

An XCAT license is required to generate the phantom files.


# Usage

**1. Run XCAT with the three different parameter files**

Note: You may need to edit the parameter files to give the location of XCAT_input_ap.dat and XCAT_input_dia.dat files.


**2. Motion model files**

The motion model component files that correspond to the XCAT output are available [here](https://github.com/UCL/motionModelFromXCATDVFs/releases/tag/v1.0).


**3. Generate input sample and respiration trajectory HD5F files**

Sample jupyter notebook is provided for creating these files.

Respiration trajectory file needs to have the following format: <br />
Group model <br />
Dataset resolution - resolution of the motion model, 1D (ms, mm, mm, mm) <br />
Dataset offset - use this to offset the motion model from the centre if needed, 1D (mm, mm, mm) <br />
Dataset ap - AP component of motion model, 4D (component, x, y, z) <br />
Dataset si - SI component of motion model, 4D (component, x, y, z) <br />
Dataset model_offset - offset component of motion model, 4D (component, x, y, z) <br />
Dataset breathing_trace - time series of AP and SI values, 2D <br />

**4. Add sample and respiration trajectory to JEMRIS simulation .xml file**

E.g.: `<sample name="sample" uri="sample.h5" RespirationTrajectory="motion_model.h5"/>`
 
 
**5. Run the .xml file with JEMRIS**
