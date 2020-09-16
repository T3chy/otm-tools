# otm-tools
Tools for Open Traffic Models

# Installation #

**1.** You will need Java 11.0.5 or later.

**2.** Obtain the OTM jar file. Follow [these instructions](https://ggomes.github.io/otm-sim/installation.html) to either build the OTM jar file or download it.

**3.** Download the `otm-tools` source code. 

## Python ##

**1.** `otm-tools` uses py4j to communicate between OTM and Python code. The `python/javacnct` folder contains the connector class for the Java side. You will need Apache Maven to build this code. Follow [these instructions](https://maven.apache.org/install.html) to install Maven if you do not already have it.

**2.** Copy `otm-tools/setting.xml` to `~/.m2`. If you do not have a folder called `.m2` in your home directory, then run the `mvn` command to create it.

**3.** Build the py4j connector. From `otm-tools/python` folder, run 
```BASH
python setup.py develop
```

**4.** Configure Python. For example, with the `conda` YAML file:
```BASH
conda env create -f otmenv.yml 
```

**5.** Test the installation. Run one of the demos. For example, `demo_run.py` should generate a plot.
```BASH
python demo_run.py
```

## Matlab ##

**1.** Change Matlab's Java version to 11.0.5. This is done by setting the `MATLAB_JAVA` environment variable to the full path of the Java 11 folder. For example, on Linux `echo $MATLAB_JAVA` might return
```BASH
/usr/lib/jvm/jdk-11.0.5
```
Here are some additional links on this topic: [MacOS](https://www.mathworks.com/matlabcentral/answers/103056-how-do-i-change-the-java-virtual-machine-jvm-that-matlab-is-using-on-macos), [Windows](https://www.mathworks.com/matlabcentral/answers/130359-how-do-i-change-the-java-virtual-machine-jvm-that-matlab-is-using-on-windows), [Linux](https://www.mathworks.com/matlabcentral/answers/130360-how-do-i-change-the-java-virtual-machine-jvm-that-matlab-is-using-for-linux).

**2.** Point Matlab to the OTM jar file. Follow these [instructions](https://www.mathworks.com/help/matlab/matlab_external/static-path.html) to include the OTM jar file in Matlab's static class path. You will need to restart Matlab after doing this. 

**3.** Add `otm-tools/matlab` (with subfolders) to Matlab's path. See instructions [here](https://www.mathworks.com/help/matlab/matlab_env/add-remove-or-reorder-folders-on-the-search-path.html). 

**4.** Run `otm-tools/matlab/sample_script.m`. If this runs without error, you have succeeded in installing the package.
