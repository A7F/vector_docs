[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/KLine/Functions/CAPLfunctionDiagPreSend.md)

**CAPL Functions** » **K-Line** » _Diag_PreSend

# _Diag_PreSend

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
_Diag_Presend(BYTE data[], WORD& dataLenInOut, WORD headerLen)
```

## Description

Is called before a frame is transmitted. Allows manipulating the frame.

## Parameters

- **data**: Transmitted data buffer of the frame.
- **dataLenInOut**: Indicates the length of the frame when _Diag_PreSend is called. Determines the length of the frame before the frame is transmitted.
- **headerLen**: Length of the header of a frame. Not supported yet.

## Return Values

—

## Example

```c
_Diag_Presend(BYTE data[], WORD& dataLenInOut, WORD headerLen)
{
    if (!gDoPatchInPreSend) // Global variable
    {
        return;
    }

    gDoPatchInPreSend = 0; // deactivate patching

    // Changing the data and the length of the request
    data[2] = 0x99;
    data[3] = 0x99;
    dataLenInOut = 4;
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
