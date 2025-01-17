## Forked !

This is forked repo.

Info about the fork [click here](#fork-information).

##  <img align="left" alt="AWS Copilot CLI" src="./site/content/assets/images/copilot-logo-48-light.svg" width="85" /> AWS Copilot CLI
###### _Build, Release and Operate Containerized Applications on AWS._ 

![latest version](https://img.shields.io/github/v/release/aws/copilot-cli) [![Join the chat at https://gitter.im/aws/copilot-cli](https://badges.gitter.im/aws/copilot-cli.svg)](https://gitter.im/aws/copilot-cli?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

* **Documentation**: [https://aws.github.io/copilot-cli/](https://aws.github.io/copilot-cli/)

The AWS Copilot CLI is a tool for developers to build, release and operate production ready containerized applications on Amazon ECS and AWS Fargate.

Use Copilot to:
* Deploy production-ready, scalable ECS services from a Dockerfile in one command
* Organize all your related microservices in one application
* Set up test and production environments, across regions and accounts
* Set up CI/CD pipelines to release your services to your environments
* Monitor and debug your services from your terminal

<p align="center">
    <img alt="init" src="./site/content/assets/images/init-cropped.gif" width="600"/>
</p>

## Installation

To install with homebrew:
```sh
$ brew install aws/tap/copilot-cli
```
To install manually, we're distributing binaries from our GitHub releases:

<details>
  <summary>Instructions for installing Copilot for your platform</summary>


| Platform | Command to install |
|---------|---------
| macOS | `curl -Lo copilot https://github.com/aws/copilot-cli/releases/latest/download/copilot-darwin && chmod +x copilot && sudo mv copilot /usr/local/bin/copilot && copilot --help` |
| Linux x86 (64-bit) | `curl -Lo copilot https://github.com/aws/copilot-cli/releases/latest/download/copilot-linux && chmod +x copilot && sudo mv copilot /usr/local/bin/copilot && copilot --help` |
| Linux (ARM) | `curl -Lo copilot https://github.com/aws/copilot-cli/releases/latest/download/copilot-linux-arm64 && chmod +x copilot && sudo mv copilot /usr/local/bin/copilot && copilot --help` |
| Windows | `Invoke-WebRequest -OutFile 'C:\Program Files\copilot.exe' https://github.com/aws/copilot-cli/releases/latest/download/copilot-windows.exe` |

</details>


## Getting started

Make sure you have the AWS command line tool installed and have already run `aws configure` before you start.

To get a sample app up and running in one command, run the following:

```sh
$ git clone git@github.com:aws-samples/aws-copilot-sample-service.git demo-app
$ cd demo-app
$ copilot init --app demo                \
  --name api                             \
  --type 'Load Balanced Web Service'     \
  --dockerfile './Dockerfile'            \
  --deploy
```

This will create a VPC, Application Load Balancer, an Amazon ECS Service with the sample app running on AWS Fargate. This process will take around 8 minutes to complete - at which point you'll get a URL for your sample app running! 🚀

## Learning more 

Want to learn more about what's happening? Check out our documentation [https://aws.github.io/copilot-cli/](https://aws.github.io/copilot-cli/) for a getting started guide, learning about Copilot concepts, and a breakdown of our commands. 

## Feedback

Have any feedback at all? 🙏 Drop us an [issue](https://github.com/aws/copilot-cli/issues/new) or join us on [gitter](https://gitter.im/aws/copilot-cli).

We're happy to hear feedback or answer questions, so reach out, anytime!

## Security disclosures

If you think you’ve found a potential security issue, please do not post it in the Issues. Instead, please follow the instructions [here](https://aws.amazon.com/security/vulnerability-reporting/) or email AWS security directly at [aws-security@amazon.com](mailto:aws-security@amazon.com).

## License
This library is licensed under the Apache 2.0 License.

## Fork information

The fork was done to apply only one change: https://github.com/Tipser/copilot-cli/commit/ce4f56abb899dc0f329fc173545857dedc09ef1d

The change is needed for case in Tipser specific setup, where same application, but different envs has to connect to the same VPC.

The changed `copilot-cli` can be used together with GH action: `Tipser/setup-aws-copilot@v3`. 

### How to install ?

Download binaries from release with `-forked` suffix, e.g.`v1.4.0-forked`, or build the tool locally by yourself. 
