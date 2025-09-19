[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILPDDSetLogTrigger.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » Iso11783IL_PDDSetLogTrigger

# Iso11783IL_PDDSetLogTrigger

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_PDDSetLogTrigger( dword command, ulong ddi, ulong elNum, ulong value ); // form 1
long Iso11783IL_PDDSetLogTrigger( dbNode implement, dword command, ulong ddi, ulong elNum, ulong value ); // form 2
```

## Description

A measurement command can be executed with this function. It can be used in the callback function [Iso11783IL_PDDOnDefaultLogRequest](CAPLfunctionIso11783ILPDDOnDefaultLogRequest.md) to activate the default logging.

## Parameters

- **command**: measurement command:
  - 4: Time Interval
  - 5: Distance Interval
  - 6: Minimum within Threshold
  - 7: Maximum within Threshold
  - 8: Change Threshold

- **ddi**: Data Dictionary Identifier, 0x0000..0xFFFF

- **elNum**: element number, 0x000..0xFFF

- **value**: depends on **command**
  - **Time Interval**: time in ms
  - **Distance Interval**: distance in mm
  - **Minimum within Threshold**, **Maximum within Threshold**, **Change Threshold**: value of the process variable
  - use value 0 to disable a trigger

- **implement**: Simulation node to apply the function.

## Return Values

- **0**: function has been executed successfully
- **< 0**: an error has occurred

## Example

```plaintext
void Iso11783IL_PDDOnDefaultLogRequest ()
{
    Iso11783IL_PDDSetLogTrigger( 4, 0x0100, 0, 1000 );
    Iso11783IL_PDDSetLogTrigger( 4, 0x0101, 0, 1000 );
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
