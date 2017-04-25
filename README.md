# README

Beanstalk is a simple, fast work queue

## Installation

Copy `bin/beanstalkd` into your executable folder (like `/usr/local/bin` or `$HOME/bin`):

```sh
sudo curl --location --output /usr/local/bin/beanstalkd "https://github.com/timonier/beanstalkd/raw/master/bin/beanstalkd"
sudo chmod +x /usr/local/bin/beanstalkd
```

Linux users can use the [installer](https://github.com/timonier/beanstalkd/blob/master/bin/installer):

```sh
curl --location "https://github.com/timonier/beanstalkd/raw/master/bin/installer" | sudo sh -s install
```

## Usage

Run the command `beanstalkd`:

```sh
# See all beanstalkd options

beanstalkd -h

# Run beanstalkd

beanstalkd -V
```

## Contributing

1. Fork it.
2. Create your branch: `git checkout -b my-new-feature`.
3. Commit your changes: `git commit -am 'Add some feature'`.
4. Push to the branch: `git push origin my-new-feature`.
5. Submit a pull request.

__Note__: Use the script `bin/build` to test your modifications locally.

## Links

* [command "docker run"](https://docs.docker.com/reference/run/)
* [image "timonier/beanstalkd"](https://hub.docker.com/r/timonier/beanstalkd/)
* [kr/beanstalkd](https://github.com/kr/beanstalkd)
* [timonier/dumb-entrypoint](https://github.com/timonier/dumb-entrypoint)
* [timonier/version-lister](https://github.com/timonier/version-lister)
