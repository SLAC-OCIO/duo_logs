# duo_logs

Log grabber for Duo. Run this script periodically to dump all recent logs from Duo.

# Installation

- create a working directory for this: `mkdir /opt/duo_logs`
- clone this repository: `git clone git@github.com:SLAC-OCIO/duo_logs.git`
- install `virtualenv`: `sudo yum install -y python-virtualenv`
- create virtual environment under the working directory: `virtualenv /opt/duo_logs/`
- install dependencies: `/opt/duo_logs/bin/pip install -r requirements.txt`
-- if you don't have network access from the node, you can run `/opt/duo_logs/bin/pip install ~ytl/sys/src/six-1.9.0.tar.gz ~ytl/sys/src/nose-1.3.7.tar.gz ~ytl/sys/src/duo_client_python.zip`
- ensure some directories exist: `mkdir -p /opt/duo_logs/var/logs`
- create a cronjob to periodically poll for the logs and write them out locally: `0,5,10,15,20,25,30,35,40,45,50,55 * * * *   /opt/duo_logs/bin/duo_logs.py /opt/duo_logs/etc/duo.conf`

