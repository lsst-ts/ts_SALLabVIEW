# SAL LabVIEW Type Definition Support

*This module supports to generate the type definition and wrap the SAL LabVIEW APIs by the LabVIEW import shared library wizard.*

## 1. Platform

- *CentOS 7*
- *LabVIEW 2018 SP1 64-bit Professional Version*

## 2. Run the Software

- *Run the LabVIEW, and open the project of SAL.lvproj in SALTypeGenerator directory.*
- *Execute the main.vi under the TopLevel directory in project.*
- *User can also use the command line as the following: `labview64 path_to_main.vi -- abs_path_to_idl_file abs_path_to_dir_of_lvlib`. For example, `labview64 SALTypeGenerator/TopLevel/main.vi -- /home/ttsai/Documents/github/ts_SALLabVIEW/Tests/TestIdl/sal_Test.idl /home/ttsai/Documents/github/ts_SALLabVIEW/Tests/TestData/`.*
