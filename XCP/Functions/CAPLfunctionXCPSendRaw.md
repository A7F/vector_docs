[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/XCP/Functions/CAPLfunctionXCPSendRaw.md)

**CAPL Functions** » **XCP** » **xcpSendRaw**

# xcpSendRaw

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void xcpSendRaw(char ecuQualifier[], byte data[], long dataSize, byte expectResponse);
```

## Callback

```plaintext
void OnXcpSendRaw(char ecuQualifier[], byte data[], long dataSize);
```

## Description

Sends any data as control command to an XCP/CCP device. The first data byte defines the control command code.

The callback is called with the response to a raw XCP command sent by `xcpSendRaw`.

## Parameters

- **ecuQualifier**: Name of the device, configured within the CANoe DE Family [XCP/CCP Window](../../../CANoeCANalyzer/AMDXCP/XCPConfiguration.md).
- **data**: Byte array of the data to be sent.
- **dataSize**: Length of the data to be sent.
- **expectResponse**:
  - 0: The XCP slave will not respond to this command
  - 1: The XCP slave is expected to respond to this command and the callback will be called

## Return Values

—

## Example

```plaintext
// This example shows an upload of 4 bytes from address 0x21A1B4 of the XCP slave device "XCPsim" when the user presses the key 't'.
// Please note that this device is a PC application, hence the address is given in Intel format.

on key 't'
{
  byte data[8] = {0xF4, 4, 0, 0, 0xB4, 0xA1, 0x21, 0};
  xcpSendRaw("XcpSim", data, 8, 1);
}

OnXcpSendRaw(char ecuQualifier[], byte data[], long dataSize)
{
  char buffer[200];
  long i;
  buffer[0] = 0;
  for (i = 0; i < dataSize; i++)
  {
    snprintf(buffer, elcount(buffer), "%s 0x%2X", buffer, data[i]);
  }
  write("Raw response: %d bytes:%s", dataSize, buffer);
}
```

[xcpDeactivate](CAPLfunctionXCPDeactivate.md)

© Vector Informatik GmbH  
**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)