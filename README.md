# cloudformation-helm-demo

Demo project to show a worflow for generation and application of AWS
Cloudformation using Helm as the templating backend.

## Prerequisites

* AWS account
* Properly configured AWS CLI
* A working OpenSSH environment
* [yq](https://github.com/kislyuk/yq)
* An AWS EC2 key references in values/demo.yaml and saved as keyname.pem in the root of this project

## Usage

### Deployment

```
$ bin/deploy demo
```

### Deletion

```
$ bin/delete demo
```

