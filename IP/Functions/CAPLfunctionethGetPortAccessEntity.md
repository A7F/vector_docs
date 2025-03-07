[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Functions/CAPLfunctionethGetPortAccessEntity.md)

# ethGetPortAccessEntity

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » ethGetPortAccessEntity

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
EthernetPortAccessEntity ethGetPortAccessEntity(ethernetPort port);
```

## Description

Returns the MACsec Port Access Entity associated with the given measurement port. The measurement port must have an existing MACsec configuration to get a valid port access entity.

## Parameters

- **port**: A measurement port with an existing MACsec configuration.

## Return Values

- **EthernetPortAccessEntity**: The MACsec port access entity. Check with its property `isValid` if the call succeeded.

## Example

```plaintext
variables {
    EthernetPortAccessEntity pae1;
}
on prestart
{
    pae1 = ethGetPortAccessEntity(ethernetport::Ethernet1::Port1);
    if (pae1.isValid)
    {
        pae1.active = false;
    }
}

on key ‘s’
{
    if (pae1.isValid)
    {
        if (pae1.active)
            pae1.active = false;
        else
            pae1.active = true;
    }
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)