# SAL LabVIEW Type Definition Support

This module supports to generate the type definition and wrap the SAL LabVIEW APIs by the LabVIEW import shared library wizard.
The dummies of control, indicator, and name of vi will be replaced based on the IDL file.

## Platform

- CentOS 7
- LabVIEW 2018 SP1 64-bit Professional Version

## Needed Package

- JKI VI Package Manager 2017 (vipm)
- Caraya Unit Test Framework (installed by vipm, optional, test only)

## Update the SAL LabVIEW Vi by the Command Line

1. Before the use of command line interface, you need to open the TCP/IP connection in LabVIEW first.
The setup can follow [here](https://support.vipm.io/hc/en-us/articles/214135683-Resolving-issues-with-VIPM-connecting-to-LabVIEW).

2. You can use the command line interface as the following (use the absolute file paths of IDL file and SAL LabVIEW library):

``` bash
labview64 $path_to_main_vi -- $abs_path_to_idl_file $abs_path_to_dir_of_lvlib
```

For example,

```bash
labview64 SALTypeGenerator/TopLevel/main.vi -- /home/ttsai/Documents/github/ts_SALLabVIEW/Tests/TestIdl/sal_Test.idl /home/ttsai/Documents/github/ts_SALLabVIEW/Tests/TestData/
```

## Run the Software as a LabVIEW Project

1. Run the LabVIEW, and open the project of `SALTypeGenerator.lvproj` in the `SALTypeGenerator/` directory.
2. Execute the `main.vi` under the `TopLevel/` directory in project.

## Do the Unit Test

1. You can run the `testAll.vi` under the `Tests/` directory in `SALTypeGenerator.lvproj` to do the unit tests by using the Caraya unit test framework.

2. To do the unit tests and generate the JUnit xml report from the command line, do the following command. The generated report (`testReport.xml`) will be in the `Log/` directory.

```bash
labview64 Tests/testAllWithXmlReport.vi
```

## Configuration File

The configuration file is in the `Config/` directory.
At this moment, there is only one file now: `sharedEnum.ini`, which is the mapping of shared enumeration in IDL file.
The section is the name of enumeration and the key is the items in enumeration.
If the field name in IDL file is the same as the section, the related data type will be the enumeration in `sharedEnum.ini`.
If the shared enumeration in IDL file is updated, this configuration file needs to be updated as well.

## Do the Performance Evaluation

You can run the `evalPerf.vi` under the `Tests/` directory in `SALTypeGenerator.lvproj` to evaluate the performace.
The total time will show on the panel after finishing the wrapping of vi.
The test data is under the `Tests/TestData/` and `Tests/TestIdl/` directories.
