# EnergyCommunityConsumption

## Description

An energy consumption measurement entity for a community member, derived from the [ACMeasurement](https://github.com/smart-data-models/dataModel.Energy/tree/master/ACMeasurement) Smart Data Model. Captures active and reactive power, energy import/export, voltage, and frequency readings from smart meters installed at member households.

This entity type extends concepts from [dataModel.Energy/ACMeasurement](https://github.com/smart-data-models/dataModel.Energy/tree/master/ACMeasurement) to provide community-specific consumption tracking, linking each measurement to a specific community member and their smart meter device.

## Properties

| Property | Type | Required | Description |
|----------|------|----------|-------------|
| id | string (URI) | Yes | Unique identifier in URN format (`urn:ngsi-ld:EnergyCommunityConsumption:<instance-id>`) |
| type | string | Yes | NGSI-LD entity type. Must be `EnergyCommunityConsumption` |
| activePower | number | Yes | Current active power consumption in Watts (W). Must be ≥ 0 |
| dateObserved | string (DateTime) | Yes | Timestamp of the measurement observation (ISO 8601) |
| refMember | string (URI) | Yes | URN reference to the [EnergyCommunityMember](../EnergyCommunityMember/) entity |
| reactivePower | number | No | Reactive power measured by the smart meter in Volt-Ampere reactive (VAr) |
| activeEnergyImport | number | No | Cumulative active energy imported from the grid in kWh. Must be ≥ 0 |
| activeEnergyExport | number | No | Cumulative active energy exported to the grid in kWh. Must be ≥ 0 |
| voltage | number | No | Line voltage measured at the smart meter in Volts (V) |
| frequency | number | No | Grid frequency measured at the smart meter in Hertz (Hz) |
| address | object | No | Postal address of the smart meter location |
| location | GeoProperty (object) | No | GeoJSON Point geometry representing the smart meter location |
| refDevice | string (URI) | No | URN reference to the smart meter device entity |

## Relationships

| Relationship | Target Entity | Cardinality | Description |
|---|---|---|---|
| refMember | [EnergyCommunityMember](../EnergyCommunityMember/) | 1 (required) | The community member associated with this consumption measurement |
| refDevice | Device (Smart Meter) | 0..1 | The smart meter device producing this measurement |

## Links

- [Schema definition](./schema.json)
- [Example entities](./examples/)
  - [Normalized format](./examples/example-normalized.jsonld)
  - [Key-values format](./examples/example-keyvalues.jsonld)
