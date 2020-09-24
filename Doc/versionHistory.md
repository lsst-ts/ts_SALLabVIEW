# Version History

1.0.6

- Update the **Jenkinsfile.labview** to use the private docker image in CTIO nexus.

1.0.5

- Use the test data from **ts_sal** commit: `13a69b9`.
- Remove the check of private item in `createElements.vi`.

1.0.4

- Rename the **Jenkinsfile** to **Jenkinsfile.labview**.
- Support the shared enumeration from SAL based on the configuration file.
- Remove the restriction of tab/space in the IDL file.

1.0.3

- Run the Caraya unit test and generate the JUnit xml report from the command line.
- Support the Jenkins automatic test.

1.0.2

- Add the Caraya unit test framework.
- Add the unit test cases of reading the IDL file and instantiating the related objects.
- Add the functions to support the unit tests of classes.
- Refactor the `viUpdate.vi` and related functions for the I/O part to improve the performance.
- Rename `SAL.lvproj` to `SALTypeGenerator.lvproj`.
- Remove the unused files.

1.0.1

- Support the command line parser.

1.0.0

- Initial version of module to support the generation of type definition.
