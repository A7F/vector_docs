[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILMakeDdopAvailable.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Task Controller Interaction Layer (TC IL)](../CAPLfunctionsISOILTCOverview.md) » TCIL_MakeDdopAvailable

# TCIL_MakeDdopAvailable

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long TCIL_MakeDdopAvailable(char[] ddopPath[]); // form 1
long TCIL_MakeDdopAvailable(dbNode tc, char[] ddopPath[]); // form 2
```

## Description

Loads a device descriptor object pool (DDOP) into the Task Controller. Represents the situation that the DDOP is available on the side of Task Controller (e.g. via task file). An available DDOP can be activated with the Object-pool Activate message.

## Parameters

- **tc**: Task Controller simulation node to apply the function.
- **ddopPath**: Path of the DDOP file (*.XML). Path has to be absolute or relative relating to the folder of the CANoe configuration.

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

Example form 2

```plaintext
long result;
result = TCIL_MakeDdopAvailable(TC, "xml\\sprayerV1.xml");
if (result < 0)
{
  TestStepFail("Failed to make DDOP file available!");
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
