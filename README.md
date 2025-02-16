# $\mathrm{\omega}_{\rm GDD}^{\rm ML}$

This machine learning model enables fast prediction of the range-separation parameter $\mathrm{\omega}_{\rm GDD}^{\rm ML}$ for the LRC-&omega;PBE functional. Given a molecular system in the form of a .xyz or .sdf file, this program will generate the features used by the model and return the predicted value for the parameter.

The details of this code can be found in the work of DOI: [10.1063/5.0157340](https://doi.org/10.1063/5.0157340)


If provided a system in the XYZ format, the model will rely on xyz2mol (https://github.com/jensengroup/xyz2mol) to obtain an RDKit mol object from its coordinate. In case of a charged system, the second line of the XYZ file must be formatted as to explicitly state it. For instance, the second line of the XYZ file containing a positively charged system would be formatted as:
```
charge=1=
```
For more information on xyz2mol, please see the related article at DOI:10.1002/bkcs.10334, or the github link cited above.

For complexe systems or if the system contains multiple charges, using a SDF file is recommended to ensure this program performs to the best of its ability. The SDF format ensures proper placement of charges or bonds, and can be used directly by RDKit without preprocessing by xyz2mol, which may represents the bottleneck of this code.


## Running the code:

This code requires a number of packages available directly via conda. For simplicity, you may install a conda environment using the .yml file contained within the directory:
```
conda env create -n YOUR_ENV_NAME -f environment.yml
```

Once the environment is installed, activate it and run the code:
 ```
 conda activate YOUR_ENV_NAME
 python3 main.py C60.xyz
 ```
 
 Note that the C60 molecule is given as example, but any path to an XYZ or SDF file will work.

## Dependencies:
```
- Numpy
- RDKit
- Scikit-learn
- XGBoost
- xyz2mol
```
