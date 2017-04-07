# proxy_ctl
proxy_ctl is a tool designed for simplifing the job of setting reverse proxy when using nginx.

## Installation
```
# install acme.sh to support letsencrypt
wget -O -  https://get.acme.sh | sh
# install proxy_ctl
wget -O /usr/bin/proxy_ctl https://raw.githubusercontent.com/gidcs/proxy_ctl/master/proxy_ctl
chmod 755 /usr/bin/proxy_ctl
```

## Usage
```
proxy_ctl add <domain> <ipaddr>
proxy_ctl del <domain>
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