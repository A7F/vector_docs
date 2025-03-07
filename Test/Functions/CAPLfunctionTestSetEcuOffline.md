[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestSetEcuOffline.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestSetEcuOffline

# TestSetEcuOffline

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void testSetEcuOffline (dbNode aNode);
void testSetEcuOffline (char aNodeName[]);
```

## Description

Disconnects the ECU from the bus. Messages being sent by the ECU will not be forwarded to the bus. With the [testSetEcuOnline](CAPLfunctionTestSetEcuOnline.md) function the ECU can be reconnected to the bus.

This function interferes with the CAPL program and possible modeling library.

## Parameters

- **aNode**: ECU to be switched offline (must be defined in the database).
- **aNodeName**: Name of the ECU to be switched offline (must be defined in the database).
  - Node name can optionally specified by an additional qualifier:
    - NodeName
    - BusName::NodeName

## Return Values

—

## Example

```plaintext
// cuts the node ‚SUT’ 5000 ms from the bus
TestSetEcuOffline(SUT);
TestWaitForTimeout(5000);
TestSetEcuOnline(SUT)
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)