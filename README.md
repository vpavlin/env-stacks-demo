# Env&Stacks Demo Dockerfiles Repository

The purpose of this repository is to show people and let them play with how Docker Hub Automated Builds work. After one of our Env&Stacks WG meetings we came to conclusion we will create and document how to work with this repository to figure out how to properly curate Fedora-Dockerfiles Github repository. Following description will help you understand how to work with branches and directories in the repository to be able to manage a number of Dockerfiles and Atomated Build for them in Docker Hub.

## Branches



## Directory Structure

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

As you can see, we have 3 projects: apache, prostgresql, and ruby represented by three directories. These are directly in the root of the repository. In these project directories you can find Dockerfiles and other arbitrary content neccessary to successfuly build Docker images. 

