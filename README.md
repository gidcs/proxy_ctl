# proxy_ctl
proxy_ctl is a tool designed to simplify the task of setting up a reverse proxy when using nginx. It creates a configuration file for nginx and configures SSL using acme.sh, and finally lets nginx listen on the port you specify and reverse proxy your service. We provide templates for cockpit and transmission, which are very handy for newcomers.

## Installation
```
# install nginx
dnf install nginx
systemctl enable nginx
systemctl start nginx

# install acme.sh for https
wget -O -  https://get.acme.sh | sh

# install proxy_ctl
wget -O /usr/bin/proxy_ctl \
    https://raw.githubusercontent.com/gidcs/proxy_ctl/master/proxy_ctl
chmod 755 /usr/bin/proxy_ctl
```

## Usage
```
proxy_ctl help <command>
proxy_ctl list
proxy_ctl add <domain> <ipaddr:port> [option...]
proxy_ctl del <domain> [option...]
```

## Example
```
proxy_ctl list
proxy_ctl add test.com backend.com                    # normal case
proxy_ctl add test.com backend.com -p https           # proxy https website
proxy_ctl add test.com backend.com -P 8080            # listen on port 8080
proxy_ctl add test.com 10.0.2.1 -P 8080 -f            # not send hostname
proxy_ctl add test.com localhost:9090 -t cockpit      # proxy cockpit
proxy_ctl add test.com localhost:9091 -t transmission # proxy transmission
proxy_ctl del test.com
proxy_ctl del test.com -f                             # remove ssl also
```

## License

Copyright year [guyusoftware]

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

[guyusoftware]: https://www.guyusoftware.com/
