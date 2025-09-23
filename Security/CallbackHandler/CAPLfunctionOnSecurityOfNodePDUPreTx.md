# OnSecurityOfNodePDUPreTx

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```c
void OnSecurityOfNodePDUPreTx(char nodeName[], char networkName[], char pduName[], dword dataId, byte payload[], dword payloadLength, qword& authInfoHigh, qword& authInfo, dword authInfoBitLength, qword& freshness, dword freshnessBitLength, dword freshnessValueId)
```

## Description

This callback handler is called before the specified node on the specified network transmits a secured PDU, after all data updates and the automatic Authenticator (MAC) calculation have been done.

Payload, authInfo (Authentication Information) and Freshness can be modified before the transmission starts. By this a fault injection is easily possible.

You have to call [SecurityLocalStartControlSimulationNode](../Functions/CAPLfunctionSecurityLocalStartControlSimulationNode.md) before this callback is called.

## Parameters

- **char nodeName[]**: The name of the node.
- **char networkName[]**: The name of the network the node is on.
- **char pduName[]**: The name of the PDU.
- **dword dataId**: The data ID of the PDU.
- **byte payload[]**: The payload of the PDU.
- **dword payloadLength**: The payload length of the PDU in bytes.
- **qword& authInfoHigh [Out]**: Upper 64 bits of the authenticator (MAC), if authenticator is larger than 64 bits. Otherwise 0;
- **qword& authInfo [Out]**: The full authenticator value or the lower 64 bits of the authenticator (MAC), if authenticator is larger than 64 bits.
- **dword authInfoBitLength**: Length of complete received authenticator (length of authInfo if the authenticator is \<= 64 bit, otherwise length of authInfo + authInfoHigh)
- **qword& freshness [Out]**: The freshness value.
- **dword freshnessBitLength**: The freshness value length in bits.
- **dword freshnessValueId**: The freshness value ID of the PDU.

## Return Values

- **byte payload[]**: The payload of the PDU.
- **qword& authInfoHigh [Out]**: Upper 64 bits of the authenticator (MAC), if authenticator is larger than 64 bits. Otherwise 0;
- **qword& authInfo [Out]**: The full authenticator value or the lower 64 bits of the authenticator (MAC), if authenticator is larger than 64 bits.
- **qword& freshness [Out]**: The freshness value.

## Example

```plaintext
void OnSecurityOfNodePDUPreTx(char nodeName[], char networkName[], char pduName[], dword dataId, byte payload[], dword payloadLength, qword& authInfoHigh, qword& authInfo, dword authInfoBitLength, qword& freshness, dword freshnessBitLength, dword freshnessValueId)
{
    char testNodeName[10] = "ECU1";
    char testNetworkName[10] = "CAN1";

    if((!strncmp(nodeName,testNodeName,strlen(nodeName)))&&(!strncmp(networkName,testNetworkName,strlen(networkName))))
    {
        if (dataId == 1)
        {
            authInfo = 0x123456; // change mac
            // freshness = 0x02; // change freshness
            // payload[0] = 0xFF; // change payload;
        }
    }
}
```
