[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestSetEcuOnline.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestSetEcuOnline

# TestSetEcuOnline

[Feature availabilty for your product](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void testSetEcuOnline (dbNode aNode);
void testSetEcuOnline (char aNodeName[]);
```

## Description

Connects the ECU to the bus. After calling the [testSetEcuOffline()](CAPLfunctionTestSetEcuOffline.md) function the ECU can be reconnected to the bus by using the testSetEcuOnline() function. Messages being sent by the ECU will be forwarded to the bus.

This function interferes with the CAPL program and possible modeling library.

## Parameters

- **aNode**: ECU to be switched online (must be defined in the database).
- **aNodeName**: Name of the ECU to be switched online (must be defined in the database).

  Node name can optionally specified by an additional qualifier:
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