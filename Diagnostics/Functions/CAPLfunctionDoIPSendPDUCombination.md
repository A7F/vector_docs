# DoIP_SendPDUCombination

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**

Executing `SendPDUCombination` does not clear the container buffer, i.e. when calling [DoIP_AddCombinedPDU](CAPLfunctionDoIPAddCombinedPDU.md) after sending, the container will be extended further. To empty the container, you need to call [DoIP_CreatePDUCombination](CAPLfunctionDoIPCreatePDUCombination.md) again after sending.

The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```
long DoIP_SendPDUCombination();
```

## Description

Send the combined PDUs on the open TCP connection in one block. Typically, the PDUs will be sent in one IP packet, depending on the PDU size of the transporting medium.

## Parameters

—

## Return Values

- **-11**: Sending data on the TCP connection failed
- **-6**: No PDUs have been combined yet
- **-4**: The TCP connection is not established
- **0**: Success
- **Other**: Reserved

## Example

```c
BYTE rawReq[7] = {
    0x0E, 0x80, // source address (tester)
    0x10, 0x00, // target address (ECU)
    0x22, 0x01, 0x05 // diagnostics service Read Data By Identifier
};

// Initialize the PDU combination, i.e. drop previous combination
DoIP_CreatePDUCombination();

// Add diagnostics message PDUs, changing the target address for each PDU
DoIP_AddCombinedPDU( 0x8001, rawReq, 7);
rawReq[3] = 0x01;
DoIP_AddCombinedPDU( 0x8001, rawReq, 7);
rawReq[3] = 0x02;
DoIP_AddCombinedPDU( 0x8001, rawReq, 7);
rawReq[3] = 0x03;
DoIP_AddCombinedPDU( 0x8001, rawReq, 7);

// Send the PDU combination. On Ethernet all four PDUs will be put into the
// same frame and arrive together at the DoIP gateway
DoIP_SendPDUCombination();
```

[DoIP_AddCombinedPDU](CAPLfunctionDoIPAddCombinedPDU.md) • [DoIP_CreatePDUCombination](CAPLfunctionDoIPCreatePDUCombination.md) • [DoIP_TCPSend](CAPLfunctionDoIPTCPSend.md)
