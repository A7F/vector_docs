[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILPressSoftKey.md)

## CAPL Functions » ISO11783 » Virtual Terminal Interaction Layer (VT IL) » VTIL_PressSoftKey, VTIL_SoftKeyActivationMsg

### Valid for: CANoe DE • CANoe4SW DE

### Function Syntax

- `long VTIL_PressSoftKey(dword objectId, dword duration); // form 1`
- `long VTIL_PressSoftKey(dword objectId, dword duration, dword parentId); // form 2`
- `long VTIL_PressSoftKey(dbNode vt, dword objectId, dword duration); // form 3`
- `long VTIL_PressSoftKey(dbNode vt, dword objectId, dword duration, dword parentId); // form 4`
- `long VTIL_SoftKeyActivationMsg(dword objectId, dword parentId, byte keyActivationCode, byte keyNumber); // form 5`
- `long VTIL_SoftKeyActivationMsg(dbNode vt, dword objectId, dword parentId, byte keyActivationCode, byte keyNumber); // form 6`

### Description

The `VTIL_PressSoftKey` methods simulate the pressing of a Soft Key and the releasing of it after the duration. As a result, the Soft Key Activation Message is immediately sent with the key activation code = **pressed**, then every 200 ms with the key activation code = **still held** and after the duration with the key activation code = **released**.

For form 1 and 3 the Soft Key must be part of the active Soft Key Mask. Otherwise, the function will return with an error code and no messages will be sent.

In contrast, forms 2, 4, 5 and 6 do not check whether the Soft Key belongs to the given Soft Key mask or whether the Soft Key is active or visible.

The `VTIL_SoftKeyActivationMsg` methods only send the Soft Key Activation message (without triggering any event in the Virtual Terminal).

You can also use these methods to simulate the press of the ACK means of the Virtual Terminal to acknowledge an alarm mask. For this the **objectId** must be **0xFFFF** and **parentId** has to be equal to the ID of the current alarm mask.

### Parameters

- **vt**: VT simulation node to apply the function
- **objectId**: Object ID of the Soft Key
- **parentId**: Object ID of the visible Data Mask, Alarm Mask, or in the case where the Soft Key is in a visible Key Group, the Object ID of the Key Group Object, that is to be sent with the corresponding Soft Key Activation message (without checking whether the soft key really belongs to the given Data/Alarm/Key Group Object mask or whether the Soft Key is active or visible).
- **duration**: Time while the key is held [ms]. If duration is < 200 ms then only the commands **Key has been pressed** and **Key has been released** are sent. Else the command **Key is still pressed** is sent too.
- **keyActivationCode**:
  - 0: Key has been released (state change)
  - 1: Key has been pressed (state change)
  - 2: Key is still pressed
  - 3: Key press aborted
- **keyNumber**: Overwrites the key number of the Soft Key object

### Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

### Example

```plaintext
long result;
result = VTIL_PressSoftKey(VT, 6011, 250);
switch (result)
{
  case 0: TestStepPass(); break;
  case -2102: TestStepFail("Invalid object!"); break;
  case -2104: TestStepFail("Currently there is no active Working Set!"); break;
  case -2107: TestStepFail("Currently there is no active Soft Key Mask!"); break;
  case -2115: TestStepFail("VT works in passive mode therefore you cannot press keys!"); break;
  default: TestStepFail("Unexpected error"); break;
}
```

© Vector Informatik GmbH
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)