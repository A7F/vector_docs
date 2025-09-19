[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthGetSourcePort.md)

**CAPL Functions** » **Ethernet** » **AUTOSAR Eth IL** » **AREthGetSourcePort**

# AREthGetSourcePort

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword AREthGetSourcePort ( dword messageHandle );
```

## Description

This function returns the source port (UDP/TCP).

## Parameters

- **messageHandle**: Handle of the received SOME/IP message.

  **Note**: This function can only be called within the [OnAREthMessage](CAPLfunctionOnAREthMessage.md) callback function.

## Return Values

- **Source port**: In the event of an error, the function returns the value 0. The [AREthGetLastError](CAPLfunctionAREthGetLastError.md) function can then be used to check whether the value is valid or an error has occurred.

## Example

```c
void OnAREthMessage( dword messageHandle )
{
  dword srcPort       = 0;
  LONG  errorCode     = 0;
  LONG  errorOccured  = 0;

  // get data from SOME/IP message
  if((srcPort = AREthGetSourcePort(messageHandle)) == 0)
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
    write("SOME/IP message from Source Port %d received",srcPort);
  } // if
}
```

**See Also**: [AREthFillValues](CAPLfunctionAREthFillValues.md#aanchor7828), [AREthGetDestinationAddress](CAPLfunctionAREthGetDestinationAddress.md#aanchor23823), [AREthGetDestinationPort](CAPLfunctionAREthGetDestinationPort.md#aanchor1389), [AREthGetInterfaceVersion](CAPLfunctionAREthGetInterfaceVersion.md#aanchor8618), [AREthGetLength](CAPLfunctionAREthGetLength.md#aanchor584), [AREthGetMessageId](CAPLfunctionAREthGetMessageId.md#aanchor12320), [AREthGetMessageType](CAPLfunctionAREthGetMessageType.md#aanchor30485), [AREthGetProtocol](CAPLfunctionAREthGetProtocol.md#aanchor24304), [AREthGetProtocolVersion](CAPLfunctionAREthGetProtocolVersion.md#aanchor14682), [AREthGetRequestId](CAPLfunctionAREthGetRequestId.md#aanchor13716), [AREthGetReturnCode](CAPLfunctionAREthGetReturnCode.md#aanchor405), [AREthGetSourceAddress](CAPLfunctionAREthGetSourceAddress.md#aanchor11241), [AREthGetSourcePort](#aanchor6456), [AREthGetValue...](CAPLfunctionAREthGetValue.md#aanchor3713), [AREthGetValueDWord](CAPLfunctionAREthGetValueDWord.md#aanchor1597), [AREthGetValueFloat](CAPLfunctionAREthGetValueFloat.md#aanchor8487), [AREthGetValueInt64](CAPLfunctionAREthGetValueInt64.md#aanchor16774), [AREthGetValueLong](CAPLfunctionAREthGetValueLong.md#aanchor17591), [AREthGetValuePhys](CAPLfunctionAREthGetValuePhys.md#aanchor13149), [AREthGetValueQWord](CAPLfunctionAREthGetValueQWord.md#aanchor5973), [AREthGetValueString](CAPLfunctionAREthGetValueString.md#aanchor5730), [AREthSetRequestId](CAPLfunctionAREthSetRequestId.md#aanchor15454), [AREthSetReturnCode](CAPLfunctionAREthSetReturnCode.md#aanchor25639), [AREthSetValue...](CAPLfunctionAREthSetValue.md#aanchor18328), [AREthSetValueDWord](CAPLfunctionAREthSetValueDWord.md#aanchor10782), [AREthSetValueFloat](CAPLfunctionAREthSetValueFloat.md#aanchor18228), [AREthSetValueInt64](CAPLfunctionAREthSetValueInt64.md#aanchor29739), [AREthSetValueLong](CAPLfunctionAREthSetValueLong.md#aanchor24876), [AREthSetValuePhys](CAPLfunctionAREthSetValuePhys.md#aanchor11265), [AREthSetValueQWord](CAPLfunctionAREthSetValueQWord.md#aanchor30957), [AREthSetValueString](CAPLfunctionAREthSetValueString.md#aanchor9201), [Syntax for Database-based Access Paths](CAPLfunctionAREthSyntaxDatabaseAccessPath.md#aanchor1875), [Syntax for Predefined Service Discovery (SD) Access Paths](CAPLfunctionAREthSyntaxPredefinedSDAccessPath.md#aanchor18979)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
