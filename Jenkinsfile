pipeline {
    agent any
    stages {
        stage('scm checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/L3O1337/maven-project.git'
            }
        }

        stage('code validate')
        {
            steps {
                withMaven(globalMavenSettingsConfig: '', jdk: 'JAVA_HOME', maven: 'MAVEN_HOME', mavenSettingsConfig: '', traceability: true) {
                    sh 'mvn validate' // validate the code
                }
            }
        }
        stage('code compile')
        {
            steps {
                withMaven(globalMavenSettingsConfig: '', jdk: 'JAVA_HOME', maven: 'MAVEN_HOME', mavenSettingsConfig: '', traceability: true) {
                    sh 'mvn compile' // compile 
                }
            }
        }
        stage('code test')
        {
            steps {
                withMaven(globalMavenSettingsConfig: '', jdk: 'JAVA_HOME', maven: 'MAVEN_HOME', mavenSettingsConfig: '', traceability: true) {
                    sh 'mvn test' // test 
                }
            }
        }
        stage('code build')
        {
            steps {
                withMaven(globalMavenSettingsConfig: '', jdk: 'JAVA_HOME', maven: 'MAVEN_HOME', mavenSettingsConfig: '', traceability: true) {
                    sh 'mvn package' // validate + compile + test + package
                }
            }
        }
    }


    }

