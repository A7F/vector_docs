[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionRegisterOnBeforeSendMPDU.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » **EthernetMacsecSecureEntity::RegisterOnBeforeSendMPDU**

# EthernetMacsecSecureEntity::RegisterOnBeforeSendMPDU

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Method Syntax

```plaintext
byte EthernetMacsecSecureEntity.RegisterOnBeforeSendMPDU(functionPtr callback);
```

## Description

Register a callback function which is called each time before a readily encoded MACsec frame (MPDU) is going to be transmitted.

The callback function must have the following signature:

```plaintext
dword OnBeforeSendMPDU(EthernetMacsecSecureEntity, EthernetPacket*)
```

The callback function may manipulate the frame freely. The result value from the callback function determines whether the frame will actually be sent or discarded: returning 0 will cause the frame to be discarded, otherwise the frame will be sent. Note that the ICV needs to be recalculated using the SAK if the frame has been modified by a callback.

Any number of callback functions can be registered for a physical port’s secure entity. The execution order of the callback functions is not determined. Whenever a registered callback returns 0, execution stops and the remaining callbacks will not be called.

Thus, these callback functions shall not rely on side effects of each other.

There is no way to unregister a callback function, other than stopping measurement.

## Parameters

- **callback**: The callback function to be registered.

## Return Values

- **byte**: 1 if the call succeeded, 0 otherwise.

## Example

```plaintext
EthernetMacsecSecureEntity secY1;
secY1 = ethGetMacsecSecureEntity(ethernetport::Ethernet1::Port1);
if (secY1.isValid)
{
  secY1.RegisterOnBeforeSendMPDU(ProcessMacsecFrame);
}

dword ProcessMacsecFrame(EthernetMacsecSecureEntity secy, EthernetPacket* packet)
{
  if (packet.macsec.IsAvailable())
  {
    // invert the bytes of the MPDU’s ICV
    byte disturbData[16];
    int i;
    packet.macsec.icv.GetData(0, disturbData, 16);
    for (i=0;i<16;i++)
    {
      disturbData[i] = ~disturbData[i];
    }
    packet.macsec.icv.SetData(0, disturbData, 16);
  }
  return 1; // MACsec Frame shall be transmitted
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
