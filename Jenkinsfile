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
                        value_Push = yamlInput.get(value).usr
                        export "${value}_pushed = xyz"
                        str += '''echo retriving ${value} user = ${usr} '''
                        str += """ db ${value} """
                    }
                    print(str)
                    echo "$db1_pushed"
                    echo "$db1_Push"
                }
            }
        }
    }
}