[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/CAPLfunctionsCANopenOverview.md)

**CAPL Functions** » **CANopen**

# CANopen

**Valid for:** CANoe DE • CANoe:lite DE • CANoe4SW DE

**CANopen**

Only available with Option CANopen.

---

### CANopen Basic

- [CAPL Functions](CANopenBasic/CAPLfunctionsCANopenBasicOverview.md)

Starting with CANoe 10.0 the CANopen basic functions replace the CANopen node layer functions. See below.

Also available: Test Feature Set for CANopen

### CANopen Node Layer (deprecated)

**Note**

The CANopen node layer is still supported for capability with CANoe versions up to and including 9.0 SP6. It was replaced by the [Simulation Concept](../../CANoeCANalyzer/CANopen/OptionCANopen/extensionsProCANopen.md#SimulationConcept) that is supported starting with CANoe 10.0.

The CANopen® Node Layer can be assigned to every node in the simulation structure. It simplifies the simulation of CANopen nodes and offers CANopen specific functions:

- Realizing the object dictionary
- Communication status machine
- Guarding and Heartbeat
- Processing PDOs

### CANopen Test Feature Set Node Layer

- [CAPL Functions](NodeLayerTFS/CAPLfunctionsCANopenNLTFSLevelOverview.md)

The Test Feature Set test module for CANopen can be assigned to any test module within CANoe. This test module makes available the following functionality:

- SDO protocol tests
- NMT tests
- Heartbeat tests
- Guarding tests
- Emergency tests
- SDO response time statistics
- User callbacks for sync messages/PDOs, heartbeat and callback events
- PDO tests
- Object dictionary tests
- SDO timing tests

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)