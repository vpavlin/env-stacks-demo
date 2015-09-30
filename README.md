# Env&Stacks Demo Dockerfiles Repository

The purpose of this repository is to show people and let them play with how Docker Hub Automated Builds work. After one of our Env&Stacks WG meetings we came to conclusion we will create and document how to work with this repository to figure out how to properly curate Fedora-Dockerfiles Github repository. Following description will help you understand how to work with branches and directories in the repository to be able to manage a number of Dockerfiles and Atuomated Build for them in Docker Hub.

## Git

Following lines will explain how git can be used to track various versions of Dockerfiles which represent Docker images for various projects.

### Branches

A branch represents an independent line of development. We will use them here to differentiate between various Fedora releases (Fedora 21, Fedora 22, Fedora Rawhide...).

```
$ git branch
  f21
  f22
* master
  rawhide
```

Every branch can then contain slightly different Dockerfile - for example `f21` will use `yum` to install software, but `f22` and `rawhide` will use `dnf` for that.

### Directory Structure

You can find a directory tree for this repository below. Directories, in addition to branches, are used to specify a concrete `Dockerfile` in your repository when you setup an Automated Build.

```
$ tree -L 2
.
├── apache
│   ├── Dockerfile
│   ├── LICENSE
│   ├── README.md
│   └── run-apache.sh
├── postgresql
│   ├── cont-postgresql
│   ├── Dockerfile
│   ├── LICENSE
│   ├── README.md
│   ├── root
│   └── update
├── README.md
└── ruby
    ├── Dockerfile
    ├── LICENSE
    └── README.md

```

As you can see, we have 3 projects: `apache`, `prostgresql`, and `ruby` represented by three directories. These are directly in the root of the repository. In these project directories you can find Dockerfiles and other arbitrary content necessary to successfully build Docker images.

## Docker Hub

It's great to have Dockerfiles and be able to build them locally, but most users don't want to do that - they want to simply pull the image from a registry. This registry will mostly be the Docker Hub.

### Image Repository

Similarly to Github, you can divide your projects on the Docker Hub to organizations and repositories. I created `envstacks` organization for the sake of this demo. You can then create repositories under the organization. Every repository then contains images which are labelled with tags.

For example `apache` project from `f21` branch from this repository can be represented by image like this:

```
https://github.com/vpavlin/env-stacks-demo/tree/f21/apache -> envstacks/apache:f21
```

### Setting up Automated Build (video)

[![How to set up an Automated Build on Docker Hub](https://raw.githubusercontent.com/vpavlin/env-stacks-demo/master/presentation/create-automated-build.png)](https://youtu.be/34c9kERdJ8Y)
