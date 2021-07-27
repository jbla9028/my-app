

node{
    stage('SCM Checkout'){
        git 'https://github.com/jbla9028/my-app.git'
    }
    stage('Read Variable File'){
        def loadProperties(path) {
        properties = new Properties()
        File propertiesFile = new File(path)
        properties.load(propertiesFile.newDataInputStream())
        Set<Object> keys = properties.keySet();
        for(Object k:keys){
        String key = (String)k;
        String value =(String) properties.getProperty(key)
        env."${key}" = "${value}"
        }
    }
    }
    stage('Email Notification'){
        mail bcc: '', body: 'the build was a success', cc: '', from: '', replyTo: '', subject: 'build successful', to: 'jeffreyjblanchard@gmail.com'
    }
}


def loadProperties(path) {
    properties = new Properties()
    File propertiesFile = new File(path)
    properties.load(propertiesFile.newDataInputStream())
    Set<Object> keys = properties.keySet();
    for(Object k:keys){
    String key = (String)k;
    String value =(String) properties.getProperty(key)
    env."${key}" = "${value}"
    }
}