## Local Job Submission

A job can be submitted to the **master node** via a port-forwarded localhost:

```python
spark = SparkSession.builder \
	.appName("JobName") \
	.master("spark://localhost:123") \
	.getOrCreate()
```

Make sure the correct port number is used in the code above and forwarded with a command for your cloud provider. Follow the steps below to check which port the master node is listening to.

Find the **pid** that identifies the Spark process running on the master node. Multiple processes may be running, and you may need to test all the ports they are running on. Make sure to use sudo in all the commands below to print all processes and ports.

```bash
sudo jps -lm | grep spark
```

Copy the pid and match it to ports being listened to with `grep`. The matching port should have a value `LISTEN` printed to the screen.

```bash
sudo netstat -otulpn | grep 567
```

Before running the Python script that will launch your spark job, ensure the port is forwarded with a command for your cloud provider. For example, in GCP, you can run:

```bash
gcloud compute ssh data-transfer-cluster-m --project myproject --zone myzone --tunnel-through-iap -- -L 123:localhost:123
```