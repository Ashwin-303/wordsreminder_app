node('Windows') {
    try {
        stage('Checkout') {
            checkout scm
            //notifySlack('STARTED')
        }
        /*stage('Navigate to android directory') {

            cd /d D:\demo_app\wordsreminder\android

        }
        */

        stage('Build'){

            if (env.BRANCH_NAME == 'master'){
                D:\demo_app\wordsreminder\android\bundle exec fastlane beta
            }
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