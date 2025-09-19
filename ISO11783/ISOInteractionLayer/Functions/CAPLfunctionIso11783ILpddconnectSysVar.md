[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILpddconnectSysVar.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » Iso11783IL_PDDConnectSysVar

# Iso11783IL_PDDConnectSysVar

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_PDDConnectSysVar( dword ddi, dword elementNumber, char sysVarNameWithPath[] ); // form 1
long Iso11783IL_PDDConnectSysVar(  dbNode implement, dword ddi, dword elementNumber, char sysVarNameWithPath[] ); // form 2
```

## Description

Connects an object from the loaded Process Data Description (PDD) (on Implement side) with a system variable.

The connected system variable receives the value that was sent by the Task Controller to the ECU via **Set Value and Acknowledge** command or **Set Value** command and modified the object value in the object pool on the implement side.

If the system variable in CANoe DE product itself is modified (e.g., in CAPL or in a panel), the value of the process variable in the PDD on implement side is modified. This value can then be requested by the Task Controller with a **Request Value** command or transferred to the Task Controller by the implement itself as logging.

To release connection between the system variable and an object from the PDD, just call the same method again, but with the empty string instead of the name of system variable.

## Parameters

- **ddi**: Data dictionary identifier 0x000..0xFFFF
- **elementNumber**: Element number, 0x000..0xFFF
- **sysVarNameWithPath**: Name of the system variable, all namespaces inclusive.
- **implement**: Simulation node to apply the function.

## Return Values

- **0**: function has been executed successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
int ret;
ret = Iso11783IL_PDDConnectSysVar(0x6, 0x1, "ConnectedSysVars::svIntVar");//connect
...
ret = Iso11783IL_PDDConnectSysVar(0x6, 0x1, "");//release
```

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
