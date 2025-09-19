[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINtpPreSend.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » LINtp_PreSend

# LINtp_PreSend

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This callback function is called every time a LIN message is scheduled to be sent. The function allows to change the message data.

**Caution**:  
Changing message data before they are sent can violate the TP protocol and lead to errors! Please make sure that the network can handle these situations!

## Function Syntax

```plaintext
void LINtp_PreSend(byte data[]);
```

## Description

The callback function is called before a LIN message is sent with the provided data.

## Parameters

- **data**: Message data

## Return Values

—

## Example

```plaintext
LINtp_PreSend(byte data[])
{
  // ...
  // change sequence number of the consecutive frame
  data[1] = data[1] + 1;
  // ...
}
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
