# EnergyCommunityProduction

## Description

An energy production measurement entity for a community member, extending the [SolarEnergy](https://github.com/smart-data-models/dataModel.Energy/tree/master/SolarEnergy) Smart Data Model. Captures real-time and cumulative energy generation from solar panels or wind turbines via microinverters.

This entity type extends concepts from [dataModel.Energy/SolarEnergy](https://github.com/smart-data-models/dataModel.Energy/tree/master/SolarEnergy) to provide community-specific production tracking, linking each measurement to a specific community member and their microinverter device. The `sourceType` property distinguishes between solar and wind energy sources.

## Properties

| Property | Type | Required | Description |
|----------|------|----------|-------------|
| id | string (URI) | Yes | Unique identifier in URN format (`urn:ngsi-ld:EnergyCommunityProduction:<instance-id>`) |
| type | string | Yes | NGSI-LD entity type. Must be `EnergyCommunityProduction` |
| activePower | number | Yes | Current power output in Watts (W). Must be ≥ 0 |
| dateObserved | string (DateTime) | Yes | Timestamp of the measurement observation (ISO 8601) |
| refMember | string (URI) | Yes | URN reference to the [EnergyCommunityMember](../EnergyCommunityMember/) entity that owns this production installation |
| activeEnergyGenerated | number | No | Cumulative energy produced in kWh. Must be ≥ 0 |
| sourceType | string (enum) | No | Energy source type: `solar` or `wind` |
| panelEfficiency | number | No | Current panel efficiency in percent (%) |
| irradiance | number | No | Solar irradiance on panel surface in W/m² |
| address | object | No | Postal address of the production installation |
| location | GeoProperty (object) | No | GeoJSON Point representing the geographic location of the production installation |
| refDevice | string (URI) | No | URN reference to the microinverter device entity |

## Relationships

| Relationship | Target Entity | Cardinality | Description |
|---|---|---|---|
| refMember | [EnergyCommunityMember](../EnergyCommunityMember/) | 1 (required) | The community member that owns this production installation |
| refDevice | Device (Microinverter) | 0..1 | The microinverter device producing this measurement |

## Links

- [Schema definition](./schema.json)
- [Example entities](./examples/)
  - [Normalized format](./examples/example-normalized.jsonld)
  - [Key-values format](./examples/example-keyvalues.jsonld)
