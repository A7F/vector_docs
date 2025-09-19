[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783PDDsetdistance.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Node Layer** » Iso11783PDDSetDistance

# Iso11783PDDSetDistance

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783PDDSetDistance( dword ecuHandle, dword distance );
```

## Description

The distance covered is set with this function. The value is needed for the distance trigger and should be updated cyclically.

## Parameters

- **ecuHandle**: Handle of the ECU. The handle must previously have been created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md).
- **distance**: Distance covered in [m].

## Return Values

[Error code](../CAPLfunctionsISONLErrorCodesPDDOnError.md)

## Example

```plaintext
void ReceiveGBSDFromTractor( pg GroundBasesSpeedPG thisPG ){
  Iso11783PDDSetDistance( ecuHandle, thisPG.GroundBasedDistance.phys );
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
