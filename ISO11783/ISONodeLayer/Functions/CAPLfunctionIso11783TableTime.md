[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783TableTime.md)

## Iso11783TableTime

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783TableTime

### Function Syntax

```plaintext
dword Iso11783TableTime( char busName[] );
```

### Description

The function returns the time stamp of the last received "Request for Address Claim". Use this function to determine if the network table is up to date.

### Parameters

- **busName**: Bus name or "default"

### Return Values

Time stamp of the last received Request for Address Claim in 10µs

### Example

```plaintext
dword time;
time = Iso11783TableTime( "default" );

if (time + 25000 < timeNow()) {
    write( "Last Request for ACL is older than 250ms" );
}
```
