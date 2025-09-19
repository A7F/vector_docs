[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/XCP/Functions/CAPLfunctionXCPActivate.md)

[CAPL Functions](../../CAPLfunctions.md) » [XCP](../CAPLfunctionsXCPOverview.md) » xcpActivate

# xcpActivate

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**

- xcpActivate must not be used in [on preStart](../../Other/CAPLfunctionsEventProceduresOverview.md)!
- Parameters that are measured via polling can be activated in state **connected** (e.g., after [xcpConnect](CAPLfunctionXCPConnect.md)). Parameters measured via DAQ can be activated either in [on Start](../../Other/CAPLfunctionsEventProceduresOverview.md) directly or later in state **disconnected** (e.g., after [xcpDisconnect](CAPLfunctionXCPDisconnect.md)).

## Function Syntax

```plaintext
long xcpActivate (char namespace[], char variable[]); // form 1
long xcpActivate (sysvar sysvar);
```

## Description

Activates an a2l parameter for upload and DAQ measurement.

**Note**

Using system variables [structs](../../../Shared/CAPL/General/Structures.md), the function must be used for the variable valid for the entire struct but not for single members.

## Parameters

- **namespace**: Namespace of the corresponding system variable.
- **variable**: Name of the corresponding system variable.
- **sysVar**: Name of the fully qualified name of the system variable, including all namespaces, separated by "::". The name must be preceded by "sysVar::".

## Return Values

- **0**: OK
- **-1**: System variable was not found
- **-2**: Operation not allowed

## Example

```plaintext
on start
{
    if(0 == XcpActivate(sysvar::XCP::XcpSim::ampl))
    {
        write("Parameter ampl activated for measurement");
    }
}
```

[xcpDeactivate](CAPLfunctionXCPDeactivate.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
