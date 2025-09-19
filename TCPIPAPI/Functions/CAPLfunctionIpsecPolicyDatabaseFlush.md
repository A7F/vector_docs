[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIpsecPolicyDatabaseFlush.md)

**CAPL Functions** » **TCP/IP API** » **ipsecPolicyDatabaseFlush**

# ipsecPolicyDatabaseFlush

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
The function is dependent on the selected stack. This functionality cannot be used in connection with the operating system TCP/IP stack.

## Function Syntax

```plaintext
long ipsecPolicyDatabaseFlush();
```

## Description

This functions deletes all IPsec security policies from the current network stack.

## Parameters

—

## Return Values

- **0**: Success
- **-1**: Failed

## Example

```plaintext
on start
{
  // add two policies
  IpSecPolicyDatabaseAdd(ip_Endpoint(0.0.0.0:0), 0, ip_Endpoint(192.168.1.12:23), 32, "any", "out bypass");
  IpSecPolicyDatabaseAdd(ip_Endpoint(0.0.0.0:0), 0, ip_Endpoint(192.168.1.13:23), 32, "any", "out discard");

  // ... do anything ...

  // remove all policies
  IPsecPolicyDatabaseFlush();
}
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
