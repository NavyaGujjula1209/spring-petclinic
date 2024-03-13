pipeline{
    agent none
    triggers{
        pollscm('* * * * * *')
    }
    stages{
        stage('clone'){
            steps{
            git url:'https://github.com/NavyaGujjula1209/spring-petclinic.git',
                branch:'master'
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