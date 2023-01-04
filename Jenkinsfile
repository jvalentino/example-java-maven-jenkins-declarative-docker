pipeline {
  agent { label 'maven' }

  stages {
    
    stage('Verify') {
      steps {
          withMaven(mavenSettingsFilePath: 'settings.xml') {
            sh """
              mvn verify \
                  -Drepo.id=github \
                  -Drevision=1.${BUILD_NUMBER}
            """
          }  
        
      }
    } // Publish

    stage('Post') {
      steps {
        script {
          jacoco()
          junit 'target/surefire-reports/*.xml'
          def pmd = scanForIssues tool: [$class: 'Pmd'], pattern: 'target/pmd.xml'
          publishIssues issues: [pmd]
        }
      }
    } // Post

  }
}