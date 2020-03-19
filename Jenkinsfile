node ('terraform_node'){

try {
    stage('checkout') {
        checkout scm
        }

    stage('run unit tests') {


        sh '''
            ansible-playbook tomcat-setup.yml -u ${USER} --extra-vars="hosts=${HOSTS}, ui_manager_user=${UI_MANAGER_USER}, ui_manager_pass=${UI_MANAGER_PASS},ui_admin_username=${UI_ADMIN_USERNAME},ui_admin_pass=${UI_ADMIN_PASS}"
         '''
    }

}
catch (err) {
    print err.getMessage()
    currentBuild.result = 'FAILURE'
}
finally {

    step([
        $class: 'WsCleanup',
        deleteDirs: true,
        patterns: [
            [pattern: '.git/**', type: 'EXCLUDE']
        ]
    ])
}

}
