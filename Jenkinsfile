node('Windows') {
    try {
        stage('Checkout') {
            checkout scm
            //notifySlack('STARTED')
        }

        stage('Clean & Prepare') {
            dir("D:\\demo_app\\wordsreminder\\android") {  
                bat './gradlew clean'
            }
        }

        stage('Navigate to android directory') {
                bat 'cd /d D:\\demo_app\\wordsreminder\\android'    
        }

        stage('Build'){

            //if (env.BRANCH_NAME == 'master'){
                dir("D:\\demo_app\\wordsreminder\\android") {
                    bat 'bundle exec fastlane beta'
                }
            //}
            /*if (env.BRANCH_NAME == 'preprod'){
                sh ""
            }
            if (env.BRANCH_NAME == 'develop'){
                sh ""
            }
            */
        }

    }catch(e){
        currentBuild.result = 'FAILED'
        throw e
    }/*finally{
        notifySlack(currentBuild.result)
    }*/
}