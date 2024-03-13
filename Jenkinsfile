pipeline{
    agent { label 'jenkins-woker-node' }
    triggers { pollSCM 'H/5 * * * *' }
    stages{
        stage('clone'){
            steps{
            git url:'https://github.com/NavyaGujjula1209/spring-petclinic.git',
                branch:'main'
            }
        }
        stage('build'){
            steps{
                sh 'mvn clean package'
                archiveArtifacts artifacts: '/spring-petclinic-*.jar'
                junit testResults:'**/TEST-*.xml'
            }
        }
    }
}