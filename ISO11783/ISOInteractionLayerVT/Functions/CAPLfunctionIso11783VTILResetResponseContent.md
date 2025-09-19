[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILResetResponseContent.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Virtual Terminal Interaction Layer (VT IL)](../CAPLfunctionsISOILVTOverview.md) » VTIL_ResetResponseContent

# VTIL_ResetResponseContent

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long VTIL_ResetResponseContent(dbNode workingSetMaster, byte vtFunction); // form 1`
- `long VTIL_ResetResponseContent(dword addressWorkingSetMaster, byte vtFunction); // form 2`
- `long VTIL_ResetResponseContent(dbNode vt, dbNode workingSetMaster, byte vtFunction); // form 3`
- `long VTIL_ResetResponseContent(dbNode vt, dword addressWorkingSetMaster, byte vtFunction); // form 4`

## Description

The function resets the response modification of [VTIL_SetResponseContent](CAPLfunctionIso11783VTILSetResponseContent.md). Afterwards, the default response is sent by the VT IL.

## Parameters

- **vt**: VT simulation node to apply the function
- **workingSetMaster**: Receiver of the VT12 response message
- **addressWorkingSetMaster**: Address of the Receiver of the VT12 response message
- **vtFunction**: The function refers to the response with this VT function value

## Return Values

- **0**: Blocking of all messages has been stopped successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md).

## Example

Example form 3, 4

```plaintext
long result;
result = VTIL_ResetResponseContent(VT, Sprayer, 168);
if (result < 0)
{
  TestStepFail("Failed to reset fault injection");
}
```

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
