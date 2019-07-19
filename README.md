# ansible-playbooks
Playbooks for AWS

Initial codebase for codeigniter framework and two sample application playbooks. The expected installation of these components is handled in an EC2 ASG by an appropriate EC2 launch configuration userdata script invoking local ansible commands:

#!/bin/bash
# Install needed packages to enable an AMI for ansible-pull and use of an IAM
profile
yum install epel-release -y
yum install awscli -y
yum install ansible -y
yum install git -y
ansible-pull -U <YourPlaybookRepo> --full <application_framework_tasks>.yml
ansible-pull -U <YourPlaybookRepo> --full <playbook_tasks_for_all_applications>.yml
