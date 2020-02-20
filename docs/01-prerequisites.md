# Prerequisites

## Amazon Web Services

This tutorial leverages the [Amazon Web Services](https://aws.amazon.com/) to streamline provisioning of the compute infrastructure required to bootstrap a Kubernetes cluster from the ground up. It would cost less then $2 for a 24 hour period that would take to complete this exercise.

> The compute resources required for this tutorial exceed the Amazon Web Services free tier. Make sure that you clean up the resource at the end of the activity to avoid incurring unwanted costs. 
## Homebrew install on MAC 
Follow the Homebrew documentation located here [HomeBrew](https://brew.sh/)
Running the following from a command line to install 
```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

## Amazon Web Services CLI

### Install the AWS CLI

Follow the AWS CLI [documentation](https://aws.amazon.com/cli/) to install and configure the `aws` command line utility.

Verify the AWS CLI version using:

```
aws --version
```
For Mac users utilzing brew to install the AWS CLI is far easier 
```
brew install awscli
```
### Set a Default Compute Region and Zone

This tutorial assumes a default compute region and zone have been configured.

Go ahead and set a default compute region:

```
AWS_REGION=us-west-1

aws configure set default.region $AWS_REGION
```


## Running Commands in Parallel with tmux

[tmux](https://github.com/tmux/tmux/wiki) can be used to run commands on multiple compute instances at the same time. Labs in this tutorial may require running the same commands across multiple compute instances, in those cases consider using tmux and splitting a window into multiple panes with `synchronize-panes` enabled to speed up the provisioning process.

> The use of tmux is optional and not required to complete this tutorial.

![tmux screenshot](images/tmux-screenshot.png)

> Enable `synchronize-panes`: `ctrl+b` then `shift :`. Then type `set synchronize-panes on` at the prompt. To disable synchronization: `set synchronize-panes off`.

Next: [Installing the Client Tools](02-client-tools.md)
