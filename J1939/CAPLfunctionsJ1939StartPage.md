[J1939 CAPL Functions](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/CAPLfunctionsJ1939StartPage.md)

[CAPL Functions](../CAPLfunctions.md) » J1939 CAPL Functions

# J1939 CAPL Functions

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**J1939**

Only available with Option J1939.

## General

- [Functions & Event Procedures](CAPLfunctionsJ1939Overview.md)
- [Access PGNs of Database Messages](CAPLfunctionsJ1939AccessPGN.md)
- [Define Parameter Groups](CAPLfunctionsJ1939DefinePG.md)
- [Specific Language Limitations](CAPLfunctionsJ1939Limitations.md)
- [Parameter Group Selectors](CAPLfunctionJ1939GroupSelectors.md)

## Interaction Layer

**J1939 Interaction Layer (J1939 IL)**

The J1939 Interaction Layer provides signal-based access to the J1939 bus. The mapping of the signals on the Tx messages is done according to the configuration in the used database. The J1939 IL manages the Tx messages, Rx messages are handled directly by CANoe and can be processed in CAPL.

- [CAPL Functions](J1939InteractionLayer/CAPLfunctionsJ1939ILOverview.md)
- [Error Codes](../CAPLfunctionsISOj1939ErrorCodes.md)

**GB/T 27930 Interaction Layer**

- [CAPL Functions](GBT27930InteractionLayer/CAPLfunctionsGBT27930ILOverview.md)
- [Error Codes](../CAPLfunctionsISOj1939ErrorCodes.md)

## J1939 Test

**Test Feature Set**

The CANoe Test Feature Set contains a set of functions optimized for J1939 requirements:

- [TestWaitForJ1939PG](../Test/Functions/CAPLfunctionTestWaitForJ1939PG.md)
- [TestJoinJ1939PGEvent](../Test/Functions/CAPLfunctionTestJoinJ1939PGEvent.md)
- [TestWaitForJ1939DTC](../Test/Functions/CAPLfunctionTestWaitForJ1939DTC.md)
- [TestWaitForJ1939DmWithoutSPN](../Test/Functions/CAPLfunctionTestWaitForJ1939DmWithoutSPN.md)
- [TestJoinJ1939DTCEvent](../Test/Functions/CAPLfunctionTestJoinJ1939DTCEvent.md)
- [TestGetWaitJ1939PGData](../Test/Functions/CAPLfunctionTestGetWaitJ1939PGData.md)

**J1939 Test Service Library (J1939 TSL) (deprecated)**

The J1939 TSL extends the Test Feature Set with J1939 specific functions. The functions can be used in CAPL and XML test modules.

## Node Layer

**GNSS Node Layer**

The GNSS (Global Navigation Satellite System) Node Layer is used to simulate a GNSS receiver. These virtual receivers can be used to supply other devices on the network with position data. GNSS positions are transferred cyclically with configurable messages.

- [CAPL Functions](GNSSNodeLayer/CAPLfunctionsGNSSNLOverview.md)
- [Error Codes GNSSAppErrorIndication](GNSSNodeLayer/CAPLfunctionsGNSSNLErrorCodesAppErrorIndication.md)
- [Error Codes GNSSGetLastError](GNSSNodeLayer/CAPLfunctionsGNSSNLErrorCodesGetLastError.md)

### J1939 Node Layer (deprecated)

The J1939 Node Layer simplifies the simulation of a J1939 node with CAPL.

- [Functions](J1939NodeLayer/CAPLfunctionsJ1939NLOverview.md)
- [Error Codes](J1939NodeLayer/CAPLfunctionsJ1939NLErrorCodes.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
