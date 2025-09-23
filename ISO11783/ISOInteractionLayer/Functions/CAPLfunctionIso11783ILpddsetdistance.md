[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILpddsetdistance.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » Iso11783IL_PDDSetDistance

# Iso11783IL_PDDSetDistance

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_PDDSetDistance( dword distance ); // form 1
long Iso11783IL_PDDSetDistance( dbNode implement, dword distance ); // form 2
```

## Description

The distance covered is set with this function. The value is needed for the distance trigger and should be updated cyclically.

## Parameters

- **distance**: distance covered in [m]
- **implement**: Simulation node to apply the function.

## Return Values

- **0**: function has been executed successfully
- **< 0**: an error has occurred

## Example

```plaintext
void ReceiveGBSDFromTractor( 
 pg GroundBasesSpeedPG thisPG ){
  Iso11783IL_PDDSetDistance( thisPG.GroundBasedDistance.phys );
}
```
