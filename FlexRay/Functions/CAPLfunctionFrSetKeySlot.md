[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/FlexRay/Functions/CAPLfunctionFrSetKeySlot.md)

# frSetKeySlot

[CAPL Functions](../../CAPLfunctions.md) » [FlexRay](../CAPLfunctionsFlexrayOverview.md) » frSetKeySlot

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
void frSetKeySlot (long channel, long channelMask, long keySlotIndex, long keySlotId, long keySlotUsage);
```

## Description

Configures one of two possible key slots that are to be sent for a FlexRay bus. The change will be applied with the next reset of the interface hardware (e.g. by [resetFlexRayCC](CAPLfunctionResetFlexrayCC.md) or [resetFlexRayCCEx](CAPLfunctionResetFlexrayCCEX.md)).

## Parameters

- **channel**: Channel number (or cluster number)
- **channelMask**: Channel of the transmission frame.  
  Values:  
  - 1: Channel A
  - 2: Channel B
  - 3: Channel A+B
- **keySlotIndex**: Addresses the desired key slot (1 or 2).
- **keySlotId**: This number designates a specific FlexRay slot in the static segment. Its value must be between 1 and 1023.
- **keySlotUsage**: Defines the mode of the key slot:
  - 0: Off
  - 1: Startup/Sync (Allowing Leading Coldstart)
  - 2: Sync
  - 3: Startup/Sync

## Return Values

—

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
