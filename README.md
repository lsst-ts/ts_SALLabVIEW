# SAL LabVIEW Type Definition Support

This module supports to generate the type definition and wrap the SAL LabVIEW APIs by the LabVIEW import shared library wizard. The dummies of control, indicator, and name of vi will be replaced based on the IDL file.

## Platform

- CentOS 7
- LabVIEW 2018 SP1 64-bit Professional Version

## Needed Package

- JKI VI Package Manager (vipm)
- Caraya Unit Test Framework (installed by vipm)

## Update the Vi by the Command Line

User can also use the command line as the following:

``` bash
labview64 $path_to_main_vi -- $abs_path_to_idl_file $abs_path_to_dir_of_lvlib
```

For example,

```bash
labview64 SALTypeGenerator/TopLevel/main.vi -- /home/ttsai/Documents/github/ts_SALLabVIEW/Tests/TestIdl/sal_Test.idl /home/ttsai/Documents/github/ts_SALLabVIEW/Tests/TestData/
```

## Run the Software

1. Run the LabVIEW, and open the project of `SALTypeGenerator.lvproj` in the `SALTypeGenerator/` directory.
2. Execute the `main.vi` under the `TopLevel/` directory in project.

## Do the Unit Test

You can run the `testAll.vi` under the `Tests/` directory in `SALTypeGenerator.lvproj` to do the unit tests.

## Do the Performance Evaluation

You can run the `evalPerf.vi` under the `Tests/` directory in `SALTypeGenerator.lvproj` to evaluate the performace. The total time will show on the panel after finishing the wrapping of vi. The test data is under the `Tests/TestData/` and `Tests/TestIdl/` directories.
