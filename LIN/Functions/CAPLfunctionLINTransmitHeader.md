[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINTransmitHeader.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linTransmitHeader

# linTransmitHeader

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword linTransmitHeader(dword frameId); // form 1
dword linTransmitHeader(linFrame frame); // form 2
```

## Description

Transmits a frame header for a specific LIN frame.

**Note**

Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **frameId**: ID of the LIN frame whose header will be transmitted.  
  Value range: 0..63

- **frame**: The LIN frame whose header will be transmitted.

## Return Values

Returns **1** if the transmission succeeded, otherwise **0**.

## Example

```plaintext
// Transmit a LIN header with the id 0x01

linFrame 0x01 frm1;
linTransmitHeader(frm1);
```

[linUpdateResponse](CAPLfunctionLINUpdateResponse.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
