node 
{   
    try 
    { 
        stage ('Checkout') 
        { 
            deleteDir()
            checkout scm   
        }


        stage ('Compile')
        { 
            //All the compilation steps
        }
        
        stage ('TestRun') 
        {
            sh 'aws ecs list-services --cluster DevopsTest'
            sh 'aws ecs list-tasks --cluster DevopsTest --service-name ecs-simple-service2'
        }
        
    } 
    catch (err)
    {
        //Do something
        throw err
    }
    finally
    {
        /*stage('Email')
        {
            env.ForEmailPlugin = env.WORKSPACE      
            emailext attachmentsPattern: 'TestResults\\*.trx',      
            body: '''${SCRIPT, template="groovy_html.template"}''', 
            subject: currentBuild.currentResult + " : " + env.JOB_NAME, 
            to: 'prasadshivan@gmail.com'
        } */
    }
}
