# CM
# Register to jenkins master
sudo ansible-playbook  jenkins-slave02.yml --extra-vars="jenkins_slave_name={{ project_name }}-dev jenkins_slave_labels={{ project_name }}-dev"
# run essential thing for magento
sudo ansible-playbook dev-staging.yml --extra-vars='php_version={{ php_version }} project_name={{ project_name }} domain_name={{ domain_name }}'
