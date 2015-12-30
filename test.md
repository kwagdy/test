# This stack show how to install php5 on your VM
# First we update packages using apt-get update
# Then we install php5 using apt-get install php5

provider:
  aws:
    access_key: '${var.aws_access_key}'
    secret_key: '${var.aws_secret_key}'
resource:
  aws_instance:
    php_example:
      tags:
        Name: '${var.koding_user_username}-${var.koding_group_slug}'
      instance_type: t2.nano
      ami: ''
      user_data: |
          apt-get update
          apt-get install php5
