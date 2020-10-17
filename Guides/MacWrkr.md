### MacOS Worker

This guide shows you how you can install and register the worker.

Download the [latest](https://gitlab-runner-downloads.s3.amazonaws.com/latest/binaries/gitlab-runner-darwin-amd64).

Move it to the */usr/local/bin/* folder.
Give it executable permissions.

``` bash
chmod +x /usr/local/bin/gitlab-runner
```

Execute the install and register commands.

``` bash
gitlab-runner install
gitlab-runner execute
```

The service can only run in user mode which means you need to be logged it, you may configure auto-login to make this process easier.
