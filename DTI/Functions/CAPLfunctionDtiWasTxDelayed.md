[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DTI/Functions/CAPLfunctionDtiWasTxDelayed.md)

[CAPL Functions](../../CAPLfunctions.md) » [DTI](../CAPLfunctionsDTIOverview.md) » DtiWasTxDelayed

# DtiWasTxDelayed

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
byte DtiWasTxDelayed(ethernetPacket packet);
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```plaintext
byte DtiPipe::WasTxDelayed(ethernetPacket packet);
```

## Description

The function returns true if the provided packet could not be sent at the specified time stamp. E.g. if [DtiSend](CAPLfunctionDtiSend.md) was called with a timestamp from the past.

## Parameters

- **packet**: The Ethernet packet that is to be checked.

## Return Values

- **0**: The packet was transmitted on time.
- **1**: The packet was delayed.

## Example

```plaintext
variables
{
  dword gPipe;
  ethernetPacket gPkt;
}

on start
{
  stack ethernetPort port = ethernetPort::Ethernet1::ECU_2;
  gPipe = DtiOpen(port);
  if (gPipe == 0)
  {
    write("failed to open pipe");
    return;
  }

  gPkt.source = ethGetMacAddressAsNumber("02:00:00:00:00:01");
  gPkt.destination = ethGetMacAddressAsNumber("ff:ff:ff:ff:ff:ff");
}

on stopMeasurement
{
  if (DtiClose(gPipe) != 0)
  {
    write("failed to close pipe");
    return;
  }
}

on ethernetPacket *
{
  if (DtiWasTxDelayed(this))
    write("packet was delayed");
  else
    write("packet was not delayed");
}

on key '1'
{
  int64 timeNs;

  write("sending, packet should be delayed");
  timeNs = timeNowInt64() - 1;

  if (DtiSend(gPipe, gPkt, timeNs) != 0)
  {
    write("failed to send packet");
    return;
  }
}

on key '2'
{
  int64 timeNs;

  write("sending, packet should not be delayed");
  timeNs = timeNowInt64() + (1 * 1e9);

  if (DtiSend(gPipe, gPkt, timeNs) != 0)
  {
    write("failed to send packet");
    return;
  }
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)