pipeline {
    agent any
    stages {
      stage ('CxSCA') {
        steps {
          step([$class: 'CxScanBuilder',
                configAsCode: false,
                dependencyScanConfig: [
                    dependencyScannerType: 'SCA',
                    scaAccessControlUrl: 'https://platform.checkmarx.net',
                    scaCredentialsId: 'checkmarx-user',
                    scaConfigFile: 'build.gradle',
                    scaServerUrl: 'https://api-sca.checkmarx.net',
                    scaTenant: 'cx_ps_apac_test_james_bostock',
                    scaWebAppUrl: 'https://sca.checkmarx.net',
                    isExploitablePath: false
            ],
            projectName: 'jenkins-sca-break-build',
            enableProjectPolicyEnforcement: true,
            waitForResultsEnabled: true,
            hideDebugLogs: false,
            jobStatusOnError: 'UNSTABLE'
          ])
        }
      }
    }
}
