[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILPDDConnectSysVarWithSection.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_PDDConnectSysVarWithSection

# Iso11783IL_PDDConnectSysVarWithSection

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_PDDConnectSysVarWithSection(dword ddiOfCondensedState, dword elementNumber, dword sectionNumber, char[] sysVarNameWithPath); // form 1
long Iso11783IL_PDDConnectSysVarWithSection(dbNode implement, dword ddiOfCondensedState, dword elementNumber, dword sectionNumber, char[] sysVarNameWithPath); // form 2
```

## Description

Connects a single section state to a system variable. If a section state is changed the new value is put into the system variable. To release connection between the system variable and the condensed state, just call the same method again, but with the empty string instead of the name of system variable.

## Parameters

- **ddiOfCondensedState**: Data dictionary identifier the condensed state belongs to, e.g.:
  - 161..176 (0x0A1..0x0B0) for Actual Condensed Work State
  - 290..305 (0x122..0x131) for Setpoint Condensed Work State
  - 367..382 (0x16F..0x17E) for Condensed Section Override State

- **elementNumber**: Element number, 0x000..0xFFF.

- **sectionNumber**: Section number within the object, 1..256.

- **sysVarNameWithPath**: Name of the system variable, all namespaces inclusive.

- **implement**: Simulation node to apply the function.

## Return Values

- **0**: function has been executed successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
long result;
char text[256];
result = Iso11783IL_PDDConnectSysVarWithSection(290, 10, 1, "ConnectedSysVars::svSection1");
if (result < 0)
{
  Iso11783IL_GetLastErrorText ( elCount(text), text );
  write( "ERROR: %s", text);
}
```

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
