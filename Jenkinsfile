@Library('shared-library')_
pipeline{
    agent any
    stages{
        stage('db_fetch'){
            steps{
                dbValues("val","val1","val2")
            }
        }
        stage('read yaml'){
            steps{
                script{
                    yamlInput = readYaml file: "${WORKSPACE}/input.yaml"
                    for (value in yamlInput.databases){
                        print(value)
                        for (value1 in yamlInput){
                            print(yamlInput.get(value))
                        }
                    }
                }
            }
        }
    }
}