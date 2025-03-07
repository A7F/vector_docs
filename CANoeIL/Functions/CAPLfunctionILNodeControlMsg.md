[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANoeIL/Functions/CAPLfunctionILNodeControlMsg.md)

**CAPL Functions** » **CANoe IL** » **ILNodeControlMsg**

# ILNodeControlMsg

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

### Note
- This function is not available for all OEM add-ons — depends on the CANoeIL.
- This function can be used in a global node outside the node context of the IL and in test modules.

## Function Syntax

- `ILNodeControlMsg(dbMsg msg, dword control, dword flags, dword param1, dword param2); // form 1`
- `ILNodeControlMsg(char messageName[], dword control, dword flags, dword param1, dword param2); // form 2`
- `ILNodeControlMsg(dword msgId, dword control, dword flags, dword param1, dword param2); // form 3`

## Description

This generic function influences the sending of a certain message of a simulation node with an assigned CANoe Interaction Layer. The meaning of the parameters flags, **param1** and **param2** depends on the parameter control.

## Parameters

- **msg**: Message that should be influenced.
- **messageName**: Name of the message that should be influenced.
- **msgId**: CAN identifier of the message that should be influenced.
- **control**: Specifies the manner of influencing the message.
  - `control = 1`: Enables sending of the message. Parameters **param1**, **param2** have no meaning. Parameter **flags** is evaluated bitwise:
    - `0x1`: One message is sent immediately if the message would be sent cyclically under the current conditions.
    - `0x2`: One message is sent immediately independently from current conditions. This is also true for noncyclic messages.
    - `0x4`: The send pattern of cyclic messages is shifted with the time instance of calling the function as new basis.
  - `control = 2`: Disables sending of the message. Parameters **flags**, **param1**, **param2** have no meaning.
- **flags, param1, param2**: See parameter control for meaning.

## Return Values

- **0**: No error
- **-10000**: Unspecific error
- **-10001**: Node or module not found
- **-10002**: No suitable module available
- **-10003**: Function is not supported by module
- **-10004**: Module returns illegal value
- **other**: Error in module

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)