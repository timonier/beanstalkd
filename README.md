# README

## Installation

Pull the image `timonier/beanstalkd`:

```sh
# Get the latest image (version 1.10)
docker pull timonier/beanstalkd

# Or get a specific version

# Get the version 1.10
docker pull timonier/beanstalkd:1.10
```

## Usage

Run the application via `docker run`. The beanstalkd options can be passed as arguments:

```sh
# See all beanstalkd options
docker run \
    -i \
    -t \
    --net host \
    timonier/beanstalkd -h

# Run beanstalkd
docker run \
    -i \
    -t \
    --net host \
    timonier/beanstalkd -V
```

## Contributing

1. Fork it.
2. Create your branch: `git checkout -b my-new-feature`.
3. Commit your changes: `git commit -am 'Add some feature'`.
4. Push to the branch: `git push origin my-new-feature`.
5. Submit a pull request.

__Note__: Use the script `bin/build` to test your modifications locally.

## Links

* [beanstalkd](https://github.com/kr/beanstalkd)
* [command "docker pull"](https://docs.docker.com/reference/commandline/pull/)
* [command "docker run"](https://docs.docker.com/reference/run/)
* [image "timonier/beanstalkd"](https://hub.docker.com/r/timonier/beanstalkd/)
