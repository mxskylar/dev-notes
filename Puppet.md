## Verify run
```bash
sudo puppet agent -t --noop 
```
## Run
```bash
sudo puppet agent -t
```
## Disable
```bash
sudo puppet agent -t --disable
```
## Enable
```bash
sudo puppet agent -t --enable
```
## Check the default environment
```bash
cat /etc/puppetlabs/puppet/puppet.conf | grep environment
```