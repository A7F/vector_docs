[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/FlexRay/Functions/CAPLfunctionFRGetFrameCRC.md)

[CAPL Functions](../../CAPLfunctions.md) » [FlexRay](../CAPLfunctionsFlexrayOverview.md) » frGetFrameCRC

# frGetFrameCRC

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
dword frGetFrameCRC(this);
```

## Description

This function returns the CRC of a received FlexRay frame. The Header CRC can be determined with a special selector of the event procedure.

## Parameters

- **this**  
  The function can only be used in the context of the following event procedures:
  - [on frRSlot](../EventProcedures/CAPLfunctionOnFRSlot.md)
  - [on frFrame](../EventProcedures/CAPLfunctionOnFRFrame.md)
  - [on frNullFrame](../EventProcedures/CAPLfunctionOnFRNnullFrame.md)
  - [on frFrameError](../EventProcedures/CAPLfunctionOnFRFrameError.md)

  `this` references the corresponding receive object in the event procedure.

## Return Values

- **Frame CRC (data type WORD)**  
  The return value is only valid if the frame was received by a Vector FlexRay network interface in asynchronous monitor mode. In any other case 0 will be sent back.

## Example

The following example writes the CRC into the Write Window for all received frames.

```capl
on frFrame *
{
   dword crc;
   crc = frGetFrameCRC(this);
   Write("Frame %d in Cycle %d has CRC 0x%x", this.FR_SlotID, this.FR_Cycle, crc);
   output(this); // only required in Measurement Setup
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)