# AREthGetProtocol

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```
dword AREthGetProtocol ( dword messageHandle );
```

## Description

This function returns the protocol (UDP/TCP) the SOME/IP message was transmitted with.

## Parameters

- **messageHandle**: Handle of the received SOME/IP message.

  **Note**: This function can only be called within the [OnAREthMessage](CAPLfunctionOnAREthMessage.md) callback function.

## Return Values

- **Protocol**:
  - `0`: An error occurred. The error can be evaluated using the [AREthGetLastError](CAPLfunctionAREthGetLastError.md) function.
  - `6`: TCP
  - `17`: UDP

## Example

```c
void OnAREthMessage( dword messageHandle )
{
  dword protocol      = 0;
  LONG  errorCode     = 0;
  LONG  errorOccured  = 0;

  // get data from SOME/IP message
  if((protocol = AREthGetProtocol(messageHandle)) == 0)
  {
    // check if last function was executed correct
    if((errorCode = AREthGetLastError()) != 0)
    {
      write("AUTOSAR Eth IL error occured: Error code: %d", errorCode);
      errorOccured = 1;
    } // if
  } // if

  if(errorOccured == 0)
  {
    write("SOME/IP message with Protocol Type 0x%x (%d) received",protocol,protocol);
  } // if
}
```

[See Also](javascript:void(0);)
- [AREthFillValues](CAPLfunctionAREthFillValues.md#aanchor7828)
- [AREthGetDestinationAddress](CAPLfunctionAREthGetDestinationAddress.md#aanchor23823)
- [AREthGetDestinationPort](CAPLfunctionAREthGetDestinationPort.md#aanchor1389)
- [AREthGetInterfaceVersion](CAPLfunctionAREthGetInterfaceVersion.md#aanchor8618)
- [AREthGetLength](CAPLfunctionAREthGetLength.md#aanchor584)
- [AREthGetMessageId](CAPLfunctionAREthGetMessageId.md#aanchor12320)
- [AREthGetMessageType](CAPLfunctionAREthGetMessageType.md#aanchor30485)
- [AREthGetProtocol](#aanchor24304)
- [AREthGetProtocolVersion](CAPLfunctionAREthGetProtocolVersion.md#aanchor14682)
- [AREthGetRequestId](CAPLfunctionAREthGetRequestId.md#aanchor13716)
- [AREthGetReturnCode](CAPLfunctionAREthGetReturnCode.md#aanchor405)
- [AREthGetSourceAddress](CAPLfunctionAREthGetSourceAddress.md#aanchor11241)
- [AREthGetSourcePort](CAPLfunctionAREthGetSourcePort.md#aanchor6456)
- [AREthGetValue...](CAPLfunctionAREthGetValue.md#aanchor3713)
- [AREthGetValueDWord](CAPLfunctionAREthGetValueDWord.md#aanchor1597)
- [AREthGetValueFloat](CAPLfunctionAREthGetValueFloat.md#aanchor8487)
- [AREthGetValueInt64](CAPLfunctionAREthGetValueInt64.md#aanchor16774)
- [AREthGetValueLong](CAPLfunctionAREthGetValueLong.md#aanchor17591)
- [AREthGetValuePhys](CAPLfunctionAREthGetValuePhys.md#aanchor13149)
- [AREthGetValueQWord](CAPLfunctionAREthGetValueQWord.md#aanchor5973)
- [AREthGetValueString](CAPLfunctionAREthGetValueString.md#aanchor5730)
- [AREthSetRequestId](CAPLfunctionAREthSetRequestId.md#aanchor15454)
- [AREthSetReturnCode](CAPLfunctionAREthSetReturnCode.md#aanchor25639)
- [AREthSetValue...](CAPLfunctionAREthSetValue.md#aanchor18328)
- [AREthSetValueDWord](CAPLfunctionAREthSetValueDWord.md#aanchor10782)
- [AREthSetValueFloat](CAPLfunctionAREthSetValueFloat.md#aanchor18228)
- [AREthSetValueInt64](CAPLfunctionAREthSetValueInt64.md#aanchor29739)
- [AREthSetValueLong](CAPLfunctionAREthSetValueLong.md#aanchor24876)
- [AREthSetValuePhys](CAPLfunctionAREthSetValuePhys.md#aanchor11265)
- [AREthSetValueQWord](CAPLfunctionAREthSetValueQWord.md#aanchor30957)
- [AREthSetValueString](CAPLfunctionAREthSetValueString.md#aanchor9201)
- [Syntax for Database-based Access Paths](CAPLfunctionAREthSyntaxDatabaseAccessPath.md#aanchor1875)
- [Syntax for Predefined Service Discovery (SD) Access Paths](CAPLfunctionAREthSyntaxPredefinedSDAccessPath.md#aanchor18979)
