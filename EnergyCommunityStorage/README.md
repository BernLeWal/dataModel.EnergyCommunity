# EnergyCommunityStorage

## Description

An energy storage (battery) measurement entity for a community member, derived from the [StorageBatteryMeasurement](https://github.com/smart-data-models/dataModel.Battery/tree/master/StorageBatteryMeasurement) Smart Data Model. Captures battery level, state of charge, power in/out, capacity, and operating status for community-connected battery systems.

This entity type extends concepts from [dataModel.Battery/StorageBatteryMeasurement](https://github.com/smart-data-models/dataModel.Battery/tree/master/StorageBatteryMeasurement) to provide community-specific storage tracking, linking each measurement to a specific community member and their battery device.

## Properties

| Property | Type | Required | Description |
|----------|------|----------|-------------|
| id | string (URI) | Yes | Unique identifier in URN format (`urn:ngsi-ld:EnergyCommunityStorage:<instance-id>`) |
| type | string | Yes | NGSI-LD entity type. Must be `EnergyCommunityStorage` |
| batteryLevel | number | Yes | Current battery charge level as a percentage (0–100) |
| stateOfCharge | number | Yes | State of charge in ampere-hours (Ah) or kilowatt-hours (kWh) |
| dateObserved | string (DateTime) | Yes | Timestamp of the measurement observation (ISO 8601) |
| refMember | string (URI) | Yes | URN reference to the [EnergyCommunityMember](../EnergyCommunityMember/) entity |
| activePowerIn | number | No | Active power flowing into the battery (charging) in Watts (W). Must be ≥ 0 |
| activePowerOut | number | No | Active power flowing out of the battery (discharging) in Watts (W). Must be ≥ 0 |
| batteryCapacity | number | No | Total energy capacity of the battery in kWh |
| operatingStatus | string (enum) | No | Current operating status: `charging`, `discharging`, or `idle` |
| address | object | No | Postal address of the battery storage location |
| location | GeoProperty (object) | No | GeoJSON Point geometry representing the battery storage location |
| refDevice | string (URI) | No | URN reference to the battery device entity |

## Relationships

| Relationship | Target Entity | Cardinality | Description |
|---|---|---|---|
| refMember | [EnergyCommunityMember](../EnergyCommunityMember/) | 1 (required) | The community member associated with this storage measurement |
| refDevice | Device (Battery) | 0..1 | The battery device producing this measurement |

## Links

- [Schema definition](./schema.json)
- [Example entities](./examples/)
  - [Normalized format](./examples/example-normalized.jsonld)
  - [Key-values format](./examples/example-keyvalues.jsonld)
