pipeline {
    agent none
    stages {
        stage("build and deploy on Windows and Linux") {
            parallel {
                stage("windows") {
                    agent any
                    stages {
                        stage("build") {
                            steps {
                                echo 'run-build.bat'
                            }
                        }
                        stage("deploy") {
                            steps {
                                echo 'run-deploy.bat'
                            }
                        }
                    }
                }

                stage("linux") {
                    agent any                    }
                    stages {
                        stage("build") {
                            steps {
                                echo './run-build.sh'
                            }
                        }
                        stage("deploy") {
                             steps {
                                echo './run-deploy.sh'
                            }
                        }
                    }
                }
            }
        }
    }
