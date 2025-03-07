[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADFX/Functions/CAPLfunctionAfdxCopyOperator.md)

[CAPL Functions](../../CAPLfunctions.md) » [AFDX »](../CAPLfunctionsAFDXOverview.md) AFDX Copy-Operator

# AFDX Copy-Operator

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

`target-object = source-object`

## Description

The copy-operator allows to copy the following object combinations:

1. A664Message on A664Message
2. A664Message on A664Frame
3. A664Frame on A664Frame

**Note**: It is explicitly not allowed to copy a A664Frame onto a A664Message (as this might violate the A664Message integrity).

## Example

```plaintext
a664Message DEMOMSG_ALLTYPES myMsg = { msgChannel = 1};
a664Message * myMsg2;
a664Frame *     myFrame;

myMsg2 = myMsg;        // copy myMsg onto myMsg2
//myMsg2.EthVlId = 2;  // forbidden for messages

write("Msg2 as copy from Msg: #Ch:%d VlId=%x name:=%s",
myMsg2.msgChannel,
myMsg2.EthVlId, myMsg2.name);

myFrame = myMsg;        // copy myMsg onto myFrame
myFrame.EthVlId = 1;    // allowed for frames

write("myFrame as copy from Msg: #Ch:%d VlId=%x name:=%s", myFrame.msgChannel,
myFrame.EthVlId, myFrame.name);
myFrame.EthVlId = 3;
myFrame.msgChannel = 2;

write("myFrame modified2: #Ch:%d VlId=%x name:=%s", myFrame.msgChannel,
myFrame.EthVlId, myFrame.name);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)