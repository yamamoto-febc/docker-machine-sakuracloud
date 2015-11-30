# Docker Machine SAKURA CLOUD Driver

This is a plugin for [Docker Machine](https://docs.docker.com/machine/) allowing
to create Docker hosts on [SAKURA CLOUD](http://cloud.sakura.ad.jp)

([日本語版](README.ja.md))

## Requirements
* [Docker Machine](https://docs.docker.com/machine/) 0.5.1+ (is bundled to
  [Docker Toolbox](https://www.docker.com/docker-toolbox) 1.9.1+)

## Tested Operationg System
* OSX 10.9+
* Windows 10

## Installation
#### Install via Homebrew(for OSX):

```console
$ brew tap yamamoto-febc/docker-machine-sakuracloud
$ brew install docker-machine-sakuracloud
```

#### Install via manualy:

download the binary `docker-machine-driver-sakuracloud`
and  make it available by `$PATH`, for example by putting it to `/usr/local/bin/`


```console
$ chmod +x /usr/local/bin/docker-machine-driver-sakuracloud
```

The latest version of `docker-machine-driver-sakuracloud` binary is available on
the ["Releases"](https://github.com/yamamoto-febc/docker-machine-sakuracloud/releases/latest) page.

## Usage
Official documentation for Docker Machine [is available here](https://docs.docker.com/machine/).

To create a virtual machine on `SAKURA CLOUD` for Docker purposes just run this command:

```
$ docker-machine create --driver=sakuracloud \
    --sakuracloud-access-token=[YOUR TOKEN] \
    --sakuracloud-access-token-secret=[YOUR TOKEN SECRET] \
    sakura-dev
```

Options:

 - `--sakuracloud-access-token`: **required** Your personal access token for the SAKURA CLOUD API.
 - `--sakuracloud-access-token-secret`: **required** Your personal access token secret for the SAKURA CLOUD API.
 - `--sakuracloud-connected-switch`: The ID of SAKURA CLOUD switch or router.
 - `--sakuracloud-additional-ip`: The address of eth1 IP.
 - `--sakuracloud-additional-subnet-mask`: The netmask of eth1.
 - `--sakuracloud-disk-connection`: The type of disk connection (`virtio` or `ide`).
 - `--sakuracloud-disk-name`: The name of SAKURA CLOUD disk.
 - `--sakuracloud-disk-plan`: The plan of SAKURA CLOUD disk plan (HDD:`2` or SSD:`4`).
 - `--sakuracloud-disk-size`: The size of disk for the SAKURA CLOUD server(in MB).
 - `--sakuracloud-plan`: The id of SAKURA CLOUD server plan.
 - `--sakuracloud-region`: The resion to create the server in.


Environment variables and default values:

| CLI option                          | Environment variable              | Default                  |
|-------------------------------------|-----------------------------------|--------------------------|
| `--sakuracloud-access-token`        | `SAKURACLOUD_ACCESS_TOKEN`        | -                        |
| `--sakuracloud-access-token-secret` | `SAKURACLOUD_ACCESS_TOKEN_SECRET` | -                        |
| `--sakuracloud-connected-switch`    | `SAKURACLOUD_CONNECTED_SWITCH`     | -                 |
| `--sakuracloud-additional-ip`       | `SAKURACLOUD_ADDITIONAL_IP`     | -                 |
| `--sakuracloud-additional-subnet-mask`     | `SAKURACLOUD_ADDITIONAL_SUBNET_MASK`     | `255.255.255.0`                 |
| `--sakuracloud-disk-connection`     | `SAKURACLOUD_DISK_CONNECTION`     | `virtio`                 |
| `--sakuracloud-disk-name`           | `SAKURACLOUD_DISK_NAME`           | `disk001`                |
| `--sakuracloud-disk-plan`           | `SAKURACLOUD_DISK_PLAN`           | `4`                      |
| `--sakuracloud-disk-size`           | `SAKURACLOUD_DISK_SIZE`           | `20480`                  |
| `--sakuracloud-plan`                | `SAKURACLOUD_PLAN`                | `1001`                   |
| `--sakuracloud-region`              | `SAKURACLOUD_REGION`              | `is1a`                   |


## Author

* Kazumichi Yamamoto ([@yamamoto-febc](https://github.com/yamamoto-febc))
