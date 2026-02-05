**Container resize and move actions.**<br/>

**Policy hierarchy.**<br/>
`User defined` policies override `default` policy.<br/>fff
When `user defined` policies are in conflict, `the most conservative` policy setting wins.<br/>

***Automation at the namespace and workload level***<br/>
Configure `default policy` for `recommended` actions mode.<br/>
Configure `namespace scoped` policy for `automatic` actions mode.<br/>
Configure `workload scoped` policy for `manual/recommended` actions mode.<br/>

***Automation for specific workload without namespace scope***
If workload namespace is not targeted for automation, configure workload-scoped policy for automatic/manual/recommended actions.<br/>

***Turbonomic containers supply chain.***
````
container -> container-spec -> workload-controller -> namespace -> container-platform
container -> container-pod -> namespace -> container-platform
````

***Configure `container resize` actions.***</br>
`Container-spec` entity sets parameters for container `resize` actions.<br/>
`Workload-controller` entity sets action execution mode for resize actions.<br/>

***Example: configure resize actions at the namespace scope***</br>
Configure `container-spec default` policy capacity and scaling.<br/>

Create label or annotation on the namespace to use as Turbonomic tag.<br/>
Create `container-spec` group and scope it to the namespace with the `namespace-tag` tag.<br/>
Create `container-spec` policy scoped to this group and define capacity and scaling parameters.<br/>

Configure `workload-controller default` policy with recommended actions mode.<br/>
Create `workload-controller` group and scope it to the namespace with the `namespace-tag` tag.<br/>
Create `workload-controller` policy scoped to this group and set `resize` action generation mode.<br/>

***`Container-spec` capacity settings.***<br/>
````
capacity('container-spec', vcpu_lim, [500 mcores, 6400 mcores], target_util_midpoint(70%)).
resize_below_min(vcpu_lim, recommended).
resize_above_max(vcpu_lim, recommended).

capacity('container-spec', vcpu_req, [10 mcores, 6400 mcores], target_util_midpoint(110%)).
resize_below_min(vcpu_req, recommended).
resize_above_max(vcpu_req, recommended).

capacity('container-spec', vmem_lim, [10 mb,1048576 mb], target_util_midpoint(70%)).
resize_below_min(vmem_lim, recommended).
resize_above_max(vmem_lim, recommended).

capacity('container-spec', vmem_req, [10 mb,1048576 mb], target_util_midpoint(110%)).
resize_below_min(vmem_req, recommended).
resize_above_max(vmem_req, recommended).

cpu_throttling_tolerance(20%).
````

***`Container-spec` scaling constraints.***<br/>
````
resize_aggressiveness_percentile(p99).
vcpu_lim_incr(100 mcores).
vcpu_req_incr(10 mcores).
vmem_lim_incr(128 mb).
vmem_req_incr(16 mb).
rate_of_resize(3).
max_obs_period(30 days).
min_obs_period(1 days).
```
