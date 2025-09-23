# J1939TableTime

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword J1939TableTime( char busName[] );
```

## Description

The function returns the time stamp of the last received "Request for Address Claim". Use this function to determine if the network table is up to date.

## Parameters

- **busName**: bus name or "default"

## Return Values

Time stamp of the last received Request for Address Claim in 10µs

## Example

```plaintext
dword time;
time = J1939TableTime( "default" );

if (time + 25000 < timeNow()) {
    write( "Last Request for ACL is older than 250ms" );
}
```
