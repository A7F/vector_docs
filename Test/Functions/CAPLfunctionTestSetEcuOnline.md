# TestSetEcuOnline

[Feature availabilty for your product](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```c
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

```c
// cuts the node ‚SUT’ 5000 ms from the bus
TestSetEcuOffline(SUT);
TestWaitForTimeout(5000);
TestSetEcuOnline(SUT)
```
