[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILSetResponseContent.md)

## VTIL_SetResponseContent

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Virtual Terminal Interaction Layer (VT IL)](../CAPLfunctionsISOILVTOverview.md) » VTIL_SetResponseContent

### Tool Availability
[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

### Function Syntax

- `long VTIL_SetResponseContent(dbNode workingSetMaster, byte vtFunction, pg VT12 pgWithNewContent); // form 1`
- `long VTIL_SetResponseContent(dword addressWorkingSetMaster, byte vtFunction, pg VT12 pgWithNewContent); // form 2`
- `long VTIL_SetResponseContent(dbNode vt, dbNode workingSetMaster, byte vtFunction, pg VT12 pgWithNewContent); // form 3`
- `long VTIL_SetResponseContent(dbNode vt, dword addressWorkingSetMaster, byte vtFunction, pg VT12 pgWithNewContent); // form 4`

### Description

The function changes the content of the next VT response VT12 sent by the VT IL to allow fault injection.

### Parameters

- **vt**: VT simulation node to apply the function.
- **workingSetMaster**: Receiver of the VT12 response message.
- **addressWorkingSetMaster**: Address of the Receiver of the VT12 response message.
- **vtFunction**: The function refers to the response with this VT function value.
- **pgWithNewContent**: This message replaces the VT12 response of the VT IL.

### Return Values

- **0**: Blocking of all messages has been stopped successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md).

### Example

Example form 3, 4

```plaintext
long result;
pg VT12 vt12;
J1939InitPGData(vt12);
vt12.VTFunctionVTtoECU = 168; // Change numeric value response
vt12.ObjectToChangeNumValueID = objectID;
vt12.byte(3) = errorCodes;
vt12.ValueOfTheObject = value;
result = VTIL_SetResponseContent(VT, Sprayer, 168, vt12);
if (result < 0)
{
  TestStepFail("Failed to change Numeric Value response");
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
