pipeline {

    agent any

    tools {
        gradle "my-gradle.8"
    }

    stages {

        stage("Build jar file") {
                steps {
                    script {
                    
                        if(!fileExists('spring-petclinic')) {
                            echo 'Cloning repo....'
                            sh 'git clone https://github.com/spring-projects/spring-petclinic.git'
                        } else {
                            echo 'repo already exists'
                        }
                        echo "Building jar file....."
                        sh 'cd spring-petclinic; ./gradlew build -x test'
                        echo "jar file built"
                    }
                }
        }

        stage("build image") {
            steps {
                script {
                    echo 'Building Image.......'
                    sh 'docker build -t 3laaharrrr/petclinic:v1 .'
                    echo 'Image built'
                }
            }
        }

        stage("push image") {

            steps {
               script {
                    echo 'Pushing Image.......'

                    withCredentials([
                        usernamePassword(credentialsId: 'dockerhub', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')
                     ]) {
                            sh "echo ${PASSWORD} | docker login -u ${USERNAME} --password-stdin"
                            sh 'docker push 3laaharrrr/petclinic:v1'
                        }

                    echo 'Image pushed'

               }
            }
        }

    }

}
