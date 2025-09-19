[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPOnStateChange.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » **Iso11783IL_OPOnStateChange**

# Iso11783IL_OPOnStateChange

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void Iso11783IL_OPOnStateChange( dword state );
```

## Description

The function is called by the node layer, if the state of the Object Pool API has changed.

## Parameters

- **state**: State of the Object Pool API
  - 0: not active
  - 1: wait until ECU is online
  - 2: wait for the status message from the VT
  - 3: initialization phase with the VT
  - 4: object pool upload is active or load version active
  - 5: active

## Return Values

—

## Example

```plaintext
void Iso11783IL_OPOnStateChange( dword state )
{
}
```

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
