[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimConnectSysVarToFunctionState.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » **Iso11783IL_TIMConnectSysVarToFunctionState**

# Iso11783IL_TIMConnectSysVarToFunctionState

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_TIMConnectSysVarToFunctionState(dword functionID, char[] sysVarNameWithPath); // form 1
long Iso11783IL_TIMConnectSysVarToFunctionState(dbNode participant, dword functionID, char[] sysVarNameWithPath); // form 2
```

## Description

Connects the automation state of a TIM function to a system variable.

- **State 0**: Automation unavailable
- **State 1**: Automation not ready
- **State 2**: Automation ready to enable
- **State 3**: Automation enabled
- **State 4**: Automation pending
- **State 5**: Active, not limited
- **State 6**: Active, limited high
- **State 7**: Active, limited low
- **State 14**: Non-recoverable fault
- **State 15**: Not available (parameter not supported or not configured for TIM)

If this function is used by a TIM client, the system variable only changes if the TIM function is assigned by the client. To release the connection between the system variable and the function, call the same method again with an empty string instead of the name of the system variable. You can also use the callback function [Iso11783IL_TIMOnFunctionStateChanged](CAPLfunctionIso11783ILtimOnFunctionStateChanged.md) if you are interested in the state of a function.

## Parameters

- **functionID**: Function ID of the function.
  - **Function ID 1-32 (1h-20h)**: Auxiliary Value 1 – 32, Supported Since TIM Version 1
  - **Function ID 64 (40h)**: Front PTO, Supported Since TIM Version 1
  - **Function ID 65 (41h)**: Rear PTO, Supported Since TIM Version 1
  - **Function ID 66 (42h)**: Front hitch, Supported Since TIM Version 1
  - **Function ID 67 (43h)**: Rear hitch, Supported Since TIM Version 1
  - **Function ID 68 (44h)**: Vehicle speed, Supported Since TIM Version 1
  - **Function ID 70 (46h)**: External guidance, Supported Since TIM Version 1
  - **Function ID 71 (47h)**: Front top linkage, Supported Since TIM Version 2
  - **Function ID 72 (48h)**: Rear top linkage, Supported Since TIM Version 2

- **participant**: TIM simulation node (TIM Client or TIM Server) to apply the function.

- **sysVarNameWithPath**: Name of the system variable, all namespaces inclusive.

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
Iso11783IL_TIMConnectSysVarToFunctionState(0, "sysvarAuxValve1State");
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
