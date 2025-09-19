[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPDeleteObjectPool.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_OPDeleteObjectPool

# Iso11783IL_OPDeleteObjectPool

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_OPDeleteObjectPool(); // form 1
long Iso11783IL_OPDeleteObjectPool(dbNode implement); // form 2
```

## Description

The function sends the **Delete Object Pool** message to the connected Virtual Terminal.

The simulated node neither clears the loaded Object Pool nor stops to send the **Working Set Maintenance** message to the Virtual Terminal.

For simultaneous clearing of the loaded Object Pool and stopping the **Working Set Maintenance** message, call the [Iso11783IL_OPDeactivate()](CAPLfunctionIso11783ILOPDeactivate.md) instead.

## Parameters

- **implement**: Simulation node to apply the function.

## Return Values

- **= 0**: Function has been executed successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

**Example Form 2**

```plaintext
long result;
result = Iso11783IL_OPDeleteObjectPool(Sprayer);
if (result < 0)
{
  TestStepFail("Failed to send the Delete Object Pool mesage");
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
