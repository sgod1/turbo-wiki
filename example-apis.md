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

****work in progress...****</br>
```
{
    "uuid": "287473450564496",
    "displayName": "mmmmmm",
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
                }
            ]
        }
    ],
    "disabled": false,
    "readOnly": false,
    "default": false
}
```

**Update Policy**<br/>
