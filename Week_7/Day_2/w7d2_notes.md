# W7D2 notes

## Today

Building APIs

## Lecture

### Topics

- Review of RESTful APIs
- Introduction to Flask
- Cloud Solutions
  - AWS
  - Google Cloud

## Core

### RESTful API

**RE**presentational **S**tate **T**ransfer-full **A**pplication **P**rogramming **I**nterface

### Flask

Web frameworks

- Django
- bottle
- tornado
- Flask

stackoverflow [Visual Studio Code terminal doesn't activate Conda environment](https://stackoverflow.com/a/69413270/17083205)

Secure Copy from local machine to AWS instance
CLI `spc -i /path/to/your/.pemkey -r /copy/from/path user@server:/copy/to/path`

```Python
flags = {
  '-i' : 'identity_file',
  '-r' : 'recursive'
}
```

Secure File Transfer Protocol (SFTP) with Cyberduck (compatible for MacOS and Windows)
Install

- <https://cyberduck.io/download/>
- On MacOS `brew install --cask cyberduck`
- Cyberduck is free but will promt for donations. To disable the prompt, a registration key can be purchased from the link above or the app can be purchased from the Mac App Store

Connect to AWS EC2 Instance with Cyberduck 8.2.1

- Open Cyberduck
- Open Connection
- SFTP (SSH File Transfer Protocol)
```Python
  Server : <Public IPv4 DNS>,
  Port : 22  # Default,
  Username : 'ec2-user' or 'ubuntu',  # depends on Amazon Machine Image
  Password : <blank>,
  SSH Private Key : /path/to/key.pem
```
- Connect

Once connected, you can disconnect using the Disconnect button at the top of the window.  
Connections are saved in the Bookmarks list


Process adapted from the [tutorial by Jhonny Fransis](https://www.youtube.com/watch?v=hd4oL3WIPVM)