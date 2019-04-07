# Former2

![CloudFormation](https://img.shields.io/badge/CloudFormation-100%25-orange.svg)

> Convert your existing cloud resources into CloudFormation / Terraform / Troposphere etc.


![Screenshot](img/screen1.png)

![Screenshot](img/screen2.png)

:exclamation: **CAUTION:** This project is currently in beta stages. Some components may not work as expected.

## Overview

Former2 allows you to generate Infrastructure-as-Code outputs from your existing resources within your AWS account. By making the relevant calls using the AWS JavaScript SDK, Former2 will scan across your infrastructure and present you with the list of resources for you to choose which to generate outputs for.

## Installation

Though [some AWS services](https://github.com/aws/aws-sdk-js/blob/master/SERVICES.md) do not require it, you will need to install the Former2 Helper browser extension in order to have support for all AWS services. The extension exists to bypass a lack of CORS on some services, such as S3 and IAM.

[Install Former2 Helper for Google Chrome](https://chrome.google.com/webstore/detail/former2-helper/fhejmeojlbhfhjndnkkleooeejklmigi)

[Install Former2 Helper for Mozilla Firefox](https://addons.mozilla.org/en-US/firefox/addon/former2-helper/)

Alternatively, you can [download and install](https://github.com/iann0036/former2-helper) the extension yourself.

## Usage

Visit [former2.com](https://former2.com/) to start.

You will need an [IAM key pair](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_access-keys.html) to authenticate your requests. It is recommended that you provide only read access with these credentials and suggest you assign the [ReadOnlyAccess](https://console.aws.amazon.com/iam/home?#/policies/arn:aws:iam::aws:policy/ReadOnlyAccess) policy.

The following outputs are currently supported:

* CloudFormation
* Troposphere
* TypeScript CDK (Cfn Primitives)

With Terraform and IAM policy support coming soon.

## Security

Calls to the AWS service API endpoints are made either directly with the JavaScript SDK or via the browser extension (which also hits endpoints directly). Recording data is kept entirely in memory or on local disk and is never sent over the internet or anywhere else. You should take care to remove any sensitive data (passwords etc.) when sharing your generated code/templates with others.

If you prefer not to use a publicly hosted site to use Former2, you can host your own version by running a HTTP server from the root of the repository. Extension support will also be available if you host on 127.0.0.1:8080, otherwise you can modify the extension source code as needed.