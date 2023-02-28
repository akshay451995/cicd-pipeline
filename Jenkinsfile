pipeline{

    agent any

    stages{

        stage("build docker image from dockerfile"){

            steps{

                script{

                    sh 'docker build -t akshay451995/newimage .'

                }

            }

        }

        stage("push image to docker hub"){

            steps{

                script{

                    withCredentials([string(credentialsId: 'dockerhubp', variable: 'dockerhubp')]) {

                        sh 'docker login -u akshay451995 -p ${dockerhubp}'

}

                sh 'docker push akshay451995/newimage'

               }

            }

        }

        stage("pulling image from dockerhub"){

            steps{

                script{

                    sh 'docker pull akshay451995/newimage'

                }

           }      

        }

        stage("creating a container from the pulled image"){

            steps{

                script{

                    sh 'docker run -dit --name container10 akshay451995/newimage'

                }

            }

        }

    }

}


