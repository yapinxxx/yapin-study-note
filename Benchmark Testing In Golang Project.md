# [ghz](https://ghz.sh/)
#### Command
1. 使用不需要憑證的連線，1000 條連線，每次同步發送 100 條 Request，Request 內容為 EDR 對 DraySOAR 的第一次連線
	1. Command
		1. Multiple line
			```sh
			  ghz --insecure     
				  --proto gRPC/pbedr/grpc_mdr_to_edr.proto     
				  --call BidStreamTest.Talk.Talking     
				  -d '{ "configWithAction": { "Introduction": { "Data": { "UUID": { "String": "{{.RequestNumber}}" }, "HostName": { "String": "DESKTOP-{{.RequestNumber}}" } } } } }'    -n 2000     
				  -c 1000  
				  -t 60s 
				  -z 360s 
				  192.168.130.104:10207
			```
		2. Oneline
	        ```
	        ghz --insecure --proto gRPC/pbedr/grpc_mdr_to_edr.proto --call BidStreamTest.Talk.Talking -d '{ "configWithAction": { "Introduction": { "Data": { "UUID": { "String": "{{.RequestNumber}}" }, "HostName": { "String": "DESKTOP-{{.RequestNumber}}" } } } } }' -n 2000 -c 1000 -t 60s -z 5s 192.168.130.104:10207
	        ```
	2. Detail
		1. `{{.RequestNumber}}` 為 ghz 提供的 template
		2. `--call` 必須涵蓋 proto package name
		3. 有時候 `-n`, `-c` 的數字太小，不會發現程式有錯誤
		4. 
	3. [Flag Meaning](https://ghz.sh/docs/options)
		1. -n -> Total 
		2. -c -> concurrency numbers
		3. -t -> Timeout
			1. Default 20s
		4. -z -> Duration
			1. If duration is specefied, `n` is ignored
				1. Such as: `-z 3m`, `-z 10s`


# [Prometheus](https://prometheus.io/)
## Server
1. Download Server
2. Setting Config
3. Start Prometheus Server

## Exporter
#### Node-Exporter
##### Official (Prometheus)
1. Download Node-Exporter
2. Start Node-Exporter
#### Process-Exporter
1. Command Line
	1. Multiple Line
		```sh
		  docker run -d --rm 
			  -p 9256:9256 --privileged 
			  -v /proc:/host/proc 
			  -v `pwd`:/config ncabatoff/process-exporter 
			  --procfs /host/proc 
			  -config.path /config/filename.yml
		```
	2. One Line
        ```
        docker run -d --rm -p 9256:9256 --privileged -v /proc:/host/proc -v "$PWD"/config:/config --name=process-exporter ncabatoff/process-exporter --procfs /host/proc -config.path /config/wumu_conf.yaml
        ```

	3. Default
		```
		  docker run -d --rm -p 9256:9256 --privileged -v /proc:/host/proc -v `pwd`:/config ncabatoff/process-exporter --procfs /host/proc -config.path /config/filename.yml
		
		```
# Grafana
1. Start Grafana
	`docker run -d --name=grafana -p 3000:3000 grafana/grafana`
## Template
1. [Process-Exporter](https://grafana.com/grafana/dashboards/249-named-processes/)
2. [Node-Exporter](https://grafana.com/grafana/dashboards/11074-node-exporter-for-prometheus-dashboard-en-v20201010/)

# Reference
1. [Monitoring Linux Processes using Prometheus and Grafana](https://devconnected.com/monitoring-linux-processes-using-prometheus-and-grafana/)
2. [process-exporter](https://github.com/ncabatoff/process-exporter)
3. [Prometheus process-exporter 監控服務處理程序](https://chenzhonzhou.github.io/2020/11/19/prometheus-process-exporter-jian-kong-fu-wu-jin-cheng/)