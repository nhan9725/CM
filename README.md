# CM
# Register to jenkins master as dev
sudo ansible-playbook  jenkins-slave02.yml --extra-vars="jenkins_slave_name={{ project_name }}-dev jenkins_slave_labels={{ project_name }}-dev"
# Register to jenkins master as prod
sudo ansible-playbook  jenkins-slave02.yml --extra-vars="jenkins_slave_name={{ project_name }}-prod jenkins_slave_labels={{ project_name }}-prod"
# spin up magento dev
sudo ansible-playbook dev-staging.yml --extra-vars='php_version={{ php_version }} project_name={{ project_name }} domain_name={{ domain_name }}'
# spin up magento prod
sudo ansible-playbook dev-staging.yml --extra-vars='php_version={{ php_version }} project_name={{ project_name }} domain_name={{ domain_name }} prod=true'
