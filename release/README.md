Releasing Apache Kafka
======================

This directory contains the tools used to publish a release.

# Requirements

* python 3.12
* git
* gpg 2.4
* sftp

The full instructions for producing a release are available in
https://cwiki.apache.org/confluence/display/KAFKA/Release+Process.


# Setup

Create a virtualenv for python, activate it and install dependencies:

```
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

# Usage

To start a release, first activate the virutalenv, and then run
the release script.

```
source .venv/bin/activate
```

You'll need to setup `PUSH_REMOTE_NAME` to refer to
the git remote for `apache/kafka`.

```
export PUSH_REMOTE_NAME=<value>
```

It should be the value shown with this command:

```
git remote -v | grep -w 'github.com' | grep -w 'apache/kafka' | grep -w '(push)' | awk '{print $1}'
```

Then start the release script:

```
python release.py
```

