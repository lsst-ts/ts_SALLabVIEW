#!/usr/bin/env groovy

pipeline {

    agent any

    triggers {
        pollSCM('H * * * *')
    }

    environment {
        // XML report path
        XML_REPORT = "Log/testReport.xml"
    }

    stages {

        stage('Unit Tests') {
            // Add the timeout to abort the stage if needed. This is important
            // for the GUI related test (Xvnc or LabVIEW may fail).
            options {
                timeout(time: 20, unit: "SECONDS")
            }

            steps {
                wrap([$class: 'Xvnc']){
                    // Pytest needs to export the junit report.
                    withEnv(["HOME=${env.WORKSPACE}"]) {
                        sh """
                            timeout 10 labview64 Tests/testAllWithXmlReport.vi || true
                        """
                    }
                }
            }
        }
    }

    post {
        always {
            // The path of xml needed by JUnit is relative to
            // the workspace.
            junit "${env.XML_REPORT}"
        }

        cleanup {
            // clean up the workspace
            deleteDir()
        }
    }
}
