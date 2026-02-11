**Example APIs**</br>

**Create Group**</br>
```
{
  "links": [
    {
      "rel": {}
    }
  ],
  "uuid": "string",
  "displayName": "api-group-container-spec",
  "className": "Group",
  "membersCount": 0,
  "entitiesCount": 0,
  "costPrice": 0,
  "groupType": "ContainerSpec",
  "severity": "UNKNOWN",
  "state": "UNKNOWN",
  "environmentType": "HYBRID",
  "scope": [
    "string"
  ],
  "isStatic": false,
  "logicalOperator": "AND",
  "criteriaList": [
    {
      "expVal": ".*",
      "expType": "RXEQ",
      "filterType": "ContainerSpecsByContainerPlatformCluster",
      "caseSensitive": false,
      "entityType": "string",
      "singleLine": false
    }
  ],
  "memberUuidList": [
    "string"
  ],
  "realtimeMarketReference": {
    "links": [
      {
        "rel": {}
      }
    ],
    "uuid": "string",
    "displayName": "string",
    "className": "string"
  },
  "stats": [
    {
      "links": [
        {
          "rel": {}
        }
      ],
      "uuid": "string",
      "displayName": "string",
      "className": "string",
      "date": "string",
      "statistics": [
        {
          "links": [
            {
              "rel": {}
            }
          ],
          "uuid": "string",
          "displayName": "string",
          "className": "string",
          "name": "string",
          "capacity": {
            "max": 0,
            "min": 0,
            "avg": 0,
            "total": 0,
            "totalMax": 0,
            "totalMin": 0
          },
          "reserved": {
            "max": 0,
            "min": 0,
            "avg": 0,
            "total": 0,
            "totalMax": 0,
            "totalMin": 0
          },
          "relatedEntityType": "string",
          "filters": [
            {
              "type": "string",
              "value": "string",
              "displayName": "string"
            }
          ],
          "relatedEntity": {
            "links": [
              {
                "rel": {}
              }
            ],
            "uuid": "string",
            "displayName": "string",
            "className": "string"
          },
          "numRelatedEntities": 0,
          "units": "string",
          "values": {
            "max": 0,
            "min": 0,
            "avg": 0,
            "total": 0,
            "totalMax": 0,
            "totalMin": 0
          },
          "value": 0,
          "commoditySource": {
            "capacityCommoditySource": "string",
            "usedCommoditySource": "string",
            "capacitySourceIndex": 0,
            "usedSourceIndex": 0
          },
          "histUtilizations": [
            {
              "type": "string",
              "usage": 0,
              "capacity": 0,
              "resizeMaxScalingObservationPeriod": 0,
              "resizeScalingAggressiveness": 0
            }
          ]
        }
      ],
      "epoch": "HISTORICAL"
    }
  ],
  "temporary": true,
  "activeEntitiesCount": 0,
  "cloudType": "AWS",
  "source": {
    "links": [
      {
        "rel": {}
      }
    ],
    "uuid": "string",
    "displayName": "string",
    "className": "string",
    "category": "Hypervisor",
    "isProbeRegistered": false,
    "uiCategory": "Application Server, Billing, Cloud Management, Applications and Databases, Fabric and Network, Guest OS Processes, HYPERCONVERGED, HYPERVISOR, Load Balancer, Operations Manager Appliance, ORCHESTRATOR, PaaS, Storage, Storage Browsing, WINDOWS APPLICATION. There are also categories Custom and UNKNOWN to be used for new probe development.",
    "identifyingFields": [
      "string"
    ],
    "inputFields": [
      {
        "links": [
          {
            "rel": {}
          }
        ],
        "uuid": "string",
        "displayName": "string",
        "className": "string",
        "name": "string",
        "value": "string",
        "defaultValue": "string",
        "isMandatory": true,
        "isSecret": true,
        "isMultiline": true,
        "isTargetDisplayName": true,
        "valueType": "STRING",
        "specificValueType": "string",
        "description": "string",
        "verificationRegex": "string",
        "groupProperties": [
          [
            "string"
          ]
        ],
        "allowedValues": [
          "string"
        ],
        "dependencyKey": "string",
        "dependencyValue": "one|two|four"
      }
    ],
    "lastValidated": "string",
    "status": "Validated, VALIDATION FAILED, UNKNOWN",
    "derivedTargets": [
      "string"
    ],
    "patchedTargets": [
      {
        "probeType": "string",
        "patchedFields": [
          {
            "fieldName": "string",
            "fieldValue": "string"
          }
        ]
      }
    ],
    "parentTargets": [
      "string"
    ],
    "type": "string",
    "subType": "RedHatOpenShift",
    "readonly": true,
    "healthSummary": {
      "healthState": "NORMAL",
      "rollupState": "NORMAL",
      "timeOfLastSuccessfulDiscovery": "2021-07-07T20:33:49Z"
    },
    "discoveryMode": "PAUSED"
  },
  "memberTypes": [
    "string"
  ],
  "entityTypes": [
    "string"
  ],
  "aspects": {
    "additionalProp1": {
      "type": "string",
      "sli": [
        "string"
      ]
    },
    "additionalProp2": {
      "type": "string",
      "sli": [
        "string"
      ]
    },
    "additionalProp3": {
      "type": "string",
      "sli": [
        "string"
      ]
    }
  },
  "vendorIds": {
    "additionalProp1": "string",
    "additionalProp2": "string",
    "additionalProp3": "string"
  },
  "groupOrigin": "DISCOVERED",
  "targetType": "string",
  "groupClassName": "string"
}

```

**Update Group**<br/>

**Create Policy**<br/>

**Update Policy**<br/>
