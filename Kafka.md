## Check broker connection logs
Connection logs:
```bash
sudo cat /var/log/messages | tail -50 # Verify log timestamps
```
## Verify broker connection to Zookeeper
```bash
nc -v zookeeper-url-path 2181
```
## Restart
```bash
sudo systemctl restart kafka
```