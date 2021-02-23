# terraform-docs

[![Build Status](https://github.com/terraform-docs/terraform-docs/workflows/ci/badge.svg)](https://github.com/terraform-docs/terraform-docs/actions) [![GoDoc](https://pkg.go.dev/badge/github.com/terraform-docs/terraform-docs)](https://pkg.go.dev/github.com/terraform-docs/terraform-docs) [![Go Report Card](https://goreportcard.com/badge/github.com/terraform-docs/terraform-docs)](https://goreportcard.com/report/github.com/terraform-docs/terraform-docs) [![Codecov Report](https://codecov.io/gh/terraform-docs/terraform-docs/branch/master/graph/badge.svg)](https://codecov.io/gh/terraform-docs/terraform-docs) [![License](https://img.shields.io/github/license/terraform-docs/terraform-docs)](https://github.com/terraform-docs/terraform-docs/blob/master/LICENSE) [![Latest release](https://img.shields.io/github/v/release/terraform-docs/terraform-docs)](https://github.com/terraform-docs/terraform-docs/releases)

![terraform-docs-teaser](./images/terraform-docs-teaser.png)

## What is terraform-docs

A utility to generate documentation from Terraform modules in various output formats.

```bash
terraform-docs asciidoc ./my-terraform-module          # generate asciidoc table
terraform-docs asciidoc table ./my-terraform-module    # generate asciidoc table
terraform-docs asciidoc document ./my-terraform-module # generate asciidoc document
terraform-docs json ./my-terraform-module              # generate json
terraform-docs markdown ./my-terraform-module          # generate markdown table
terraform-docs markdown table ./my-terraform-module    # generate markdown table
terraform-docs markdown document ./my-terraform-module # generate markdown document
terraform-docs pretty ./my-terraform-module            # generate colorized pretty
terraform-docs tfvars hcl ./my-terraform-module        # generate hcl format of terraform.tfvars
terraform-docs tfvars json ./my-terraform-module       # generate json format of terraform.tfvars
terraform-docs toml ./my-terraform-module              # generate toml
terraform-docs xml ./my-terraform-module               # generate xml
terraform-docs yaml ./my-terraform-module              # generate yaml
```

## Documentation

- **Users**
  - Read the [User Guide] to learn how to use terraform-docs
  - Read the [Formats Guide] to learn about different output formats of terraform-docs
  - Refer to [Config File Reference] for all the available configuration options
- **Developers**
  - Read [Contributing Guide] before submitting a pull request

Visit [our webside] for all documentation.

## Installation

The latest version can be installed using `go get`:

```bash
GO111MODULE="on" go get github.com/terraform-docs/terraform-docs@v0.11.2
```

**NOTE:** to download any version **before** `v0.9.1` (inclusive) you need to use to
old module namespace (`segmentio`):

```bash
# only for v0.9.1 and before
GO111MODULE="on" go get github.com/segmentio/terraform-docs@v0.9.1
```

**NOTE:** please use the latest go to do this, we use 1.15.6 but ideally go 1.14 or greater.

This will put `terraform-docs` in `$(go env GOPATH)/bin`. If you encounter the error
`terraform-docs: command not found` after installation then you may need to either add
that directory to your `$PATH` as shown [here] or do a manual installation by cloning
the repo and run `make build` from the repository which will put `terraform-docs` in:

```bash
$(go env GOPATH)/src/github.com/terraform-docs/terraform-docs/bin/$(uname | tr '[:upper:]' '[:lower:]')-amd64/terraform-docs
```

Stable binaries are also available on the [releases] page. To install, download the
binary for your platform from "Assets" and place this into your `$PATH`:

```bash
curl -Lo ./terraform-docs.tar.gz https://github.com/terraform-docs/terraform-docs/releases/download/v0.11.2/terraform-docs-v0.11.2-$(uname)-amd64.tar.gz
tar -xzf terraform-docs.tar.gz
chmod +x terraform-docs
mv terraform-docs /some-dir-in-your-PATH/terraform-docs
```

**NOTE:** Windows releases are in `ZIP` format.

If you are a Mac OS X user, you can use [Homebrew]:

```bash
brew install terraform-docs
```

or

```bash
brew install terraform-docs/tap/terraform-docs
```

Windows users can install using [Scoop]:

```bash
scoop bucket add terraform-docs https://github.com/terraform-docs/scoop-bucket
scoop install terraform-docs
```

or [Chocolatey]:

```bash
choco install terraform-docs
```

Alternatively you also can run `terraform-docs` as a container:

```bash
docker run quay.io/terraform-docs/terraform-docs:0.11.2
```

**NOTE:** Docker tag `latest` refers to _latest_ stable released version and `edge`
refers to HEAD of `master` at any given point in time.

## Community

- Discuss terraform-docs on [Slack]

## Maintenance

This project was originally developed by [Segment] but now is no longer maintained
by them. Instead, [Martin Etmajer] from [GetCloudnative] and [Khosrow Moossavi] from
[CloudOps] are maintaining the project with help from these awesome [contributors].
Note that maintainers are unaffiliated with Segment.

## License

MIT License - Copyright (c) 2021 The terraform-docs Authors.

[User Guide]: ./docs/USER_GUIDE.md
[Formats Guide]: ./docs/reference/terraform-docs.md
[Config File Reference]: ./docs/reference/config-file.md
[Contributing Guide]: CONTRIBUTING.md
[our webside]: https://terraform-docs.io/
[here]: https://golang.org/doc/code.html#GOPATH
[releases]: https://github.com/terraform-docs/terraform-docs/releases
[Homebrew]: https://brew.sh
[Scoop]: https://scoop.sh/
[Chocolatey]: https://www.chocolatey.org
[Slack]: https://slack.terraform-docs.io/
[Segment]: https://github.com/segmentio/
[Martin Etmajer]: https://github.com/metmajer
[GetCloudnative]: https://github.com/getcloudnative
[Khosrow Moossavi]: https://github.com/khos2ow
[CloudOps]: https://github.com/cloudops
[contributors]: AUTHORS
