# cloudformation-helm-demo

Demo project to show a worflow for generation and application of AWS
Cloudformation using Helm as the templating backend.

## Prerequisites

* AWS account
* Properly configured AWS CLI
* A working OpenSSH environment
* [yq](https://github.com/kislyuk/yq)
* An AWS EC2 key as referenced in `values/demo.yaml` and saved as `<key_name>.pem` in the root of this project

## Usage

### Help

```
$ bin/deploy --help
USAGE: bin/deploy [--profile=PROFILE] [--action=ACTION]

PROFILE must match a YAML file in values/ - defaults to "demo"
ACTION is a cloudformation action - valid values are "create" and "delete"
       default id "create"

--help  : shows this message
--debug : enables trace logging
```

### Deployment

```
$ bin/deploy --profile=demo
```

### Deletion

```
$ bin/deploy --action=delete --profile=demo
```

### Notes / Caveats

* Generates a valid template BUT
* Provided example code did not include "AWSRegionArch2AMI" Mapping, so lookup of ImageId fails
* I only learned Cloudformation this evening
* CF's defaulting syntax is used to set values. From what I can tell this should be done as a separate parameters file or explicit args to the AWS CLI.

