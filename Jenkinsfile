pipeline 
{
    agent any

    stages 
    {
        stage ('Build docker image') 
        {
            steps 
            {
                script{
                    sh 'docker build -t html2 .'
                }
            }
        }
        stage('Build docker Container') 
        {
            steps 
            {
                script{
                    sh 'docker run -d --name html2 -p 8989:80 html2 '
                }
            }
        }
    }
    post 
    {   
        always
        {
            emailext body: 'Summary', subject: 'Pipeline status', to: 'ahsan@gmail.com'
        }

    }
}