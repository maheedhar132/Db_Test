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
                    String str = """values """ 
                    yamlInput = readYaml file: "${WORKSPACE}/input.yaml"
                    for (value in yamlInput.databases){
                        def usr = yamlInput.get(value).usr
                        str += """ user = ${usr} """
                    }
                }
                print(str)
            }
        }
    }
}