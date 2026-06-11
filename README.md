# dataModel.EnergyCommunity

A FIWARE Smart Data Model for an **Energy Community Platform** that enables communities to jointly generate, share, and trade energy. This data model captures household energy consumption (via smart meters), energy production (via solar panels and windmills), battery storage state, community membership, and the community organization itself. 

It is based on [dataModel.Energy](https://github.com/smart-data-models/dataModel.Energy). 

The model follows [NGSI-LD](https://www.etsi.org/deliver/etsi_gs/CIM/001_099/009/01.06.01_60/gs_CIM009v010601p.pdf) standards and is structured according to [Smart Data Models](https://smartdatamodels.org) conventions.

## Entity Types

| Entity Type | Description |
|---|---|
| [EnergyCommunity](./EnergyCommunity/) | The energy community organization — defines the community name, type, total members, installed capacity, area served, and links to its members. |
| [EnergyCommunityMember](./EnergyCommunityMember/) | A household or participant in the energy community — captures member name, role (producer/consumer/prosumer), membership status, and links to the community and owned devices. |
| [EnergyCommunityConsumption](./EnergyCommunityConsumption/) | Smart meter energy consumption readings — extends [ACMeasurement](https://github.com/smart-data-models/dataModel.Energy/tree/master/ACMeasurement) with community-specific relationships (refMember, refDevice). Captures active/reactive power, energy import/export, voltage, and frequency. |
| [EnergyCommunityProduction](./EnergyCommunityProduction/) | Solar or wind energy production readings — extends [SolarEnergy](https://github.com/smart-data-models/dataModel.Energy/tree/master/SolarEnergy) with source type differentiation and community relationships. Captures power output, energy generated, irradiance, and panel efficiency. |
| [EnergyCommunityStorage](./EnergyCommunityStorage/) | Battery charge/discharge state — extends [StorageBatteryMeasurement](https://github.com/smart-data-models/dataModel.Battery/tree/master/StorageBatteryMeasurement) with community relationships. Captures battery level, state of charge, power in/out, capacity, and operating status. |

## Base Models Referenced

This data model extends and references the following existing Smart Data Models:

| Base Model | Repository | Used By |
|---|---|---|
| [ACMeasurement](https://github.com/smart-data-models/dataModel.Energy/tree/master/ACMeasurement) | [dataModel.Energy](https://github.com/smart-data-models/dataModel.Energy) | [EnergyCommunityConsumption](./EnergyCommunityConsumption/) |
| [SolarEnergy](https://github.com/smart-data-models/dataModel.Energy/tree/master/SolarEnergy) | [dataModel.Energy](https://github.com/smart-data-models/dataModel.Energy) | [EnergyCommunityProduction](./EnergyCommunityProduction/) |
| [StorageBatteryMeasurement](https://github.com/smart-data-models/dataModel.Battery/tree/master/StorageBatteryMeasurement) | [dataModel.Battery](https://github.com/smart-data-models/dataModel.Battery) | [EnergyCommunityStorage](./EnergyCommunityStorage/) |

### List of data models from [dataModel.Energy](https://github.com/smart-data-models/dataModel.Energy)

The following entity types are available:
- [ACMeasurement](https://github.com/smart-data-models/dataModel.Energy/blob/master/ACMeasurement/README.md). The Data Model intended to measure the electrical energies consumed by an electrical system which uses an Alternating Current (AC) for a three-phase (L1, L2, L3) or single-phase (L) and neutral (N). It integrates the initial version of the data Modem [THREEPHASEMEASUREMENT], extended to also perform single-phase measurements. It includes attributes for various electrical measurements such as power, frequency, current and voltage.

- [InverterDevice](https://github.com/smart-data-models/dataModel.Energy/blob/master/InverterDevice/README.md). The data model is intended to describe the mechanical, electrical characteristics of an Inverter according to *DC - Direct Current Information* supplied as input and *AC - Alternating Current Information*  returned as output. *Remark*: This Data Model can be used directly as a main entity to describe the device [Inverter] or as a sub-entity of the Data Model {DEVICE] using a reference by the [refDevice] attribute.

- [SolarEnergy](https://github.com/smart-data-models/dataModel.Energy/blob/master/SolarEnergy/README.md). A Data Model for Solar Energy generation.

- [TechnicalCabinetDevice](https://github.com/smart-data-models/dataModel.Energy/blob/master/TechnicalCabinetDevice/README.md). Technical Cabinet Device Data Model is intended to to describe the technical characteristics of the Device, designed to be placed in an urban or interurban environment. The main objective of these cabinets for this Data Model is to protect the electrical equipment necessary for the control, surveillance, reading and management of urban lighting, signaling, video and electrical distribution. The scope of use of some of these cabinets can extend to an additional protection for installations of modular apparatuses of telephony, data processing, meteorological stations, photo-voltaic stations, wind turbines stations, telecommunications, networks, data, bre Optics , etc. *Remark* : This Data Model can be used directly as a main entity to describe the device `Technical Cabinet`  or as a sub-entity of the Data Model  `DEVICE` using a reference by the `refDevice` attribute. It can also refer to the list of all the components it contains, with the `refDeviceList` attribute, using the Data Model 'DEVICE'

- [ThreePhaseAcMeasurement](https://github.com/smart-data-models/dataModel.Energy/blob/master/ThreePhaseAcMeasurement/README.md). An electrical  measurement from a system that uses three phase alternating current.



### Contributors (dataModel.Energy)
[Link](https://github.com/smart-data-models/dataModel.Energy/blob/master/CONTRIBUTORS.yaml) to the 6 current contributors of the data models of this Subject.


### Contribution (dataModel.Energy)
You can raise an [issue](https://github.com/smart-data-models/dataModel.Energy/issues) or submit your [PR](https://github.com/smart-data-models/dataModel.Energy/pulls) on existing data models


