[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939NodeLayer/Functions/CAPLfunctionJ1939TableTime.md)

**CAPL Functions** » **J1939** » **J1939 NL** » **J1939TableTime**

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

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
