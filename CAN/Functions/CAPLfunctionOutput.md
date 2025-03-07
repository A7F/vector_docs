[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Functions/CAPLfunctionOutput.md)

**CAPL Functions** » **CAN** » **output (CAN)**

# output (CAN)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `void output(message msg); // form 1`
- `void output(errorFrame); // form 2`

## Description

Outputs a message (form 1) or an Error Frame (form 2) from the program block.

## Parameters

- **msg**: Variable of type message.
- **errorFrame**: Variable of type errorFrame.

## Return Values

—

## Example

**output(msg) Example**

```plaintext
variables {
    message can2.125 msg = { // define CAN message 
        dlc = 1,
        byte(0) = 1
    };
}
on key F1 {
    output (msg); // output Message
}
```

**output(errorFrame) Example**

```plaintext
on key F10 {
    output(errorFrame); // output Error Frame on CAN channel 1
}
on CAN2.errorFrame {
    output (CAN3.errorFrame); // output Error Frame on CAN channel 3
}
```

Except for the first channel for all other channels the key word **errorFrame** has to be qualified with the number of the CAN channel.

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)