**Automation Policy Schedule**<br/>

`User defined` automation policies support `policy enforcement` and `action execution` schedules.<br/>

When a schedule is attached to `container-spec` policy, it is `policy enforcement` schedule.<br/>
It affects the period of time when analysis and scaling properties defined by the policy is in effect.</br>

When schedule is attached to `workload-controller` policy, it is `action execution` schedule.<br/>
If affects a period of time when `resize` action execution mode defined in the policy is in effect.<br/>

When schedule is attached to `container-pod` policy, it is `action execution` schedule.<br/>
If affects a period of time when `move` action execution mode defined in the policy is in effect.<br/>

```
[<----- monthly policy enforcement schedule for container-spec policy analysis and scaling settings ---->]
[<- daily action execution schedule for resize and move actions ->] [<- daily ->] [<-daily->]
```

`Scheduled` policies take precedence over policies with no schedule.<br/>
