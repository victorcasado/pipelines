pipeline {
    agent none
    stages {
        stage("Sequential Stages") {
            parallel {
                stage("windows") {
                    agent any
                    stages {
                        stage("build") {
                            steps {
                                echo 'run-build.bat'
                            }
                        stage("test") {
                            steps {
                                echo 'test'
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
                    agent any                    
                    stages {
                        stage("build") {
                            steps {
                                echo './run-build.sh'
                            }
                        stage("test") {
                            steps {
                                echo 'test'
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
}
