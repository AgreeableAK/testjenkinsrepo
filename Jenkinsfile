pipeline { 
    agent any 
 
    tools { 
        maven 'MAVEN_HOME' // Use the Maven tool configured in Jenkins 
    } 
 
    stages { 
        stage('Checkout') { 
            steps { 
                git 'https://github.com/AgreeableAK/testjenkinsrepo.git' 
            } 
        } 
 
        stage('Build') { 
            steps { 
                bat 'mvn clean package' 
            } 
        } 
 
        stage('Test') { 
            steps { 
                bat  'mvn test' 
            } 
        } 
 
        stage('Deploy') { 
            steps { 
                echo 'Deploying application...' 
            } 
        } 
    } 
 
    post { 
        success { 
            echo 'Build and Test Passed!' 
        } 
        failure { 
            echo 'Build Failed!' 
        } 
    } 
} 
