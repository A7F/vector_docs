[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILConnectSysVarWithSection.md)

**CAPL Functions** » **ISO11783** » **Task Controller Interaction Layer (TC IL)** » **TCIL_ConnectSysVarWithSection**

# TCIL_ConnectSysVarWithSection

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
If parameter **address** is used the function succeeds only if the client has claimed an address.

## Function Syntax

```plaintext
long TCIL_ConnectSysVarWithSection(dbNode client, dword ddiOfCondensedState, dword elementNumber, dword sectionNumber, char[] sysVarNameWithPath); // form 1

long TCIL_ConnectSysVarWithSection(dword addressClient, dword ddiOfCondensedState, dword elementNumber, dword sectionNumber, char[] sysVarNameWithPath); // form 2

long TCIL_ConnectSysVarWithSection(dbNode tc, dbNode client, dword ddiOfCondensedState, dword elementNumber, dword sectionNumber, char[] sysVarNameWithPath); // form 3

long TCIL_ConnectSysVarWithSection(dbNode tc, dword addressClient, dword ddiOfCondensedState, dword elementNumber, dword sectionNumber, char[] sysVarNameWithPath); // form 4
```

## Description

This function connects a single section state to a system variable.

If a section state is changed the new value is put into the system variable. To release connection between the system variable and the condensed state, just call the same method again, but with the empty string instead of the name of system variable.

## Parameters

- **ddiOfCondensedState**: Data dictionary identifier the condensed state belongs to, e.g.:
  - 161..176 (0x0A1..0x0B0) for **Actual Condensed Work State**
  - 290..305 (0x122..0x131) for **Setpoint Condensed Work State**
  - 367..382 (0x16F..0x17E) for **Condensed Section Override State**

- **elementNumber**: Element number of the data entity, 0x000..0xFFF.

- **sectionNumber**: Section number within the object, 1..256.

- **sysVarNameWithPath**: Name of the system variable, all namespaces inclusive.

- **client**: Task Controller client which provides the device descriptor object pool with corresponding sections.

- **addressClient**: Address of the Task Controller client which provides the device descriptor object pool with corresponding sections.

- **tc**: Task Controller simulation node to apply the function.

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

**Example form 2**

```plaintext
long result;
result = TCIL_ConnectSysVarWithSection(TC, Sprayer, 162, 1, 20, Sprayer::svActualCondensedWorkStateSection20");
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
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
