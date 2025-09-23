[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILConnectSysVar.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Virtual Terminal Interaction Layer (VT IL)](../CAPLfunctionsISOILVTOverview.md) » VTIL_ConnectSysVar

# VTIL_ConnectSysVar

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
If parameter **address** is used the function succeeds only if the client has claimed an address.

## Function Syntax

```plaintext
long VTIL_ConnectSysVar(dbNode workingSetMaster, dword objectId, char[] sysVarNameWithPath); // form 1
long VTIL_ConnectSysVar(dword addressWorkingSetMaster, dword objectId, char[] sysVarNameWithPath); // form 2
long VTIL_ConnectSysVar(dbNode vt, dbNode workingSetMaster, dword objectId, char[] sysVarNameWithPath); // form 3
long VTIL_ConnectSysVar(dbNode vt, dword addressWorkingSetMaster, dword objectId, char[] sysVarNameWithPath); // form 4
```

## Description

Connects an object from the object pool to a system variable. Valid objects are variables, objects representing values or string, buttons and soft keys.

If a variable object or an object representing a values or a string is changed, the new value is put into the system variable.

To release connection between the system variable and an object, just call the same method again, but with the empty string instead of the name of system variable.

## Parameters

- **vt**: VT simulation node to apply the function
- **workingSetMaster**: Working Set Master which provides the Object Pool
- **addressWorkingSetMaster**: Address of the Working Set Master which provides the Object Pool
- **sysVarNameWithPath**: Name of the system variable, all namespaces inclusive
- **objectId**: Identifier of the object in the object pool

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

**Example for 3, 4**

```plaintext
long result;
result = VTIL_ConnectSysVar(VT, Sprayer, 221, "VT::svValueInt32");
switch (result)
{
  case 0:
    write("Object 12 is successfully connected with svValueInt32");
    TestStepPass();
    break;
  case -2109: TestStepFail("Working Set is not available!"); break;
  case -2113: TestStepFail("Invalid Parameter!"); break;
  case -2114: TestStepFail("Invalid system variable path!"); break;
  default:    TestStepFail("Unexpected error!"); break;
}
```
