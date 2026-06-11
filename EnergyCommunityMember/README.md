# EnergyCommunityMember

## Description

An Energy Community Member entity representing a participant in an energy community. Each member has a defined role (producer, consumer, or prosumer), belongs to a specific community, and may be associated with one or more devices such as smart meters, microinverters, or batteries.

This is a custom entity type that links community-level organization to the individual measurement entities ([EnergyCommunityConsumption](../EnergyCommunityConsumption/), [EnergyCommunityProduction](../EnergyCommunityProduction/), [EnergyCommunityStorage](../EnergyCommunityStorage/)).

## Properties

| Property | Type | Required | Description |
|----------|------|----------|-------------|
| id | string (URI) | Yes | Unique identifier in URN format (`urn:ngsi-ld:EnergyCommunityMember:<instance-id>`) |
| type | string | Yes | NGSI-LD entity type. Must be `EnergyCommunityMember` |
| memberName | string | Yes | Name of the community member |
| memberRole | string (enum) | Yes | Role in the community: `producer`, `consumer`, or `prosumer` |
| refCommunity | string (URI) | Yes | URN reference to the parent [EnergyCommunity](../EnergyCommunity/) entity |
| membershipStatus | string (enum) | No | Current membership status: `active` or `inactive` |
| joinDate | string (DateTime) | No | Date and time when the member joined the community (ISO 8601) |
| address | object | No | Postal address of the community member |
| location | GeoProperty (object) | No | GeoJSON Point representing the geographic location of the member |
| hasDevices | array of URIs | No | URN references to device entities (smart meters, microinverters, batteries) |

## Relationships

| Relationship | Target Entity | Cardinality | Description |
|---|---|---|---|
| refCommunity | [EnergyCommunity](../EnergyCommunity/) | 1 (required) | The energy community this member belongs to |
| hasDevices | Device | 0..* | Devices associated with this member (smart meters, microinverters, batteries) |

## Links

- [Schema definition](./schema.json)
- [Example entities](./examples/)
  - [Normalized format](./examples/example-normalized.jsonld)
  - [Key-values format](./examples/example-keyvalues.jsonld)
