# helm-aws-alertmanager-sns-forwarder
SNS forwarder for AlertManager alerts

## Usage

```
helm upgrade -i prometheus-sns-forward . -n platform --values=stages/shared-values.yaml --values=stages/prod/prod-values.yaml
```


## Email Template Example

Sample alert notification email:
	
```text
	Status: firing
	Reciever: default
	
	Group key: 0
	Common Alert Annotations:
	  - description: Cluster has overcommitted CPU resource requests for Pods and cannot tolerate node failure.
	  - runbook_url: https://github.com/kubernetes-monitoring/kubernetes-mixin/tree/master/runbook.md#alert-name-kubecpuovercommit
	  - summary: Cluster has overcommitted CPU resource requests.
	
	Common Alert Labels:
	  - alertname: KubeCPUOvercommit
	  - cluster: prod-eks-cluster
	  - prometheus: platform/prometheus-prometheus
	  - region: us-east-1
	  - severity: warning
	  - stage: alpha
	
	Alert Group Labels:
	  - alertname: KubeCPUOvercommit
	
	
	Active Alert List:
	  Alert:
	    Annotations:
	    - description: Cluster has overcommitted CPU resource requests for Pods and cannot tolerate node failure.
	    - runbook_url: https://github.com/kubernetes-monitoring/kubernetes-mixin/tree/master/runbook.md#alert-name-kubecpuovercommit
	    - summary: Cluster has overcommitted CPU resource requests.
	
	    Labels:
	    - alertname: KubeCPUOvercommit
	    - cluster: prod-eks-cluster
	    - prometheus: platform/prometheus-prometheus
	    - region: us-east-1
	    - severity: warning
	    - stage: alpha
	
	    Start Time 2021-11-01T11:50:39.329Z
	
	Version:0
```
