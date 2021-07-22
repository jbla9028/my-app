node{
    stage('SCM Checkout'){
        git 'https://github.com/jbla9028/my-app.git'
    }
    stage('Compile Package'){
        def mvnHome = tool name: 'maven-3', type: 'maven'
        sh "${mvnHome}/bin/mvn package"
    }
    stage('Email Notification'){
        mail bcc: '', body: 'the build was a success', cc: '', from: '', replyTo: '', subject: 'build successful', to: 'jeffreyjblanchard@gmail.com'
    }
}