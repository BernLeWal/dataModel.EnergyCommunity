# EnergyCommunity

## Description

An Energy Community entity representing a community-level organization for joint energy generation, sharing, and trading. Based on the Austrian EEG (Erneuerbare-Energie-Gemeinschaft) model, this entity captures the top-level community information including its members, total capacity, and geographic area of operation.

This is a custom entity type specific to the Energy Community domain, serving as the root entity that aggregates all community members and their associated devices.

## Properties

| Property | Type | Required | Description |
|----------|------|----------|-------------|
| id | string (URI) | Yes | Unique identifier in URN format (`urn:ngsi-ld:EnergyCommunity:<instance-id>`) |
| type | string | Yes | NGSI-LD entity type. Must be `EnergyCommunity` |
| communityName | string | Yes | Name of the energy community |
| communityType | string (enum) | Yes | Type of energy community: `EEG`, `BEG`, or `CEC` |
| totalMembers | integer | No | Total number of members in the energy community (≥ 0) |
| totalCapacityKW | number | No | Total installed generation capacity of the community in kilowatts (kW) (≥ 0) |
| address | object | No | Postal address of the energy community's registered office |
| areaServed | GeoProperty (object) | No | Geographic area served by the community, as GeoJSON geometry (Point, Polygon, or MultiPolygon) |
| foundedDate | string (DateTime) | No | Date and time when the community was officially founded (ISO 8601) |
| hasMembers | array of URIs | No | Array of URN references to [EnergyCommunityMember](../EnergyCommunityMember/) entities |

## Relationships

| Relationship | Target Entity | Cardinality | Description |
|---|---|---|---|
| hasMembers | [EnergyCommunityMember](../EnergyCommunityMember/) | 1..* | References all member entities that belong to this energy community |

## Links

- [Schema definition](./schema.json)
- [Example entities](./examples/)
  - [Normalized format](./examples/example-normalized.jsonld)
  - [Key-values format](./examples/example-keyvalues.jsonld)
