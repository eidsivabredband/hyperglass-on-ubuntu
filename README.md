# Installation

Some tips and tricks on how to install [Hyperglass](https://hyperglass.dev/) on a clean (and **dedicated**  [Ubuntu22.04LTS](https://ubuntu.com/server)


## Requirements

Hyperglass was written for the 18.04, and some preferences and modules (mainly phyton-related) have changes since then. 
This guide is not a complete manual to neither hyperglass nor python, but more a "how to get a basic system up-and-running"

Hyperglass was developed on Python version 3.6. Current Python-version on Ubuntu22.04 is 3.10, you need version 3.9 (possibly 3.11, we have not tried) due to a bug in one of the 3.10-libraries.

Following the [instructions](https://ubuntuhandbook.org/index.php/2022/10/python-3-11-released-how-install-ubuntu/), install Python3.9, replacing references to 3.11 with 3.9.
Remember to set Python3.9 as default.

Turning to [Manual Installation Instructions](https://hyperglass.dev/docs/getting-started#manual-installation "https://hyperglass.dev/docs/getting-started#manual-installation"), a few changes is needed.

```
$ sudo apt install -y python3-dev python3-pip python3.9-distutils libjpeg-dev zlib1g-dev
```
and
```
$ python3 --version
Python 3.9.17
```

For [Other Dependencies](https://hyperglass.dev/docs/getting-started/#other-dependencies "https://hyperglass.dev/docs/getting-started/#other-dependencies"), you need to make the keyring available to apt,

```
$ curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -

$ curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
$ echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
$ sudo chmod a+r /usr/share/keyrings/nodesource.gpg

$ sudo apt update
$ sudo apt install -y nodejs yarn redis-server

$ sudo systemctl enable redis-server
$ sudo systemctl restart redis-server
```

## Hyperglass installation

After having run 
```
$ pip3 install hyperglass
```
(which we did as "root", in lack of good reasons), you need to uninstall the cryptography3.4.x that Hyperglass relies on - that version did not work for us;

```
$ pip3 uninstall cryptography
$ pip3 install cryptography>=3.5
$ pip3 list | grep cryptography
cryptography                 41.0.1
```

That should be it!

After completing [Setup](https://hyperglass.dev/docs/setup "https://hyperglass.dev/docs/setup"), we have a few more tips for you:

## Configuring Hyperglass to your environment



