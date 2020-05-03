pipeline {
    agent any
    stages {
stage('scm') {
steps {
    git 'https://github.com/mm-repo/maven_demo.git'
    }
}
    stage('build') {
    steps {
        withMaven(maven : 'MyMavenProject'){
        bat "mvn clean install"
    }
    }
}
    stage('junit') {
steps {
    junit healthScaleFactor: 10.0, testResults: '**/gameoflife-web/target/surefire-reports/*.xml'
    }
}
    stage('deploy') {
steps {
    bat 'copy "C:\\Program Files (x86)\\Jenkins\\workspace\\raghuproject\\gameoflife-web\\target\\*.war" "C:\\Program Files\\Apache Software Foundation\\Tomcat 9.0\\webapps\\"'
    }
}
}
}
