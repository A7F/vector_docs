[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINtpSetNAD.md)

**CAPL Functions** » **LIN** » **LINtp_SetNAD**

# LINtp_SetNAD

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long LINtp_SetNAD(long NAD);
```

## Description

In a slave node, sets its node address for communication with the master.

## Parameters

- **NAD**: Node address [1, 126]

## Return Values

- **0**: Setting address failed (this is a master or node address is invalid)
- **1**: Success
- **other**: reserved

## Example

—