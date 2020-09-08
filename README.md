
Following https://zonca.dev/2020/06/kubernetes-jetstream-kubespray.html


## Error: Failed to install providers

Running
```
bash terraform_init.sh
```

gives:
```
Error: Failed to install providers

Could not find required providers, but found possible alternatives:

  hashicorp/openstack -> terraform-providers/openstack

If these suggestions look correct, upgrade your configuration with the
following commands:
    terraform 0.13upgrade ../../contrib/terraform/openstack
    terraform 0.13upgrade ../../contrib/terraform/openstack/modules/compute
    terraform 0.13upgrade ../../contrib/terraform/openstack/modules/ips
    terraform 0.13upgrade ../../contrib/terraform/openstack/modules/network
```

Seems maybe I need to really only use a 0.12.x version of Terraform. Zonca mentions this:

> Install the newest 0.12.x release, I tested with 0.12.26.

```
brew uninstall terraform
brew install terraform@0.12
echo 'export PATH="/usr/local/opt/terraform@0.12/bin:$PATH"' >> /Users/machrist/.bash_profile
source ~/.bash_profile
```
