**Use cases for container workloads on k8s clusters**<br/>

**Case 1**<br/>

Take `automated` actions at `multi-cluster` scope.<br/>
`Opt out of automation` at `namespace` level.<br/>

Scheduled policies take precedence over policies with no schedule.<br/>
To avoid unexpected results, attach schedule to user defined policies.<br/>

***Container resize actions***</br>
```
// container-spec policy: analysis and scaling
container-spec default policy

container-spec user defined policy
  schedule: policy enforcement schedule

// default action generation mode: recommend/manual
workload-controller default policy
  action generation mode: recommend/manual

// automation at multi-cluster scope
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

***Container move actions***<br/>
```
// default container-pod policy: manual/recommend
contaier-pod default policy
  action generation mode: manual/recommend

// automation at multi-cluster scope
container-pod user defined policy
  action generation: automatic
  scope: group of container-pods filtered by one or more k8s clusters
  schedule: action execution schedule

// opt out of automation at namespace level
container-pod user defined policy
  action generation mode: manual
  scope: group of container-pods filtered by one or more k8s clusters
  schedule: action execution schedule
```

**Case 2**<br/>

Take `manual` actions at multi-cluster scope.<br/>
Automate selected workloads.<br/>

***Container resize actions***<br/>

```
// container-spec policy: analysis and scaling
container-spec default policy

container-spec user defined policy
  schedule: policy enforcement schedule

workload-controller default policy
  action generation mode: manual

workload-controller user defined policy:
  action generation mode: automatic
  scope: group of specific workloads
  schedule: action execution schedule
```

***Container move actions***<br/>
```
container-pod default policy
  action generation mode: manual

container-pod user defined policy:
  action generation mode: automatic
  scope: group of specific workloads
  schedule: action execution schedule
```

***Exclude clusters from policies, use different schedules***<br/>

To exclude a cluster from workload-controller group add exclusion filter to group definition:<br/>
Use group as a scope for automation policy and attach action execution schedule to a policy.<br/>
```
workload-controller group name: group1
filter: regex eq .*test
filter: not eq special_cluster_test

workload-controller user defined policy:
scope: group1
schedule: action execution schedule 1
```

Create workload-controller group for excluded clsuter:
Use group as a scope for automation policy and attach action execution schedule to a policy.<br/>
```
workload-controller group name: group2
filter: eq special_cluster_test

workload-controller user defined policy:
scope: group2
schedule: action execution schedule 2
```

**Case 3**<br/>

***Deployment automaiton***</br>

Turbonomic api's.<br/>

See `example-apis.md`.<br/>

