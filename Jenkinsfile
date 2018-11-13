pipeline {
    agent none

    stages {
        stage("build and deploy on Windows and Linux") {
            parallel {
                stage("windows") {
                    agent {
                        label "windows"
                    }
                    stages {
                        stage("build") {
                            steps {
                                bat "run-build.bat"
                            }
                        }
                        stage("deploy") {
                            when {
                                branch "master"
                            }
                            steps {
                                bat "run-deploy.bat"
                            }
                        }
                    }
                }

                stage("linux") {
                    agent {
                        label "linux"
                    }
                    stages {
                        stage("build") {
                            steps {
                                sh "./run-build.sh"
                            }
                        }
                        stage("deploy") {
                             when {
                                 branch "master"
                             }
                             steps {
                                sh "./run-deploy.sh"
                            }
                        }
                    }
                }
            }
        }
    }
}
