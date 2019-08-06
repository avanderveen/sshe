# `sshe`

Easily SSH into EC2 instances.

Just pick your instance from a list. No need to look up the URL in the AWS Console.

## Installation

### Pre-requisites
* Ruby
* AWS CLI (installed and configured)

### Install
* Put `sshe` somewhere on your path
* Put .sshe.yaml in your home directory
* Configure .sshe.yaml

## Usage

```bash
$ sshe --help
Usage: sshe [options]
    -k, --ssh-key=SSH_KEY            SSH key
    -u, --ssh-user=SSH_USER          SSH user
    -p, --aws-profile=AWS_PROFILE    AWS profile
    -r, --aws-region=AWS_REGION      AWS region
```

## Configuration

Create a `.sshe.yaml` in your working directory or your home directory (`sshe` will look in the current working directory first). See the included `.sshe.yaml` for an example.

Any option passed as a command line argument will override the value from the config file.

### Options

Config Key | CLI Argument | Description
-|-|-
`ssh.key` | `-k`<br/>`--ssh-key` | SSH key to use.<br/>If unspecified, `sshe` will use the key assigned to the instance, under the path `~/.ssh/<assigned key>.pem`.
`ssh.user` | `-u`<br/>`--ssh-user` | SSH user to connect as.<br/>Must be specified either in the config or as a CLI argument.
`aws.profile` | `-p`<br/>`--aws-profile` | AWS profile to use with the CLI.<br/>If unspecified, uses the default profile.
`aws.region` | `-r`<br/>`--aws-region` | AWS region to search in.<br/>If unspecified, uses the default region for the AWS profile.

## Future

* Integration with [AWS Session Manager](https://docs.aws.amazon.com/systems-manager/latest/userguide/session-manager-working-with-sessions-start.html)
* Configuring the SSH user based on the target AMI

## Contributing

Just fire off a PR. There are no rules yet.
