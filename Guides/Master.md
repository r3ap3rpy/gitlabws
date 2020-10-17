### Master 

This guidehelps you install the master node which controls the workers/runners, you can have your own master running workers too.

I assume you have root login for this machine and the commands are executed after issuing *sudo su -* as root user.

Let's install two dependencies.

``` bash
yum install postfix -y
```

After install we should enable them.

``` bash
systemctl enable sshd
systemctl enable postfix
```

Now we can start them aswell.

``` bash
systemctl start sshd
systemctl start postfix
```

Now we can use the official installer script to configure ther repo.

``` bash
curl -s https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.rpm.sh | sudo bash
```

Now we are ready to install the gitlab itself.

``` bash
EXTERNAL_URL="http://centosa" 
dnf install gitlab-ce -y
```

If you do not want to set the external url or want to modify it you need to edit this file */etc/gitlab/gitlab.rb* then issue the following command.

``` bash
gitlab-ctl reconfigure
```

For used ports visit [this](https://docs.gitlab.com/omnibus/package-information/defaults.html) site.

Prometheus uses the same port as the cocpit feature so it will not be able to start unless it's either disable or reconfigured.

Create the directory.

``` bash
sudo mkdir /etc/systemd/system/cockpit.socket.d/
```

Edit the */etc/systemd/system/cockpit.socket.d/listen.conf*

``` bash
[Socket]
ListenStream=
ListenStream=10000
```

Allow selinux.

``` bash
semanage port -a -t websm_port_t -p tcp 10000
```

Restart cockpit.

``` bash
systemctl daemon-reload
systemctl restart cockpit.socket
```