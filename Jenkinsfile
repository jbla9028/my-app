def loadEnvironmentVariables(path){
    def props = readProperties  file: path
    keys= props.keySet()
    for(key in keys) {
        value = props["${key}"]
        env."${key}" = "${value}"
    }
} 


node{
    stage('SCM Checkout'){
        git 'https://github.com/jbla9028/my-app.git'
    }
    stage('load Vars'){
        path = 'vars.txt'
        loadEnvironmentVariables(path)
        def result = sh(script: 'echo $vars1 $vars2', returnStdout: true)
                echo result
        
    }
    stage('Compile Package'){
        def mvnHome = tool name: 'maven-3', type: 'maven'
        sh "${mvnHome}/bin/mvn package"
    }
    stage('Archive Package'){
        archiveArtifacts artifacts: '**/*.txt',
                   allowEmptyArchive: true,
                   fingerprint: true,
                   onlyIfSuccessful: true
    }
    stage('Email Notification'){
        mail bcc: '', body: 'the build was a success', cc: '', from: '', replyTo: '', subject: 'build successful', to: 'jeffreyjblanchard@gmail.com'
    }
}


