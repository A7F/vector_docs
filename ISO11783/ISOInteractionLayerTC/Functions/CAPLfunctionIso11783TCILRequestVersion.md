[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILRequestVersion.md)

## TCIL_RequestVersion

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Task Controller Interaction Layer (TC IL)](../CAPLfunctionsISOILTCOverview.md) » TCIL_RequestVersion

### Function Syntax

- `long TCIL_RequestVersion(dbNode client); // form 1`
- `long TCIL_RequestVersion(dword addressClient); // form 2`
- `long TCIL_RequestVersion(dbNode tc, dbNode client); // form 3`
- `long TCIL_RequestVersion(dbNode tc, dword addressClient); // form 4`

### Description

This function requests the Version message from the client.

### Parameters

- **tc**: Task Controller simulation node to apply the function.
- **client**: Task Controller client node the TC sends the **Request Version** to.
- **addressClient**: Address of the Task Controller client node the TC sends the **Request Version** to.

### Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

### Example

Example form 3

```c
long result;
result = TCIL_RequestVersion(TC, Sprayer);
switch (result)
{
  case     0: TestStepPass(); break;
  case -2202: TestStepFail("Function is not available in passive mode of the TC IL!"); break;
  case -2204: TestStepFail("Node 'Sprayer' is no client device!"); break;
  case -2210: TestStepFail("Failed to send Request Version message!"); break;
  default:    TestStepFail("Unexpected error"); break;
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)