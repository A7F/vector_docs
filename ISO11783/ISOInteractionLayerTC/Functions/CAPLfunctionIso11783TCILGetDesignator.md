[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILGetDesignator.md)

**CAPL Functions** » **ISO11783** » **Task Controller Interaction Layer (TC IL)** » **TCIL_GetDesignator**

# TCIL_GetDesignator

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TCIL_GetDesignator(dbNode client, dword ddi, dword elementNumber, dword unitDesignatorBufferSize, char unitDesignatorBuffer[]); // form 1: deprecated with 13`
- `long TCIL_GetDesignator(dbNode client, dword ddi, dword elementNumber, char unitDesignatorBuffer[]); // form 2`
- `long TCIL_GetDesignator(dword addresClient, dword ddi, dword elementNumber, char unitDesignatorBuffer[]); // form 3`
- `long TCIL_GetDesignator(dbNode tc, dbNode client, dword ddi, dword elementNumber, dword unitDesignatorBufferSize, char unitDesignatorBuffer[]); // form 4: deprecated with 13`
- `long TCIL_GetDesignator(dbNode tc, dbNode client, dword ddi, dword elementNumber, char unitDesignatorBuffer[]); // form 5`
- `long TCIL_GetDesignator(dbNode tc, dword addresClient, dword ddi, dword elementNumber, char unitDesignatorBuffer[]); // form 6`

## Description

Returns the designator of DeviceProcessData (DPD) or DeviceProperty (DPT) object defined by DDI/elementNumber. Form 5 and 6 applicable in test module / test unit only.

## Parameters

- **tc**: TC simulation node to apply the function.
- **client**: TC client node the data entity belongs to.
- **addressClient**: TC client node the data entity belongs to.
- **ddi**: Data dictionary identifier, 0x0000..0xFFFF.
- **elementNumber**: Element number, 0x000..0xFFF.
- **unitDesignatorBufferSize**: Size of the return buffer.
- **unitDesignatorBuffer**: Return buffer. Contains the designator as a string.

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

Example form 5

```c
long result;
char designator[256];
// Retrieve the designator for the DPD with DDI=17 and elementNumber=3 from DDOP uploaded by Sprayer to TC
result = TCIL_GetDesignator(TC, Sprayer, 17 /*DDI/, 3 /elementNumber/, designator /buffer/);
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)