[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINGetDLC.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linGetDlc

# linGetDlc

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
long linGetDlc(long frameID);
```

## Description

Queries the Data Length Code (i.e. length in bytes) of a LIN frame.

- Per default, the DLC of LIN frames is initialized according to the LIN Description File (LDF).
- If no LDF is used, this function returns the DLC initialized in [on preStart](../../Other/EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md) for LIN frames sent by simulated LIN nodes.
- For LIN frames whose DLC has not been initialized, this function will return the default DLC for the selected ID as defined in the LIN1.1 protocol specification.
- For LIN frames sent by external LIN nodes, the measured DLC is returned.

## Parameters

- **frameID**: LIN frame identifier in the range 0 .. 63.

## Return Values

If successful, the frame length [in bytes] or -1 on failure.

## Example

Verify correct DLC is used by a certain frame

```c
...
if ( linGetDLC(0x22) != 5)
{
    linSetExpectedRespLength(0x22, 5); // set DLC of frame with identifier 0x22 to be 5
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
