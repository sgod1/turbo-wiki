**Use cases for container workloads on k8s clusters**<br/>

**Case 1**<br/>

Take automated actions at multi-cluster scope.<br/>
Opt out of automation actions at namespace level.<br/>

Scheduled policies take precedence over policies with no schedule.<br/>
To avoid unexpected results, attach schedule to user defined policies.<br/>

```
// default action generation mode: recommend/manual
workload-controller default policy
  action generation mode: recommend/manual

// setup automation at multi-cluster scope
workload-controller user-defined policy
  action generation mode: automatic
  scope: group of workload controllers filtered by one or more k8s clsuters
  schedule: action execution schedule

// opt out of automation on namespace level by namespace tag
workload-controller user-defined policy
  action-generation-mode: manual
  scope: group of workload controllers by namespace tag
  schedule: action execution schedule
```

**Case 2**<br/>

Take manual actions at multi-cluster scope.<br/>
Automate selected workloads.<br/>

```
workload-controller default policy
  action generation mode: manual

workload-controller user defined policy:
  action generation mode: automatic
  scope: group of specific workloads
  schedule: action execution schedule
```

**Case 3**<br/>

Turbonomic api's.<br/>

