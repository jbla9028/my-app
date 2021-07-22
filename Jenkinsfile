node{
    stage('SCM Checkout'){
        git 'https://github.com/jbla9028/my-app.git'
    }
    stage('Compile Package'){
        def mvnHome = tool name: 'maven-3', type: 'maven'
        sh "${mvnHome}/mvn package"
    }
}