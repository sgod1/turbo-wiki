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
```

**Update Policy**<br/>
