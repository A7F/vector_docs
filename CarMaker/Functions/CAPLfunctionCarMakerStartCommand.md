[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CarMaker/Functions/CAPLfunctionCarMakerStartCommand.md)

**CAPL Functions** » **CarMaker Interface** » **CarMaker_StartCommand**

# CarMaker_StartCommand

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long CarMaker_StartCommand(char host[char command[]);
```

## Description

Asynchronously calls a generic command and ignores the result.

## Parameters

- **command**: CarMaker script command including parameters.

## Return Values

[APO return code](../CAPLfunctionsCarMakerReturnCodes.md)

## Example

```plaintext
// stop test series after the current TestRun has ﬁnished
gErrorState = CarMaker_StartCommand("TestMgr stop");
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)