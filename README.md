# proxy_ctl
proxy_ctl is a tool designed for simplifying the job of setting reverse proxy when using nginx.

## Installation
```
# install nginx
dnf install nginx
systemctl enable nginx
systemctl start nginx

# install acme.sh for https
wget -O -  https://get.acme.sh | sh

# install proxy_ctl
wget -O /usr/bin/proxy_ctl https://raw.githubusercontent.com/gidcs/proxy_ctl/master/proxy_ctl
chmod 755 /usr/bin/proxy_ctl
```

## Usage
```
proxy_ctl list
proxy_ctl add <domain> <ipaddr:port> [--https] [--force]
proxy_ctl del <domain> [--force]
```

## Example
```
proxy_ctl list
proxy_ctl add example.com server.example.com
proxy_ctl add example.com server.example.com:8080
proxy_ctl add example.com server.example.com --https # proxy https website
proxy_ctl add example.com 10.0.2.1 --force # don't send hostname to backend
proxy_ctl add example.com 10.0.2.1
proxy_ctl del example.com
proxy_ctl del example.com --force # remove acme.sh's ssl also
```

## Note
- This tool is not compatible with mawk. mawk does not support regex's repetition notation.

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
