# elk stack on local microk8s cluster
This repo containes the following manifest files 
```
├── elasticsearch_svc.yaml
├── elasticsearch.yaml
├── filebeat.yaml
├── kibana.yaml
├── logstash.yaml
├── metricbeat.yaml
└── pv.yaml

```
## Deploy single node elastic search

At first you need to create a persistent volume. To do so 

```
kubectl apply -f pv.yaml
```
> Please keep in mind if you are using any other storageclass other than `local-storage`, you need to replace that. 

After that create the elasticsearch service 

```
kubectl apply -f elasticsearch_svc.yaml
```
Finally create the elasticsearch statefulset

```
kubectl apply -f elasticsearch.yaml
```
## Deploy logstash

To deploy logstash

```
kubectl apply -f logstash.yaml
```
## Deploy filebeat

to deploy filebeat 

```
kubectl apply -f filebeat.yaml
```
## Deploy metricbeat

To deploy metricbeat
```
kubectl apply -f metricbeat.yaml
```
## Deploy kibana

To deploy kibana
```
kubectl apply -f kibana.yaml
```

