[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPGetState.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_OPGetState

# Iso11783IL_OPGetState

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_OPGetState(); // form 1
long Iso11783IL_OPGetState(dbNode implement); // form 2
```

## Description

Returns the state of the Object Pool API.

## Parameters

- **implement**: Simulation node to apply the function.

## Return Values

- **0**: Not active
- **1**: Wait until ECU is online
- **2**: Wait for status message from VT
- **3**: Initialization phase with the VT
- **4**: Object Pool Upload active or Load Version active
- **5**: Active
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
state = Iso11783IL_OPGetState();
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)