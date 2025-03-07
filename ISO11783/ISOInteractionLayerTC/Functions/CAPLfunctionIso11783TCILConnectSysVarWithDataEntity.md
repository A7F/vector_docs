[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILConnectSysVarWithDataEntity.md)

## TCIL_ConnectSysVarWithDataEntity

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Task Controller Interaction Layer (TC IL)](../CAPLfunctionsISOILTCOverview.md) » TCIL_ConnectSysVarWithDataEntity

### Tool Availability

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

### Note

If parameter **address** is used the function succeeds only if the client has claimed an address.

### Function Syntax

```plaintext
long TCIL_ConnectSysVarWithDataEntity(dbNode client, dword ddi, dword elementNumber, char[]sysVarNameWithPath, dword useRawValue); // form 1
long TCIL_ConnectSysVarWithDataEntity(dword addressClient, dword ddi, dword elementNumber, char[]sysVarNameWithPath, dword useRawValue); // form 2
long TCIL_ConnectSysVarWithDataEntity(dbNode tc, dbNode client, dword ddi, dword elementNumber, char[]sysVarNameWithPath, dword useRawValue); // form 3
long TCIL_ConnectSysVarWithDataEntity(dbNode tc, dword addressClient, dword ddi, dword elementNumber, char[]sysVarNameWithPath, dword useRawValue); // form 4
```

### Description

This function connects a data entity specified by the data dictionary identifier to a system variable. If the value of the data entity is changed, the new value is put into the system variable. To release connection between the system variable and data entity, just call the same method again, but with the empty string instead of the name of system variable.

### Parameters

- **ddi**: Data dictionary identifier of the data entity, 0x0000..0xFFFF.
- **elementNumber**: Element number of the data entity, 0x000..0xFFF.
- **sysVarNameWithPath**: Name of the system variable, all namespaces inclusive.
- **useRawValue**:
  - 1: The connected system variable represents the raw value of data entity. This variant can be used even if the corresponding device descriptor object pool is not uploaded to the Task Controller simulated by TC IL.
  - 0: The connected system variable represents the physical value of data entry. Precondition: The corresponding device descriptor object pool has to be uploaded to Task Controller simulated by TC IL and the data entry belongs to the device descriptor object pool.
- **client**: Task Controller client which provides the device descriptor object pool with corresponding data entity.
- **addressClient**: Address of the Task Controller client which provides the device descriptor object pool with corresponding data entity.
- **tc**: Task Controller simulation node to apply the function.

### Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

### Example

Example form 3

```plaintext
result = TCIL_ConnectSysVarWithDataEntity(TC, Sprayer, 117, 1, "Sprayer::svEffectiveTotalDistance", 1);
switch (result)
{
  case     0: TestStepPass(); break;
  case -2203: TestStepFail("Invalid system variable path!"); break;
  case -2211: TestStepFail("System variable does not exist!"); break;
  default   : TestStepFail("Unexpected error!"); break;
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)