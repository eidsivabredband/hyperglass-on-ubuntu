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



 
