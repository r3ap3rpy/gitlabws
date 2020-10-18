### Welcome to the macOS Custom exec

This guide relies on 4 files found in the *customexec* folder:

* config_exec.sh
* prepare_exec.sh
* run_exec.sh
* cleanup_exec.sh

The default config for the executor can be found in the same folder aswell called *custom_config.toml*

The *config.toml* is extended by the following values.

``` bash
 builds_dir = "/Users/r3ap3rpy/.gitlab-runner/builds"
  cache_dir = "/Users/r3ap3rpy/.gitlab-runner/cache"
  
    config_exec = "/Users/r3ap3rpy/config_exec.sh"
    prepare_exec = "/Users/r3ap3rpy/prepare_exec.sh"
    run_exec = "/Users/r3ap3rpy/run_exec.sh"
    cleanup_exec = "/Users/r3ap3rpy/cleanup_exec.sh"
```