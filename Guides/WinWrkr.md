### Windows Worker

The windows worker can be downloaded from [here](https://gitlab-runner-downloads.s3.amazonaws.com/latest/binaries/gitlab-runner-windows-amd64.exe)

It either runs with System account or as specified.

After your download it find a final destination for the executable.

In this case the *C:\\Program Files\\Gitlab Runner\\* folder was found, copy the executable there and navigate there with the administrative command prompt.

Issue the following commands

``` bash
gitlab-runner-windows-amd64.exe install
gitlab-runner-windows-amd64.exe register
```

Follow the usual prompts and enjoy.