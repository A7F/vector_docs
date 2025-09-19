[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILGetDwordValue.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Virtual Terminal Interaction Layer (VT IL)](../CAPLfunctionsISOILVTOverview.md) » VTIL_GetDwordValue, VTIL_GetDoubleValue, VTIL_GetStringValue

# VTIL_GetDwordValue, VTIL_GetDoubleValue, VTIL_GetStringValue

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long VTIL_GetDwordValue(dbNode workingSetMaster, dword objectId, dword & value); // form 1`
- `long VTIL_GetDwordValue(dword addressWorkingSetMaster, dword objectId, dword & value); // form 2`
- `long VTIL_GetDwordValue(dbNode workingSetMaster, dword objectId, dword attributeID, dword & value); // form 3`
- `long VTIL_GetDwordValue(dword addressWorkingSetMaster, dword objectId, dword attributeID, dword & value); // form 4`
- `long VTIL_GetDwordValue(dbNode vt, dbNode workingSetMaster, dword objectId, dword & value); // form 5`
- `long VTIL_GetDwordValue(dbNode vt, dword addressWorkingSetMaster, dword objectId, dword & value); // form 6`
- `long VTIL_GetDwordValue(dbNode vt, dbNode workingSetMaster, dword objectId, dword attributeID, dword & value); // form 7`
- `long VTIL_GetDwordValue(dbNode vt, dword addressWorkingSetMaster, dword objectId, dword attributeID, dword & value); // form 8`
- `long VTIL_GetDoubleValue(dbNode workingSetMaster, dword objectId, dword attributeID, double & value); // form 9`
- `long VTIL_GetDoubleValue(dword addressWorkingSetMaster, dword objectId, dword attributeID, double & value); // form 10`
- `long VTIL_GetDoubleValue(dbNode vt, dbNode workingSetMaster, dword objectId, dword attributeID, double & value); // form 11`
- `long VTIL_GetDoubleValue(dbNode vt, dword addressWorkingSetMaster, dword objectId, dword attributeID, double & value); // form 12`
- `long VTIL_GetStringValue(dbNode workingSetMaster, dword objectId, char* value, dword bufferLength); // form 13`
- `long VTIL_GetStringValue(dword addressWorkingSetMaster, dword objectId, char* value, dword bufferLength); // form 14`
- `long VTIL_GetStringValue(dbNode vt, dbNode workingSetMaster, dword objectId, char* value, dword bufferLength); // form 15`
- `long VTIL_GetStringValue(dbNode vt, dword addressWorkingSetMaster, dword objectId, char* value, dword bufferLength); // form 16`
- `long VTIL_GetStringValue(dbNode workingSetMaster, dword objectId, char* value); // form 17`
- `long VTIL_GetStringValue(dword addressWorkingSetMaster, dword objectId, char* value); // form 18`
- `long VTIL_GetStringValue(dbNode vt, dbNode workingSetMaster, dword objectId, char* value); // form 19`
- `long VTIL_GetStringValue(dbNode vt, dword addressWorkingSetMaster, dword objectId, char* value); // form 20`

## Description

Returns the value of an object or of an object attribute.

You can use **VTIL_GetDoubleValue** or **VTIL_GetDwordValue** without attribute ID to get the numeric value of a Key object, Button object or an object that supports the **Change Numeric Value** command. You can use **VTIL_GetStringValue** to get the string value of an Input String, Output String, String Variable or an Input Attribute object.

## Parameters

- **vt**: VT simulation node to apply the function
- **workingSetMaster**: Working Set Master which provides the Object Pool
- **addressWorkingSetMaster**: Address of the Working Set Master which provides the Object Pool
- **objectId**: Object ID the attribute belongs to
- **attributeID**: Identifies the necessary attribute (correlate to the **AID** column of corresponding object definitions from Annex B (Iso11783-6)
- **value**: Returns the value of the object or attribute

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

Example forms 5, 6, 7, 8, 11, 12, 15, 16, 19, 20

```c
long result;
char buf[100];
result = VTIL_GetStringValue(VT, 128, 205, buf);  // Form 20 is used
switch (result)
{
  case 0:
    write("Current value of object 205 is '%s'", buf);
    TestStepPass();
    break;
  case -2102: TestStepFail("Invalid object!"); break;
  case -2104: TestStepFail("Currently there is no active Working Set!"); break;
  case -2108: TestStepFail("Invalid variable reference!"); break;
  default:    TestStepFail("Unexpected error!"); break;
}
```

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
