# W6D6 notes

## Today

- ML model deployment in the cloud with Amazon Web Services
- NoSQL
- Intro to Big Data tools with Apache Spark

## Core

### Intro to AWS

- ≈100 cloud services
- Elastic Cloud (EC2): Cloud Compute Service
- RDMS: Database migration service

OpenSSH protocol used for connecting to a cloud machine

- ssh: a command for logging into and executing commands on a remote machine
- scp: a command which copies files between hosts on a network

When setting up an EC2 Linux machine, the permissions of the permission certificate `.pem` need to be modified in terminal with `chmod 400 <file>`

#### Start AWS Instance

- From [AWS EC2 Dashboard](https://ca-central-1.console.aws.amazon.com/ec2/v2/home?region=ca-central-1#Home:)
- Set the appropriate region (e.g. ca-central)
- Launch Instance
- Choose Amazon Machine Image (AMI) (e.g. Ubuntu 20.04)
- Choose type (e.g. free tier t2.micro)
- Configure security group (skip steps 3–5)
  - Add inbound rules (e.g. Type: All Traffic, Source: Anywhere-IPv4, this is very insecure) This is the firewall and determines who can connect to your virtual machine. Give your own IP address permission.
- Review and Launch
- Create new key or connect an existing one
  - An existing key may be automatically connected
  - When creating a new permission key
    - save the `.pem` file somewhere secure
    - permissions may need to be modified from the CLI with `chmod 400 <file>`
- Launch
- Connect to AWS instance in CLI
  - `ssh -i /path_to_key/lighthouse.pem  ubuntu@<Public IPv4 DNS>`
    - `.pem` is stored on your computer
    - The Public IPv4 DNS is found at EC2/Instances/\<Instance>/Instance Summary/Public IPv4 DNS

#### Set up Anaconda3 for Data Science

- After connecting to instance 
  - Download Aanaconda3 on the instance
    - CLI `curl -O https://repo.anaconda.com/archive/Anaconda3-2020.02-Linux-x86_64.sh` More recent versions of Anaconda3 do not seem to be compatible with Ubuntu 20.04.
  - Install Anaconda3 on instance
    - CLI `sh Anaconda3-2020.02-Linux-x86_64.sh`
      - hold down `return` to progress through the license agreement and type `yes` to agree
      - Once the installation asks: `Do you wish the installer to initialize Anaconda3 by running conda init?` Select yes
  - Restart instance by typing `exit` and reconnecting

#### Using Jupyter

- Create tmux session
  - Instance CLI `tmux new -s <session_name>`
- Instance CLI `jupyter lab --ip 0.0.0.0 --port 8888 --no-browser`
  - Returned is an html file and two URLs
  - The URLs end with `token=<token>`
- In local browser navigate to `http://<Public IPv4 DNS>:8888/lab`
  >The port number `8888` could be anything but it has to mach in both commands.
  - The first time connecting will prompt for the `<token>` of the previous step
- To disconnect from instance and leave jupyter session running
  - detach from tmux session `[ctrl+b]` `[d]`
  - disconnect from instance `exit`
- To reattach to running jupyter session
  - Instance CLI `tmux a -t <session_name>`

### Tmux

[Getting started with Tmux](https://linuxize.com/post/getting-started-with-tmux/#what-is-tmux)
Reattach to session `tmux attach-session -t <session>` | `tmux a -t <session>`

### NoSQL

- In SQL data is processed into a schema before it is stored (relational)
- In NoSQL raw data is stored and processing happens after (non-relational)
- PostgreSQL stores both relational tables and raw data as JSON
- MongoDB is a NoSQL database

#### MongoDB

[Install](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-os-x/)

- start `brew services start mongodb-community`
- stop `brew services stop mongodb-community`
- activate mongoDB shell after starting the service `mongosh`

### Big data tools

- Apache Spark: big data processing
- Apache Flink: data streaming
- NiFi: data extraction and filtering
- Apache Kafka: multi data stream handling
- Apache Samza: Extends Kafka's capabilities
- Cloud Dataflow: processing
