node{
    stage('SCM Checkout'){
        git 'https://github.com/jbla9028/my-app.git'
    }
    stage('Compile Package'){
        sh 'mvn package'
    }
}