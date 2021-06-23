# terraform-mediawiki

This repository will help you install [MediaWiki](https://www.mediawiki.org/wiki/Manual:Running_MediaWiki_on_Red_Hat_Linux) on AWS in fully automated fashion using Terraform and userdata script

### Execution

#### Setup the machine if provisioning from RHEL linux

```
chmod +x setup.sh
./setup.sh
```
### Acess keys and Secret keys

Change the access and secret keys in main.yml

### Plan

```
terraform plan
```

The terraform plan command creates an execution plan, which lets you preview the changes that Terraform plans to make to your infrastructure

### Apply

```
terraform apply
```

The terraform apply command executes the actions proposed in a Terraform plan.

### After apply

* Wait for couple of minutes before mediawiki is being installed and configured. Use the output displayed on the screen in place of serverip http://serverip/w/index.php
* Select the setup link, and proceed through the setup steps. Choose the MariaDB option when prompted for a database server, and enter the database name, username, and user password you created for MediaWiki.
* Download the LocalSettings.php file when prompted at the end of the setup process, then move it or copy its contents to /var/www/html/w/LocalSettings.php
* Adjust the file’s permissions

```
sudo chmod 664 /var/www/html/w/LocalSettings.php
```
  

### Destroy

```
terraform destroy
```

The terraform destroy command is a convenient way to destroy all remote objects managed by a particular Terraform configuration.

### Useful Links

[MediaWiki Installation](https://www.mediawiki.org/wiki/Manual:Running_MediaWiki_on_Red_Hat_Linux) <br />
[Terraform Installation](https://learn.hashicorp.com/tutorials/terraform/install-cli)
