# diagSetTimeout

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long diagSetTimeout (DWORD timeout)
```

## Description

Specifies the request timeout. A diagnostics response must start within this time, i.e. this corresponds to the P2 timeout.

**Note**  
This function can only be used in combination with the CAPL Callback Interface. In this case you can use [diagSetP2Extended](CAPLfunctionDiagGetP2ExtendedDiagSetP2Extended.md) to specify the handling of pending responses. When the built-in diagnostic channel is used, the function [diagSetP2Timeouts](CAPLfunctionDiagSetP2Timeouts.md) must be used to set P2 and P2-extended together.

**Note**  
It is recommended to define the times **P2 Timeout** and **P2 Extended** as short as possible and just as long as necessary. In particular you should mind that these times have to have a smaller value than the application timeout (VDSRequestApplicationTimeout in CAN.ini). The application timeout makes sure that waiting for a final response will be aborted if an ECU continuously responds "response pending" to a request.

## Parameters

- **timeout**  
  Timeout in ms  
  Default: 1000 ms.

## Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

```plaintext
on start
{
  diagSetTimeout (200); // Set timeout to 200 ms
  diagSetTimeoutHandler("Request_Timeout");
}

on key '1'
{
  DiagRequest SimECU.ReadDataByIdentifier_Process req;
  diagSendRequest(req);
}

void Request_Timeout()
{
  write("No response received within expected time frame!");
}
```
