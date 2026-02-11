**Example APIs**</br>

**Create Group**</br>
```
{
  "displayName": "api-group-container-spec-1",
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
      "entityType": "string",
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
}

```

**Update Group**<br/>

**Create Policy**<br/>

**Update Policy**<br/>
