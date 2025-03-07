[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILSelectInputObject.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Virtual Terminal Interaction Layer (VT IL)](../CAPLfunctionsISOILVTOverview.md) » VTIL_SelectInputObject, VTIL_SelectInputObjectMsg

# VTIL_SelectInputObject, VTIL_SelectInputObjectMsg

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long VTIL_SelectInputObject(dword objectId); // form 1`
- `long VTIL_SelectInputObject(dbNode vt, dword objectId); // form 2`
- `long VTIL_SelectInputObject(dword objectId, byte openMode); // form 3`
- `long VTIL_SelectInputObject(dbNode vt, dword objectId, dword openMode); // form 4`
- `long VTIL_SelectInputObjectMsg(dword objectId, dword objectIsSelected, dword openMode); // form 5`
- `long VTIL_SelectInputObjectMsg(dbNode vt, dword objectId, dword objectIsSelected, dword openMode); // form 6`

## Description

Select an input field, Button or Key object.

The VTIL_SelectInputObject methods simulate the selection of an input field, button, or key object by the user. As a result:

- VT Select Input Object message (selection = **deselected**) for object which loses focus (if any) is sent;
- VT Select Input Object message (selection = **selected**, optionally bitmask = **object is open for data input**) for Object with ID **objectId** is sent;

The VTIL_SelectInputObjectMsg methods send only the VT Select Input Object message (without influencing any button or input object and without triggering any event in the Virtual Terminal). You can use it to implement fault injection.

If an input object is open for data input, the value of the object can be modified with [VTIL_EditNumericValue](CAPLfunctionIso11783VTILEditNumericValue.md) or [VTIL_EditStringValue](CAPLfunctionIso11783VTILEditStringValue.md). To close an input object which is open for data input, you have to use this command with openMode **0**.

## Parameters

- **vt**: VT simulation node to apply the function
- **objectId**: Object ID of an input field, Button or Key object
- **objectIsSelected**:
  - 0: Object is deselected
  - 1: Object is selected (has focus)
- **openMode**:
  - 0: Select object or close open object
  - 1: Open object for data input

## Return Values

- **0**: Blocking of all messages has been stopped successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md).

## Example

**Example 1: Form 2, 4 and 6**

```plaintext
//to simulate: operator navigates to the object with ID=220

long result;
result = VTIL_SelectInputObject(VT, 220);
switch (result)
{
  case 0: TestStepPass(); break;
  case -2102: TestStepFail("Invalid object!"); break;
  case -2104: TestStepFail("Currently there is no active Working Set!"); break;
  case -2106: TestStepFail("Currently there is no active Data or Alarm mask!"); break;
  case -2112: TestStepFail("Invalid open mode!"); break;
  case -2115: TestStepFail("VT works in passive mode therefore you cannot select objects!"); break;
  case -2116: TestStepFail("Failed to select object!"); break;
  default: TestStepFail("Unexpected error!"); break;
}
```

**Example 2: Form 2, 4 and 6**

Simulation of realtime editing:

```plaintext
//to simulate: Realtime Editing of the numeric object with ID=220

VTIL_SelectInputObject(VT, 220, 1); // open for editing
TestWaitForTimeout(200);
VTIL_EditNumericValue(VT, 220, 1, 0); //type "1"
TestWaitForTimeout(500);
VTIL_EditNumericValue(VT, 220, 12, 0); //type additionally "2"
TestWaitForTimeout(600);
VTIL_EditNumericValue(VT, 220, 123, 0);  //type additionally "3"
TestWaitForTimeout(400);
VTIL_SelectInputObject(VT, 220, 0);    //finish editing
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)