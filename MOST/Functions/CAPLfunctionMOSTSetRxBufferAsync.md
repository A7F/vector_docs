[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTSetRxBufferAsync.md)

**CAPL Functions** » **MOST** » **mostSetRxBufferAsync**

# mostSetRxBufferAsync

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This function is only available with MOST hardware VN2640 and OptoLyzer G2 3150o.

## Function Syntax

```
long mostSetRxBufferAsync (long channel, long buffermode);
```

## Description

Starts or stops draining of the asynchronous receive buffer and thereby allows to provoke low level retries.

**VN2640:**  
The node may receive a varying number of packets (MDP or MEP) before it eventually provokes low level retries. The number depends on the size of the packets and is limited either to 3 kByte of data or 255 packets. After enabling the draining of the Rx buffer again, a number of packets received during the stress mode may be shown in the Trace with time stamps close to the time of re-enabling the draining.

**OptoLyzer G2 3150o:**  
The stress network interface controller (NIC) must have its bypass opened (see [mostSetStressNodeParameter](CAPLfunctionMOSTSetGetStressNodeParameter.md)). Only packets addressed to the StressNIC will be blocked.

## Parameters

- **channel**: Channel of the connected interface.
- **buffermode**:
  - 0: stops draining the Rx buffer for MDP and MEP
  - 1: starts draining the buffer again.

## Return Values

- **0**:
- **<0**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostSetRxBufferCtrl](CAPLfunctionMOSTSetRxBufferCtrl.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
