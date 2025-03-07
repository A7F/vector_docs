[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CarMaker/Functions/CAPLfunctionCarMakerInvokeCommand.md)

**CAPL Functions** » **CarMaker Interface** » **CarMaker_InvokeCommand**

# CarMaker_InvokeCommand

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long CarMaker_InvokeCommand(char command[], char result[], long resultSize);
```

## Description

Synchronously calls a generic command and stores the result.

## Parameters

- **command**: CarMaker script command including parameters.
- **result**: Output buffer for the result text.
- **resultSize**: Size of the output buffer.

## Return Values

[APO return code](../CAPLfunctionsCarMakerReturnCodes.md)

## Example

```plaintext
long status;
char result[200];
status = CarMaker_InvokeCommand("TestMgr get Result", result, elcount(result));
write("Status: 0x%lx  Result: \"%s\"", status, result);
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)