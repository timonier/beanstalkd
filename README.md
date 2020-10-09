# README

Beanstalk is a simple, fast work queue

If you like / use this project, please let me known by adding a ★ on the [GitHub repository](https://github.com/timonier/beanstalkd).

## Installation

```sh
# Define installation folder

export INSTALL_DIRECTORY=/usr/bin

# Use local installation

sudo bin/installer install

# Use remote installation

curl --location "https://github.com/timonier/beanstalkd/raw/master/bin/installer" | sudo sh -s -- install
```

__Note__: If you do not define `INSTALL_DIRECTORY`, `installer` will use in `/usr/local/bin`.

## Usage

Run the command `beanstalkd`:

```sh
# See all beanstalkd options

beanstalkd -h

# Run beanstalkd

beanstalkd -V
```

## Links

* [image "timonier/beanstalkd"](https://hub.docker.com/r/timonier/beanstalkd/)
* [kr/beanstalkd](https://github.com/kr/beanstalkd)
* [timonier/beanstalkd](https://github.com/timonier/beanstalkd)
