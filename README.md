# web-server-infra
Automating Infrastructure Provisioning using Cloudformation. Configuration of NGINX web server using Ansible

# One command Deployment

In AWS Codepipeline,
The first stage would be infrastructure provisioning stage. After this is successful,  the second stage is triggered with and we can run a Codebuild job which executes the Ansible Playbook -- Instalallation & Config. of Nginx Server

`aws codepipeline start-pipeline-execution --name web_server_install`


# CODEPIPELINE

## STAGE1 - Cloudformation Stage - Infra Provisioning
`infra.yaml` stack is provisioned using AWS Cloudformation

## STAGE2 - Codebuild Job
`ansible-playbook -i aws_ec2.yaml nginx-playbook.yml`