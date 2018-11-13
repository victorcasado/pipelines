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
                    agent {
                        label "linux"
                    }
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
}
