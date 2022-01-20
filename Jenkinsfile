node ('docker'){
    properties(
        [
            parameters(
                [string(defaultValue: 'False', name: 'prod_run')]
                )

        ]
    )
    stage('Ansible playbook'){
        if (prod_run.equalsIgnoreCase("True")) {
            sh 'ansible-playbook -i inventory/elk/ site.yml --check --diff'
        } else {
            sh 'ansible-playbook -i inventory/elk/ site.yml'
        }
    } 
}