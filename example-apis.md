**Example APIs**</br>

**Create Group**</br>
```
curl -X 'POST' \
  'https://nginx-turbonomic.apps.turbo.szesto.io/vmturbo/rest/groups' \
  -H 'accept: application/json' \
  -H 'Content-Type: application/json' \
  -d '{ "displayName": "api-group-container-spec-1",
  "className": "Group",
  "groupType": "ContainerSpec",
  "environmentType": "HYBRID",
  "isStatic": false,
  "logicalOperator": "AND",
  "criteriaList": [
    {
      "expVal": ".*",
      "expType": "RXEQ",
      "filterType": "containerSpecsByContainerPlatformCluster",
      "caseSensitive": false,
      "singleLine": false
    }
  ],
  "temporary": false,
  "cloudType": "UNKNOWN",
  "memberTypes": [
    "ContainerSpec"
  ],
  "entityTypes": [
    "ContainerSpec"
  ],
  "groupOrigin": "USER",
  "groupClassName": "GroupApiDTO"
}'
```

***Response body, code 200***<br/>
```
{
  "uuid": "287472263631520",
  "displayName": "api-group-container-spec-1",
  "className": "Group",
  "membersCount": 258,
  "entitiesCount": 258,
  "groupType": "ContainerSpec",
  "severity": "CRITICAL",
  "environmentType": "HYBRID",
  "isStatic": false,
  "logicalOperator": "AND",
  "criteriaList": [
    {
      "expVal": ".*",
      "expType": "RXEQ",
      "filterType": "containerSpecsByContainerPlatformCluster",
      "caseSensitive": false,
      "entityType": null,
      "singleLine": false
    }
  ],
  "memberUuidList": [
  ],
  "temporary": false,
  "activeEntitiesCount": 258,
  "cloudType": "UNKNOWN",
  "memberTypes": [
    "ContainerSpec"
  ],
  "entityTypes": [
    "ContainerSpec"
  ],
  "groupClassName": "GroupApiDTO"
}
```

**Update Group**<br/>

***Update filter value***</br>
```
curl -X 'PUT' \
  'https://nginx-turbonomic.apps.turbo.szesto.io/vmturbo/rest/groups/287472263631520' \
  -H 'accept: application/json' \
  -H 'Content-Type: application/json' \
  -d '{
"displayName": "api-group-container-spec-1",
  "className": "Group",
  "groupType": "ContainerSpec",
  "environmentType": "HYBRID",
  "isStatic": false,
  "logicalOperator": "AND",
  "criteriaList": [
    {
      "expVal": ".*test$",
      "expType": "RXEQ",
      "filterType": "containerSpecsByContainerPlatformCluster",
      "caseSensitive": false,
      "singleLine": false
    }
  ],
  "temporary": false,
  "cloudType": "UNKNOWN",
  "memberTypes": [
    "ContainerSpec"
  ],
  "entityTypes": [
    "ContainerSpec"
  ],
  "groupOrigin": "USER",
  "groupClassName": "GroupApiDTO"
}'
```

***Response body, code 200***<br/>
```
{
  "uuid": "287472263631520",
  "displayName": "api-group-container-spec-1",
  "className": "Group",
  "membersCount": 258,
  "entitiesCount": 258,
  "groupType": "ContainerSpec",
  "severity": "CRITICAL",
  "environmentType": "HYBRID",
  "isStatic": false,
  "logicalOperator": "AND",
  "criteriaList": [
    {
      "expVal": ".*test$",
      "expType": "RXEQ",
      "filterType": "containerSpecsByContainerPlatformCluster",
      "caseSensitive": false,
      "entityType": null,
      "singleLine": false
    }
  ],
  "memberUuidList": [
  ],
  "temporary": false,
  "activeEntitiesCount": 258,
  "cloudType": "UNKNOWN",
  "memberTypes": [
    "ContainerSpec"
  ],
  "entityTypes": [
    "ContainerSpec"
  ],
  "groupOrigin": "USER",
  "groupClassName": "GroupApiDTO"
}
```

**Create Policy**<br/>

***EntityType: ContainerSpec***<br/>

```
curl -X 'POST' \
  'https://nginx-turbonomic.apps.turbo.szesto.io/vmturbo/rest/settingspolicies' \
  -H 'accept: application/json' \
  -H 'Content-Type: application/json' \
  -d '{
    "uuid": "287473985418640",
    "displayName": "mmmm",
    "entityType": "ContainerSpec",
    "scopes": [
        {
            "uuid": "287472263631520",
            "displayName": "api-group-container-spec-1",
            "isStatic": true,
            "logicalOperator": "AND",
            "groupClassName": "GroupApiDTO"
        }
    ],
    "settingsManagers": [
        {
            "uuid": "marketsettingsmanager",
            "displayName": "Operational Constraints",
            "category": "Analysis",
            "settings": [
                {
                    "uuid": "RATE_OF_RESIZE",
                    "displayName": "Rate of Resize",
                    "value": "3.0",
                    "defaultValue": "3.0",
                    "categories": [
                        "resizeRecommendationsConstants"
                    ],
                    "valueType": "NUMERIC",
                    "valueObjectType": "String",
                    "min": 1,
                    "max": 3,
                    "entityType": "ContainerSpec"
                },
                {
                    "uuid": "resizeVcpuLimitMaxThreshold",
                    "displayName": "VCPU Limit Resize Max Threshold (in mCores)",
                    "value": "64001.0",
                    "defaultValue": "64000.0",
                    "valueType": "NUMERIC",
                    "valueObjectType": "String",
                    "min": 0,
                    "max": 1000000,
                    "entityType": "ContainerSpec"
                },
                {
                    "uuid": "vcpuLimitToleranceContainerSpec",
                    "displayName": "VCPU Limit Target Utilization (in %)",
                    "value": "71.0",
                    "defaultValue": "70.0",
                    "valueType": "NUMERIC",
                    "valueObjectType": "String",
                    "min": 10,
                    "max": 90,
                    "entityType": "ContainerSpec"
                },
                {
                    "uuid": "usedIncrement_Container_VMEM_Request",
                    "displayName": "Increment constant for VMEM Request [MB]",
                    "value": "16.0",
                    "defaultValue": "16.0",
                    "categories": [
                        "resizeRecommendationsConstants"
                    ],
                    "valueType": "NUMERIC",
                    "valueObjectType": "String",
                    "min": 0,
                    "max": 1000000,
                    "entityType": "ContainerSpec"
                },
                {
                    "uuid": "maxCPUThrottlingTolerance",
                    "displayName": "Max CPU Throttling Tolerance (in %)",
                    "value": "21.0",
                    "defaultValue": "20.0",
                    "valueType": "NUMERIC",
                    "valueObjectType": "String",
                    "min": 10,
                    "max": 70,
                    "entityType": "ContainerSpec"
                },
                {
                    "uuid": "vcpuRequestToleranceContainerSpec",
                    "displayName": "VCPU Request Target Utilization (in %)",
                    "value": "110.0",
                    "defaultValue": "110.0",
                    "valueType": "NUMERIC",
                    "valueObjectType": "String",
                    "min": 10,
                    "max": 190,
                    "entityType": "ContainerSpec"
                },
                {
                    "uuid": "resizeVcpuLimitMinThreshold",
                    "displayName": "VCPU Limit Resize Min Threshold (in mCores)",
                    "value": "501.0",
                    "defaultValue": "500.0",
                    "valueType": "NUMERIC",
                    "valueObjectType": "String",
                    "min": 0,
                    "max": 1000000,
                    "entityType": "ContainerSpec"
                },
                {
                    "uuid": "percentileAggressivenessContainerSpec",
                    "displayName": "Aggressiveness",
                    "value": "99.0",
                    "defaultValue": "99.0",
                    "categories": [
                        "resizeRecommendationsConstants"
                    ],
                    "valueType": "NUMERIC",
                    "valueObjectType": "String",
                    "min": 90,
                    "max": 100,
                    "entityType": "ContainerSpec"
                },
                {
                    "uuid": "usedIncrement_Container_VCPU_Request",
                    "displayName": "Increment constant for VCPU Request [mCores]",
                    "value": "10.0",
                    "defaultValue": "10.0",
                    "categories": [
                        "resizeRecommendationsConstants"
                    ],
                    "valueType": "NUMERIC",
                    "valueObjectType": "String",
                    "min": 0,
                    "max": 1000000,
                    "entityType": "ContainerSpec"
                },
                {
                    "uuid": "resizeVcpuRequestMaxThreshold",
                    "displayName": "VCPU Request Resize Max Threshold (in mCores)",
                    "value": "64001.0",
                    "defaultValue": "64000.0",
                    "valueType": "NUMERIC",
                    "valueObjectType": "String",
                    "min": 0,
                    "max": 1000000,
                    "entityType": "ContainerSpec"
                },
                {
                    "uuid": "resizeVmemLimitMaxThreshold",
                    "displayName": "VMEM Limit Resize Max Threshold (in MB)",
                    "value": "1048571.0",
                    "defaultValue": "1048576.0",
                    "valueType": "NUMERIC",
                    "valueObjectType": "String",
                    "min": 0,
                    "max": 1048576,
                    "entityType": "ContainerSpec"
                },
                {
                    "uuid": "minObservationPeriodContainerSpec",
                    "displayName": "Min Observation Period",
                    "value": "1.0",
                    "defaultValue": "1.0",
                    "categories": [
                        "resizeRecommendationsConstants"
                    ],
                    "valueType": "NUMERIC",
                    "valueObjectType": "String",
                    "min": 0,
                    "max": 90,
                    "entityType": "ContainerSpec"
                },
                {
                    "uuid": "resizeVmemRequestMaxThreshold",
                    "displayName": "VMEM Request Resize Max Threshold (in MB)",
                    "value": "1048571.0",
                    "defaultValue": "1048576.0",
                    "valueType": "NUMERIC",
                    "valueObjectType": "String",
                    "min": 0,
                    "max": 1048576,
                    "entityType": "ContainerSpec"
                },
                {
                    "uuid": "vmemLimitToleranceContainerSpec",
                    "displayName": "VMEM Limit Target Utilization (in %)",
                    "value": "71.0",
                    "defaultValue": "70.0",
                    "valueType": "NUMERIC",
                    "valueObjectType": "String",
                    "min": 10,
                    "max": 90,
                    "entityType": "ContainerSpec"
                },
                {
                    "uuid": "maxObservationPeriodContainerSpec",
                    "displayName": "Max Observation Period",
                    "value": "30.0",
                    "defaultValue": "30.0",
                    "categories": [
                        "resizeRecommendationsConstants"
                    ],
                    "valueType": "NUMERIC",
                    "valueObjectType": "String",
                    "min": 7,
                    "max": 90,
                    "entityType": "ContainerSpec"
                },
                {
                    "uuid": "usedIncrement_Container_VCPU",
                    "displayName": "Increment constant for VCPU Limit [mCores]",
                    "value": "100.0",
                    "defaultValue": "100.0",
                    "categories": [
                        "resizeRecommendationsConstants"
                    ],
                    "valueType": "NUMERIC",
                    "valueObjectType": "String",
                    "min": 0,
                    "max": 1000000,
                    "entityType": "ContainerSpec"
                },
                {
                    "uuid": "resizeVmemLimitMinThreshold",
                    "displayName": "VMEM Limit Resize Min Threshold (in MB)",
                    "value": "11.0",
                    "defaultValue": "10.0",
                    "valueType": "NUMERIC",
                    "valueObjectType": "String",
                    "min": 0,
                    "max": 1048576,
                    "entityType": "ContainerSpec"
                },
                {
                    "uuid": "resizeVcpuRequestMinThreshold",
                    "displayName": "VCPU Request Resize Min Threshold (in mCores)",
                    "value": "11.0",
                    "defaultValue": "10.0",
                    "valueType": "NUMERIC",
                    "valueObjectType": "String",
                    "min": 0,
                    "max": 1000000,
                    "entityType": "ContainerSpec"
                },
                {
                    "uuid": "resizeVmemRequestMinThreshold",
                    "displayName": "VMEM Request Resize Min Threshold (in MB)",
                    "value": "11.0",
                    "defaultValue": "10.0",
                    "valueType": "NUMERIC",
                    "valueObjectType": "String",
                    "min": 0,
                    "max": 1048576,
                    "entityType": "ContainerSpec"
                },
                {
                    "uuid": "vmemRequestToleranceContainerSpec",
                    "displayName": "VMEM Request Target Utilization (in %)",
                    "value": "111.0",
                    "defaultValue": "110.0",
                    "valueType": "NUMERIC",
                    "valueObjectType": "String",
                    "min": 10,
                    "max": 190,
                    "entityType": "ContainerSpec"
                },
                {
                    "uuid": "usedIncrement_Container_VMEM",
                    "displayName": "Increment constant for VMEM Limit [MB]",
                    "value": "128.0",
                    "defaultValue": "128.0",
                    "categories": [
                        "resizeRecommendationsConstants"
                    ],
                    "valueType": "NUMERIC",
                    "valueObjectType": "String",
                    "min": 0,
                    "max": 1000000,
                    "entityType": "ContainerSpec"
                }
            ]
        },
        {
            "uuid": "automationmanager",
            "displayName": "Action Mode Settings",
            "category": "Automation",
            "settings": [
                {
                    "uuid": "resizeVmemRequestAboveMaxThreshold",
                    "displayName": "VMEM Request Resize Above Max",
                    "value": "RECOMMEND",
                    "defaultValue": "RECOMMEND",
                    "valueType": "STRING",
                    "valueObjectType": "String",
                    "options": [
                        {
                            "label": "Disabled",
                            "value": "DISABLED"
                        },
                        {
                            "label": "Recommend",
                            "value": "RECOMMEND"
                        }
                    ],
                    "entityType": "ContainerSpec"
                },
                {
                    "uuid": "resizeVcpuLimitBelowMinThreshold",
                    "displayName": "VCPU Limit Resize Below Min",
                    "value": "RECOMMEND",
                    "defaultValue": "DISABLED",
                    "valueType": "STRING",
                    "valueObjectType": "String",
                    "options": [
                        {
                            "label": "Disabled",
                            "value": "DISABLED"
                        },
                        {
                            "label": "Recommend",
                            "value": "RECOMMEND"
                        }
                    ],
                    "entityType": "ContainerSpec"
                },
                {
                    "uuid": "resizeVmemRequestBelowMinThreshold",
                    "displayName": "VMEM Request Resize Below Min",
                    "value": "RECOMMEND",
                    "defaultValue": "RECOMMEND",
                    "valueType": "STRING",
                    "valueObjectType": "String",
                    "options": [
                        {
                            "label": "Disabled",
                            "value": "DISABLED"
                        },
                        {
                            "label": "Recommend",
                            "value": "RECOMMEND"
                        }
                    ],
                    "entityType": "ContainerSpec"
                },
                {
                    "uuid": "resizeVmemLimitBelowMinThreshold",
                    "displayName": "VMEM Limit Resize Below Min",
                    "value": "RECOMMEND",
                    "defaultValue": "RECOMMEND",
                    "valueType": "STRING",
                    "valueObjectType": "String",
                    "options": [
                        {
                            "label": "Disabled",
                            "value": "DISABLED"
                        },
                        {
                            "label": "Recommend",
                            "value": "RECOMMEND"
                        }
                    ],
                    "entityType": "ContainerSpec"
                },
                {
                    "uuid": "resizeVcpuRequestBelowMinThreshold",
                    "displayName": "VCPU Request Resize Below Min",
                    "value": "RECOMMEND",
                    "defaultValue": "RECOMMEND",
                    "valueType": "STRING",
                    "valueObjectType": "String",
                    "options": [
                        {
                            "label": "Disabled",
                            "value": "DISABLED"
                        },
                        {
                            "label": "Recommend",
                            "value": "RECOMMEND"
                        }
                    ],
                    "entityType": "ContainerSpec"
                },
                {
                    "uuid": "resizeVcpuLimitAboveMaxThreshold",
                    "displayName": "VCPU Limit Resize Above Max",
                    "value": "RECOMMEND",
                    "defaultValue": "RECOMMEND",
                    "valueType": "STRING",
                    "valueObjectType": "String",
                    "options": [
                        {
                            "label": "Disabled",
                            "value": "DISABLED"
                        },
                        {
                            "label": "Recommend",
                            "value": "RECOMMEND"
                        }
                    ],
                    "entityType": "ContainerSpec"
                },
                {
                    "uuid": "resizeVcpuRequestAboveMaxThreshold",
                    "displayName": "VCPU Request Resize Above Max",
                    "value": "RECOMMEND",
                    "defaultValue": "RECOMMEND",
                    "valueType": "STRING",
                    "valueObjectType": "String",
                    "options": [
                        {
                            "label": "Disabled",
                            "value": "DISABLED"
                        },
                        {
                            "label": "Recommend",
                            "value": "RECOMMEND"
                        }
                    ],
                    "entityType": "ContainerSpec"
                },
                {
                    "uuid": "resize",
                    "displayName": "Resize",
                    "value": "MANUAL",
                    "defaultValue": "MANUAL",
                    "valueType": "STRING",
                    "valueObjectType": "String",
                    "options": [
                        {
                            "label": "Disabled",
                            "value": "DISABLED"
                        },
                        {
                            "label": "Recommend",
                            "value": "RECOMMEND"
                        },
                        {
                            "label": "External Approval",
                            "value": "EXTERNAL_APPROVAL"
                        },
                        {
                            "label": "Manual",
                            "value": "MANUAL"
                        }
                    ],
                    "entityType": "ContainerSpec"
                },
                {
                    "uuid": "resizeVmemLimitAboveMaxThreshold",
                    "displayName": "VMEM Limit Resize Above Max",
                    "value": "RECOMMEND",
                    "defaultValue": "RECOMMEND",
                    "valueType": "STRING",
                    "valueObjectType": "String",
                    "options": [
                        {
                            "label": "Disabled",
                            "value": "DISABLED"
                        },
                        {
                            "label": "Recommend",
                            "value": "RECOMMEND"
                        }
                    ],
                    "entityType": "ContainerSpec"
                }
            ]
        }
    ],
    "disabled": false,
    "readOnly": false,
    "default": false
}'
```

**Update Policy**<br/>
