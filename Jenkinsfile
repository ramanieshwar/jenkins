// pipeline{
//         agent {
//             node {
//                  label 'agent1'
//             }
//         }
//          stages {
//              stage('Hello') {
//                         steps {
//                           echo "Hello"
//                         }
//              }
//          }
//          post {
//               always {
//                     echo 'post action'
//               }
//          }
// }

// pipeline {
//       agent none
//            options {
//                disableConcurrentBuilds()
//            }
//             environment {
//                    PROJECT_NAME ="Todoapp"
//                    UBUNTU_SSH_CRED = credentials('UBUNTU-SSH')
//             }
//              triggers { cron('H */4 * * 1-5') }
//               parameters {
//                       string(name: 'COMPONENT', defaultValue:" ", description: 'which component')
//                       text(name: 'COMMENT', defaultValue: '', description: 'write a comment about job why are you running it...')
//                       booleanParam(name: 'FORCE_DEPOLY', defaultValue: true, description: 'check this for force depolyment')
//                       choice(name: 'ENV', choices: ['dev', 'qa', 'prod'], description: 'Pick an environment')
//                       password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
//               }
//               stages {
//                      stage('one') {
//                                    input {
//                                           message "Should we continue?"
//                                           ok "Yes, we should."
//                                          submitter "alice,bob"
//                                          parameters {
//                                               string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
//                                          }
//                                    }
//                                     when {
//                                         branch 'production'
//                                     }
//                                      steps {
//                                          sh "echo ${PROJECT_NAME}"
//                                           sh "env"
//                                      }
//                      }
//                      stage ('two') {
//                                   when {
//                                      beforeAgent true
//                                       branch 'production'
//                                   }
//                                    agent {
//                                         label 'ANSIBLE'
//                                    }
//                                    environment {
//                                       PROJECT_NAME ="Todoapp"
//                                    }
//                                    steps{
//                                       sh "echo ${PROJECT_NAME}"
//                                     }
//                      }
//               }
//       }
// }
 pipeline {
  agent any
   stages {
      stage('parallel Steps') {
         parallel {
            stage('one') {
                 steps {
                    sh 'sleep 100'
                 }
            }
            stage('two') {
                 steps {
                     sh 'sleep 90'
                  }
            }
            stage('three') {
                 steps {
                     sh 'sleep 200'
                 }
            }
         }
      }
   }
 }