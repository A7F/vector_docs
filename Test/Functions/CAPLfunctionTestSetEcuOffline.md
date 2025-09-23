# TestSetEcuOffline

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```c
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

```c
// cuts the node ‚SUT’ 5000 ms from the bus
TestSetEcuOffline(SUT);
TestWaitForTimeout(5000);
TestSetEcuOnline(SUT)
```
