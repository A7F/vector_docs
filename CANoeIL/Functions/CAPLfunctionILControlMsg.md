[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANoeIL/Functions/CAPLfunctionILControlMsg.md)

[CAPL Functions](../../CAPLfunctions.md) » [CANoe IL](../CAPLfunctionsCANoeILOverview.md) » ILControlMsg

# ILControlMsg

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This function can only be used in the CAPL file that is attached to the appropriate node. The corresponding function [ILNodeControlMsg](CAPLfunctionILNodeControlMsg.md) can be used in a global node outside or in test modules.

## Function Syntax

`ILControlMsg(dbMsg msg, dword control, dword flags, dword param1, dword param2)`

## Description

Allows to manipulate the sending behavior of a message.

## Parameters

- **msg**: Message that should be influenced.
- **control**: Specifies the manner of influencing the message.
  - `control = 1`: Enables sending of the message (comparable to function [ILEnableMsg](CAPLfunctionILEnableMsg.md)).
    - Parameter **param1**, **param2** have no meaning.
    - Parameter **flags** is evaluated bitwise:
      - `0x1`: One message is sent immediately if the message would be sent cyclically under the current conditions.
      - `0x2`: One message is sent immediately independently from current conditions. This is also true for noncyclic messages.
      - `0x4`: The send pattern of cyclic messages is shifted with the time instance of calling the function as new basis.
  - `control = 2`: Disables sending of the message (comparable to function [ILDisableMsg](CAPLfunctionILDisableMsg.md)).
    - Parameter **flags**, **param1**, **param2** have no meaning.
- **flags, param1, param2**: See parameter control for meaning.

## Return Values

- **0**: No error.
- **1**: Momentary state of the IL does not permit this query.
- **50**: Node layer is inactive — possibly deactivated in the node's configuration dialog.

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)