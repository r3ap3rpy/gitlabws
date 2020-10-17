### Linux Worker

In this guide you will learn how to install GitLab Runner on a Ubuntu machine.

First you need to acquire a registration token and the url.

![overview](/Pics/runnerreg.png)

You should visit the official [site](https://gitlab-runner-downloads.s3.amazonaws.com/latest/index.html) to download the appropriate runner for your instance.

The runner depends on *curl* and *git* so we need to install it.

``` bash
apt update -y
apt install curl git
apt --fix-broken install
```

Now you can grab the runner.

``` bash
wget https://gitlab-runner-downloads.s3.amazonaws.com/latest/deb/gitlab-runner_amd64.deb
```

Install the runner.

``` bash
dpkg -i gitlab-runner_amd64.deb
```

Now we can install docker.

``` bash
apt install apt-transport-https ca-certificates curl software-properties-common -y

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"

apt update

apt install docker-ce
```

Check the status.

``` bash
systemctl status docker
```
