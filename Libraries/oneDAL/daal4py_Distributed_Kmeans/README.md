# daal4py Distributed Kmeans Sample
This sample code shows how to train and predict with a distributed k-means model using the python API package daal4py for oneAPI Data Analytics Library. It assumes you have a working version of MPI library installed and it demonstrates how to use software products that can be found in the [Intel oneAPI Data Analytics Library](https://software.intel.com/content/www/us/en/develop/tools/oneapi/components/onedal.html) or [Intel AI Analytics Toolkit powered by oneAPI](https://software.intel.com/content/www/us/en/develop/tools/oneapi/ai-analytics-toolkit.html). 

| Optimized for                     | Description
| :---                              | :---
| OS                                | 64-bit Linux: Ubuntu 18.04 or higher, 64-bit Windows 10, macOS 10.14 or higher
| Hardware                          | Intel Atom® Processors; Intel® Core™ Processor Family; Intel® Xeon® Processor Family; Intel® Xeon® Scalable Performance Processor Family
| Software                          | oneDAL Software Library, Python version 2.7 or >= 3.6, conda-build version >= 3, C++ compiler with C++11 support, Pickle, Pandas, NumPy
| What you will learn               | distributed oneDAL K-Means programming model for Intel CPU
| Time to complete                  | 5 minutes

## What You Will Learn

* How to run a distributed K-Means model with oneDAL daal4py library memory objects.
* How to train a model and save the information to a file
  
## Key implementation details 
This distributed K-means sample code is implemented for CPU using the Python language. The example assumes you have daal4py and scikit-learn installed inside a conda environment, similar to what is delivered with the installation of the Intel(R) Distribution for Python as part of the [oneAPI AI Analytics Toolkit powered by oneAPI](https://software.intel.com/en-us/oneapi/ai-kit). 

## Additional Requirements
You will need a working MPI library. We recommend to use Intel(R) MPI, which is included in the [oneAPI HPC Toolkit](https://software.intel.com/en-us/oneapi/hpc-kit).
 
## License  
This code sample is licensed under MIT license

## How to Build and Run 

oneAPI Data Analytics Library is ready for use once you finish the Intel AI Analytics Toolkit installation, and have run the post installation script.

You can refer to the oneAPI [main page](https://software.intel.com/en-us/oneapi) for toolkit installation, and the Toolkit [Getting Started Guide for Linux](https://software.intel.com/en-us/get-started-with-intel-oneapi-linux-get-started-with-the-intel-ai-analytics-toolkit) for post-installation steps and scripts.

## Activate conda environment With Root Access

Please follow the Getting Started Guide steps (above) to set up your oneAPI environment with the setvars.sh script. Then navigate in linux shell to your oneapi installation path, typically `~/intel/inteloneapi`. Intel Python environment will be activte by default. However, if you activated another environment, you can return with the following command:

#### Linux
```
source activate base
```

## Activate conda environment Without Root Access (Optional)

By default, the Intel AI Analytics toolkit is installed in the inteloneapi folder, which requires root privileges to manage it. If you would like to bypass using root access to manage your conda environment, then you can clone your desired conda environment using the following command:

#### Linux
```
conda create --name user_base --clone base
```

Then activate your conda environment with the following command:

```
source activate user_base
```

## Install Jupyter Notebook
```
conda install jupyter nb_conda_kernels
```


#### _View in Jupyter Notebook_

_Note: This distributed execution cannot be launched from the jupyter notebook version, but you can still view inside the notebook to follow the included write-up and description._

Launch Jupyter Notebook in the directory housing the code example

```
jupyter notebook
```

#### _Run as Python File_

When using daal4py for distributed memory systems, the command needed to execute the program should be executed in a bash shell. To execute this example, run the following command, where the number **4** is chosen as an example and means that it will run on **4 processes**:

Run the Program

`mpirun -n 4 python ./daal4py_Distributed_Kmeans.py`

The output of the script will be saved in the included models and results directories. 

_Note: This code samples focuses on how to use daal4py to do distributed ML computations on chunks of data. The `mpirun` command above will only run on single local node. In order to launch on a cluster, you will need to create a host file on the master node among other steps. The **TensorFlow_Multinode_Training_with_Horovod** code sample explains this process well._

##### Expected Printed Output (with similar numbers, printed 4 times):
```


Here our centroids:


 [[ 5.46000000e+02 -3.26170648e+00 -6.15922494e+00]
 [ 1.80000000e+01 -1.00432059e+01 -8.38198798e+00]
 [ 4.10000000e+02  3.78330964e-01  8.29073839e+00]]

Here is our centroids loaded from file:

 [[ 5.46000000e+02 -3.26170648e+00 -6.15922494e+00]
 [ 1.80000000e+01 -1.00432059e+01 -8.38198798e+00]
 [ 4.10000000e+02  3.78330964e-01  8.29073839e+00]]
Here is our cluster assignments for first 5 datapoints:

 [[1]
 [1]
 [1]
 [1]
 [1]]
[CODE_SAMPLE_COMPLETED_SUCCESFULLY]

```

