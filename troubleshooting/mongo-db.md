# MongoDB

## Prerequisites

### NVM

Download and Run NVM install script.

```sh
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.11/install.sh | bash
```

Activate NVM.

```sh
. ~/.nvm/nvm.sh
```

Verify installation.

```sh
nvm --version
```

### Node.js

List known Node.js versions.

```sh
nvm ls-remote
```

Install the latest LTS version of Node.js.

```sh
nvm install 10.15.0
```

Verify installation.

```sh
node --version
```

## Installation

Source: https://docs.mongodb.com/manual/tutorial/install-mongodb-on-amazon/

Create a `repo` file

```sh
sudo vim /etc/yum.repos.d/mongodb-org-4.0.repo
```

with the following content:

```
[mongodb-org-4.0]
name=MongoDB Repository
baseurl=https://repo.mongodb.org/yum/amazon/2013.03/mongodb-org/4.0/x86_64/
gpgcheck=1
enabled=1
gpgkey=https://www.mongodb.org/static/pgp/server-4.0.asc
```

Install latest stable MongoDB version.

```sh
sudo yum install -y mongodb-org
```

Start MongoDB service.

```sh
sudo service mongod start
```

Verify installation.

```sh
mongo --version
```

## Storage & Security Configuration

Source: https://hackernoon.com/how-to-install-and-secure-mongodb-in-amazon-ec2-in-minutes-90184283b0a1

Create a path to store DB data.

```sh
mkdir -p ~/data/db
```

Give yourself permission to write in that folder.

```sh
chown $USER ~/data/db
```

...TODO

